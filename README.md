# ExerciciosUNIS
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class CadastroUsuario {
    private List<String> usuarios;

    public CadastroUsuario() {
        usuarios = new ArrayList<>();
    }

    public void adicionarUsuario(String nome) {
        usuarios.add(nome);
        System.out.println("Usuário adicionado com sucesso!");
    }

    public void exibirUsuarios() {
        System.out.println("Usuários cadastrados:");
        for (String usuario : usuarios) {
            System.out.println(usuario);
        }
    }

    public static void main(String[] args) {
        CadastroUsuario cadastro = new CadastroUsuario();
        Scanner scanner = new Scanner(System.in);

        int opcao = 0;
        while (opcao != 3) {
            System.out.println("Selecione uma opção:");
            System.out.println("1 - Adicionar usuário");
            System.out.println("2 - Exibir usuários cadastrados");
            System.out.println("3 - Sair");

            opcao = scanner.nextInt();
            scanner.nextLine(); // Limpa o buffer do teclado

            switch (opcao) {
                case 1:
                    System.out.println("Digite o nome do usuário:");
                    String nomeUsuario = scanner.nextLine();
                    cadastro.adicionarUsuario(nomeUsuario);
                    break;
                case 2:
                    cadastro.exibirUsuarios();
                    break;
                case 3:
                    System.out.println("Saindo do programa...");
                    break;
                default:
                    System.out.println("Opção inválida! Tente novamente.");
                    break;
            }
        }

        scanner.close();
    }
}
