# Ejercicios para el Perfil Senior en Java

## Ejercicio 2:  Implementación de Algoritmo de Ordenamiento

### Instrucciones:Ejercicio 2:
Escribe un método en Java que tome una lista de strings y devuelva la concatenación de todos los strings que tengan una longitud mayor que 5.

## Ejemplo:

import java.util.ArrayList;
import java.util.List;

public class ConcatenarStrings {
    public static String concatenarStrings(List<String> strings) {
        StringBuilder resultado = new StringBuilder();
        for (String s : strings) {
            if (s.length() > 5) {
                resultado.append(s);
            }
        }
        return resultado.toString();
    }

    public static void main(String[] args) {
        List<String> lista = new ArrayList<>();
        lista.add("Manzana");
        lista.add("Banana");
        lista.add("Naranja");
        lista.add("Fresa");
        lista.add("Sandía");
        lista.add("Pera");

        System.out.println("Strings concatenados: " + concatenarStrings(lista));
    }
}
