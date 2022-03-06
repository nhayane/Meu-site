# RESPOSTA DO DESAFIO
Gihub para o desafio de programação.
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Algoritmos {

	/**
	 * Retorna o valor da mediana do vetor informado, após a ordenação do vetor.
	 * 
	 * @param entrada Vetor de entrada.
	 * @return Valor da mediada.
	 */
	public static int mediana(int[] entrada) {
		List<Integer> lista = new ArrayList<>();
		for (int numero : entrada) {
			lista.add(numero);
		}
		Collections.sort(lista);
		return lista.get(lista.size() / 2);
	}

	/**
	 * Conta o número de pares formado por dois elementos do vetor de entrada, onde
	 * a diferença corresponde ao valor informado.
	 * 
	 * @param entrada   Vetor de entrada.
	 * @param diferenca Diferença.
	 * @return Número de pares.
	 */
	public static int contaPares(int[] entrada, int diferenca) {
		int pares = 0;
		for (int i = 0; i < entrada.length; i++) {
			for (int j = i + 1; j < entrada.length; j++) {
				if ((entrada[i] - entrada[j]) == diferenca || (entrada[i] - entrada[j]) == -diferenca) {
					pares++;
				}
			}
		}
		return pares;
	}

	/**
	 * Realiza a encriptação do texto de entrada.
	 * 
	 * @param entrada Texto de entrada.
	 * @return Texto encryptado.
	 */
	public static String encriptar(String entrada) {
		entrada = entrada.replaceAll(" ", "");
		int tamanhoGrid = (int) Math.sqrt(entrada.length());
		if ((tamanhoGrid * tamanhoGrid) < entrada.length())
			tamanhoGrid++;
		String saida = "";
		for (int i = 0; i < tamanhoGrid; i++) {
			for (int j = 0; j < tamanhoGrid; j++) {
				int posicao = i + tamanhoGrid * j;
				if (posicao < entrada.length())
					saida += entrada.charAt(posicao) + "";
				if (j == tamanhoGrid - 1)
					saida += " ";
			}
		}
		return saida.trim();
	}

	public static void main(String[] args) {
		System.out.println(mediana(new int[] { 0, 6, 5, 3, 2 }));
		System.out.println(encriptar("tenha um bom dia"));
		System.out.println(encriptar("ola mundo"));
		System.out.println(contaPares(new int[] { 1, 5, 3, 4, 2 }, 2));
	}
}
