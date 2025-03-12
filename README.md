# atividade-get-e-set
import java.util.Scanner;

import java.util.Scanner;

class Program {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);


        Pessoa pessoa = new Pessoa();


        pessoa.setNome("João");
        pessoa.setIdade(30);


        System.out.println("O nome da pessoa é: " + pessoa.getNome());
        System.out.println("A idade é: " + pessoa.getIdade());


        scanner.close();
    }
}
class Pessoa {
    // Atributos privados
    private String nome;
    private int idade;

    // Método getter para o nome
    public String getNome() {
        return nome;
    }

    // Método setter para o nome
    public void setNome(String nome) {
        this.nome = nome;
    }

    // Método getter para a idade
    public int getIdade() {
        return idade;
    }

    // Método setter para a idade
    public void setIdade(int idade) {
        this.idade = idade;
    }
}
