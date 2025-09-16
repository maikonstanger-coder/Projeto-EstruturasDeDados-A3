# QuickSort em Java

Este projeto demonstra a implementação do algoritmo QuickSort em Java, como parte da atividade A3 da disciplina Programação de Soluções Computacionais.

```java
public class QuickSort {
    public static void quickSort(int[] array, int inicio, int fim) {
        if (inicio < fim) {
            int p = particiona(array, inicio, fim);
            quickSort(array, inicio, p - 1);
            quickSort(array, p + 1, fim);
        }
    }

    private static int particiona(int[] array, int inicio, int fim) {
        int pivo = array[fim];
        int i = inicio - 1;

        for (int j = inicio; j < fim; j++) {
            if (array[j] <= pivo) {
                i++;
                troca(array, i, j);
            }
        }

        troca(array, i + 1, fim);
        return i + 1;
    }

    private static void troca(int[] array, int i, int j) {
        int temp = array[i];
        array[i] = array[j];
        array[j] = temp;
    }

    public static void main(String[] args) {
        int[] dados = {42, 23, 4, 16, 8, 15};
        quickSort(dados, 0, dados.length - 1);

        System.out.println("Array ordenado:");
        for (int num : dados) {
            System.out.print(num + " ");
        }
    }
}
