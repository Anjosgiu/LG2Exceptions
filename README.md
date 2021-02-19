# LG2Exceptions

Aluna Giulia Santana dos Anjos SP3025918

EXCEPTIONS

//CÓDIGO VIDEOAULA 1//

public class Excecao {

	public static void main(String[] args) {

		try{
			int[] vetor = new int[4];

			System.out.println("Antes da exception");

			vetor[4] = 1;

			System.out.println("Esse texto não será impresso");
		} 
    
    catch(ArrayIndexOutOfBoundsException exception){
			System.out.println("Exceção ao acessar um índide do vetor que não existe");
		}
    
		System.out.println("Esse texto será impresso após a exception");
	}

}

//CÓDIGO VIDEOAULA 2//

public class MultiplosCatch {

	public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for (int i=0; i<numeros.length; i++){
			try{
				System.out.println(numeros[i] + "/" + demon[i] + " = " + (numeros[i]/demon[i]));
			}
			catch(ArithmeticException e){
				System.out.println("Erro ao dividir por zero");
			}
			catch(ArrayIndexOutOfBoundsException e){
				System.out.println("Posição do array inválida");
			}
		}

	}

}

//CÓDIGO VIDEOAULA 3//

public class TestandoFinally {

	public static void main(String[] args) {
		
		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};
		
		for (int i=0; i<numeros.length; i++){
			try{
				System.out.println(numeros[i] + "/" + demon[i] + " = " + (numeros[i]/demon[i]));
			}
			catch(ArithmeticException e){
				System.out.println("Erro ao dividir por zero");
			}
			catch(ArrayIndexOutOfBoundsException e){
				System.out.println("Posição do array inválida");
			}
			finally {
				System.out.println("Essa linha é impressa sempre após o try ou catch");
			}
		}

	}

}


//CÓDIGO VIDEOAULA 4//

public class ExceptionGenerica {

public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for (int i=0; i<numeros.length; i++){

			try{
				System.out.println(numeros[i] + "/" + demon[i] + " = " + (numeros[i]/demon[i]));
			}
			catch(Exception e){
				System.out.println(e.getMessage());
				e.printStackTrace();
			}
		}

	}
}

//CÓDIGO 2(THROWS) - VIDEOAULA 4//

import java.util.Scanner;

public class UsandoThrows {

	public static void main(String[] args) {
		
		System.out.println("Entre com um número decimal");
		try {
			double num = leNumero();
			System.out.println("Você digitou " + num);
		} catch (Exception e) {
			System.out.println("Entrada inválida");
			e.printStackTrace();
		}

	}

	public static double leNumero() throws Exception {
		Scanner scan = new Scanner(System.in);
		double num = scan.nextDouble();
		return num;
	}
