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

public class ContaBancaria {
    // Atributos privados
    private String titular;
    private double saldo;

   
    public ContaBancaria(String titular, double saldoInicial) {
        this.titular = titular;
        this.saldo = saldoInicial;
    }

   
    public String getTitular() {
        return titular;
    }

    public void setTitular(String titular) {
        this.titular = titular;
    }

    public double getSaldo() {
        return saldo;
    }

    public void setSaldo(double saldo) {
        this.saldo = saldo;
    }

    
    public void depositar(double valor) {
        if (valor > 0) {
            saldo += valor;
            System.out.println("Depósito de R$" + valor + " realizado com sucesso.");
        } else {
            System.out.println("Valor de depósito inválido.");
        }
    }

    
    public void sacar(double valor) {
        if (valor > 0 && valor <= saldo) {
            saldo -= valor;
            System.out.println("Saque de R$" + valor + " realizado com sucesso.");
        } else if (valor > saldo) {
            System.out.println("Saldo insuficiente para o saque.");
        } else {
            System.out.println("Valor de saque inválido.");
        }
    }

    
    public void exibirSaldo() {
        System.out.println("Saldo atual de " + titular + ": R$" + saldo);
    }

    public static void main(String[] args) {
        // Criando um objeto ContaBancaria
        ContaBancaria conta = new ContaBancaria("João", 500.00);
        conta.exibirSaldo();
        conta.depositar(200.00);
        conta.sacar(100.00);
        conta.exibirSaldo();
    }
}

public class Produto {
    
    private String nome;
    private double preco;
    private int estoque;

    
    public Produto(String nome, double preco, int estoqueInicial) {
        this.nome = nome;
        this.preco = preco >= 0 ? preco : 0;  // Verifica se o preço não é negativo
        this.estoque = estoqueInicial >= 0 ? estoqueInicial : 0;  // Verifica se o estoque não é negativo
    }

   
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public double getPreco() {
        return preco;
    }

    public void setPreco(double preco) {
        if (preco >= 0) {
            this.preco = preco;
        } else {
            System.out.println("Preço não pode ser negativo.");
        }
    }

    public int getEstoque() {
        return estoque;
    }

    public void setEstoque(int estoque) {
        if (estoque >= 0) {
            this.estoque = estoque;
        } else {
            System.out.println("Estoque não pode ser negativo.");
        }
    }

    
    public void adicionarEstoque(int quantidade) {
        if (quantidade > 0) {
            estoque += quantidade;
            System.out.println("Adicionados " + quantidade + " itens ao estoque.");
        } else {
            System.out.println("Quantidade inválida para adição ao estoque.");
        }
    }

    
    public void removerEstoque(int quantidade) {
        if (quantidade > 0 && quantidade <= estoque) {
            estoque -= quantidade;
            System.out.println("Removidos " + quantidade + " itens do estoque.");
        } else if (quantidade > estoque) {
            System.out.println("Estoque insuficiente para a remoção.");
        } else {
            System.out.println("Quantidade inválida para remoção do estoque.");
        }
    }

    public static void main(String[] args) {
        
        Produto produto = new Produto("Laptop", 2500.00, 10);
        System.out.println("Produto: " + produto.getNome());
        System.out.println("Preço: R$" + produto.getPreco());
        System.out.println("Estoque inicial: " + produto.getEstoque());

       
        produto.adicionarEstoque(5);
        produto.removerEstoque(3);
        System.out.println("Estoque atual: " + produto.getEstoque());
    }
}

