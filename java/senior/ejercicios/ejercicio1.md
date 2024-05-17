# Pruebas Técnicas para Java con Respuestas y Ejemplos

## Senior

## Ejercicio 1:  Implementación de Algoritmo de Ordenamiento

### Instrucciones:Ejercicio 1:
Implementa un algoritmo de ordenamiento rápido (por ejemplo, Quicksort) en Java para ordenar un array de números enteros.

## Ejemplo:
```java
public class QuickSort {
    public static void quickSort(int[] array, int inicio, int fin) {
        if (inicio < fin) {
            int indiceParticion = particion(array, inicio, fin);
            quickSort(array, inicio, indiceParticion - 1);
            quickSort(array, indiceParticion + 1, fin);
        }
    }

    public static int particion(int[] array, int inicio, int fin) {
        int pivote = array[fin];
        int i = inicio - 1;
        for (int j = inicio; j < fin; j++) {
            if (array[j] < pivote) {
                i++;
                int temp = array[i];
                array[i] = array[j];
                array[j] = temp;
            }
        }
        int temp = array[i + 1];
        array[i + 1] = array[fin];
        array[fin] = temp;
        return i + 1;
    }

    public static void main(String[] args) {
        int[] array = {5, 3, 8, 1, 2, 7, 4};
        System.out.println("Array sin ordenar: " + Arrays.toString(array));
        quickSort(array, 0, array.length - 1);
        System.out.println("Array ordenado: " + Arrays.toString(array));
    }
}
