# Pruebas Técnicas para Java con Respuestas y Ejemplos

## Semi Senior

# Ejercicio 2: Análisis de Datos de Ventas

## Instrucciones:
Implementa una clase `Venta` que represente una venta con un ID, un producto, una cantidad y un precio unitario. Además, crea una clase `AnalizadorDeVentas` que gestione una lista de ventas y proporcione métodos para:

1. Calcular el ingreso total de todas las ventas.
2. Encontrar la venta con el mayor ingreso.
3. Calcular el ingreso promedio por venta.
4. Generar un informe que muestre el total de ventas por producto.

## Ejemplo:
```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

class Venta {
    private int id;
    private String producto;
    private int cantidad;
    private double precioUnitario;

    public Venta(int id, String producto, int cantidad, double precioUnitario) {
        this.id = id;
        this.producto = producto;
        this.cantidad = cantidad;
        this.precioUnitario = precioUnitario;
    }

    public int getId() {
        return id;
    }

    public String getProducto() {
        return producto;
    }

    public int getCantidad() {
        return cantidad;
    }

    public double getPrecioUnitario() {
        return precioUnitario;
    }

    public double getIngreso() {
        return cantidad * precioUnitario;
    }

    @Override
    public String toString() {
        return "Venta{" +
                "id=" + id +
                ", producto='" + producto + '\'' +
                ", cantidad=" + cantidad +
                ", precioUnitario=" + precioUnitario +
                '}';
    }
}

class AnalizadorDeVentas {
    private List<Venta> ventas;

    public AnalizadorDeVentas() {
        this.ventas = new ArrayList<>();
    }

    public void agregarVenta(Venta venta) {
        ventas.add(venta);
    }

    public double calcularIngresoTotal() {
        return ventas.stream().mapToDouble(Venta::getIngreso).sum();
    }

    public Venta encontrarVentaMayorIngreso() {
        return ventas.stream().max((v1, v2) -> Double.compare(v1.getIngreso(), v2.getIngreso())).orElse(null);
    }

    public double calcularIngresoPromedio() {
        return ventas.isEmpty() ? 0 : calcularIngresoTotal() / ventas.size();
    }

    public Map<String, Double> generarInformeVentasPorProducto() {
        Map<String, Double> informe = new HashMap<>();
        for (Venta venta : ventas) {
            informe.put(venta.getProducto(), informe.getOrDefault(venta.getProducto(), 0.0) + venta.getIngreso());
        }
        return informe;
    }
}

public class AnalizadorDeVentasDemo {
    public static void main(String[] args) {
        AnalizadorDeVentas analizador = new AnalizadorDeVentas();
        analizador.agregarVenta(new Venta(1, "Laptop", 3, 800.00));
        analizador.agregarVenta(new Venta(2, "Smartphone", 5, 500.00));
        analizador.agregarVenta(new Venta(3, "Tablet", 2, 300.00));

        System.out.println("Ingreso total: $" + analizador.calcularIngresoTotal());

        System.out.println("Venta con mayor ingreso:");
        System.out.println(analizador.encontrarVentaMayorIngreso());

        System.out.println("Ingreso promedio por venta: $" + analizador.calcularIngresoPromedio());

        System.out.println("Informe de ventas por producto:");
        Map<String, Double> informe = analizador.generarInformeVentasPorProducto();
        for (Map.Entry<String, Double> entrada : informe.entrySet()) {
            System.out.println(entrada.getKey() + ": $" + entrada.getValue());
        }
    }
}
