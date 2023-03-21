#include <stdio.h>
#include <stdlib.h>

void mostrarMenu()  //Função para mostrar o menu
{
    printf("\n---------------------MENU-----------------------");
    printf("\n1 - Cadastrar\n2 - Remover\n3 - Quantidade de chapas estocadas por tipo\n4 - Tipos de chapas de madeira sem estoque\n5 - Quantidade total de chapas estocadas\n6 - Quantidade em metros quadrados estocados\n7 - Alteracao da Quantidade de chapas estocadas\n8 - fim");
    printf("\n------------------------------------------------\n");
}
//posso pedir ajuda pro vitor, pro monitor, pro pessoal q ta em algo II
//estudar bastante funções (vai cair bastante na proxima prova)(fiz uma função sem retorno sem pararemtros etc)
int main() 
{
    int chapas[7][2] = {{0, 0}, {0, 0}, {0, 0}, {0, 0}, {0, 0}, {0, 0}, {0, 0}}, entrada, i, count = 0, cod = 0, isOn = 1;
    while(1)    //while deveria ser feito como while(op=!8) n é uma boa opção fazer como fiz
    {
        mostrarMenu();
        scanf("%d", &entrada); //era melhor ter colocado junto ao menu
        
        while(entrada < 1 || entrada > 7) //Enquanto entrada for inválida, mostre menu
        {
            mostrarMenu();
            scanf("%d", &entrada);
        }

        switch (entrada)
        {
            case 1:
                if(cod == 7) //Verifica se já existem 7 produtos cadastrados
                {
                    printf("\nJa ha %d produtos cadastrados.", cod);   
                }
                
                if(cod < 7) //se tiver menos que 7 produtos cadastrados //podia ter um else ao invés de if
                {
                    printf("\nDigite o tipo do produto que deseja cadastrar (digite apenas numeros):\nTipo 1 - 120cm\nTipo 2 - 85cm\nTipo 3 - 42cm\n"); //solicita tipo
                    scanf("%d", &chapas[cod][0]);
                    printf("\nDigite a quantidade de chapas:");//Solicita cod de chapas
                    scanf("%d", &chapas[cod][1]);
                    
                    if(chapas[cod][1] < 0) //se a cod de chapas for menor q 0 //ao invés de if a prof faria por while
                    {
                        printf("\n\nNao eh possivel cadastrar qnt negativas"); //reclama   
                    }
                        
                    if(chapas[cod][1] >= 0) //se a cod de chapas for maior q 0
                    {
                        printf("\n\nProduto cadastrado com sucesso! \nCodigo: %d \nTipo: %d \nQuantidade: %d\n", cod, chapas[cod][0], chapas[cod][1]); //printa infos da chapa cadastrada
                        cod++;  //Incrementa o número de produtos cadastrados
                    }
                }
                break;

            case 2:
                if(cod == 0)
                {
                    printf("\nNao ha chapas cadastrados.");
                }
                //tudo isso deveria estar dentro de um else
                printf("\nDigite o Código de cadastro de chapa que deseja remover (0-%d): ", --cod); //Solicita código da chapa para remover
                scanf("%d", &entrada);
                
                for(int i = entrada-1; i < cod; i++) //var i Percorre todas as chapas cadastradas a partir da posição da chapa que deseja remover até o final da lista de produtos
                {
                    chapas[i][0] = chapas[i+1][0]; //A posição atual recebe os valores da posição posterior
                    chapas[i][1] = chapas[i+1][1];
                }
                printf("\nCadastro removido com sucesso.");
                cod--;  //Decrementa o número de produtos cadastrados
                break;

            case 3:
                if(cod == 0)
                {
                    printf("\nNao ha produtos cadastrados.");
                }
                                                                                //a prof ao invés do cod-- colocaria alguma info de que o item foi removido por ex tipo 9 ou tipo 0
                printf("\nDigite o tipo que deseja verificar: "); //Solicita tipo de chapa
                scanf("%d", &entrada);
                count = 0;  //Inicializa a quantidade total de chapas como 0
                
                for(int i = 0; i <= cod; i++) //Percorre todos os produtos cadastrados
                {
                    if(chapas[i][0] == entrada) //se tpo de chapa = ao selecionado
                        count+= chapas[i][1];   //entao add cod na qnt total de chapas
                }
                printf("\nHa %d chapas do tipo %d.", count, entrada);
                break;

            case 4:
                if(cod == 0) //Verifica se há produtos cadastrados
                {
                    printf("\nNao ha produtos cadastrados.");
                }
                int tipos[3] = {0, 0, 0}; //Cria um array de 3 posições com a quantidade de produtos de cada tipo              
                
                for(int i = 0; i <= cod; i++) //Percorre todos os produtos cadastrados
                {
                    if(chapas[i][0] == 1)  tipos[0]++; //Incrementa a posição do array
                    if(chapas[i][0] == 2)  tipos[1]++; // de acordo com o tipo de chapa
                    if(chapas[i][0] == 3)  tipos[2]++;
                }
                if(tipos[0] == 0) printf("\nEstamos sem estoque do tipo 1"); //Verifica se há produtos
                if(tipos[1] == 0) printf("\nEstamos sem estoque do tipo 2"); //de cada tipo no estoque
                if(tipos[2] == 0) printf("\nEstamos sem estoque do tipo 3");
                break;

			case 5:
                if(cod == 0)
                {
                    printf("\nNao ha produtos cadastrados.");
                }
                count = 0;//Inicializa a qnt total de chapas como 0
                
                for(int i = 0; i <= cod; i++)//Percorre todos os produtos cadastrados
                {
                    count += chapas[i][1]; //Adiciona a quantidade de chapas deste produto na quantidade total de chapas
                }
                printf("\nHa em estoque %d chapas.", count);
                break;

            case 6:
                if(cod == 0)
                {
                    printf("\nNao ha produtos cadastrados.");
                }
                count = 0;//Inicializa qnt total de chapas em m^2 como 0
                
                for(int i = 0; i <= cod; i++)//Percorre todos os produtos cadastrados
                {
                    if(chapas[i][0] == 1)  count+= chapas[i][1] * 120; //Adiciona a quantidade de chapas de tipo 1, 2 ou 3
                    if(chapas[i][0] == 2)  count+= chapas[i][1] * 85;  // na quantidade total de chapas
                    if(chapas[i][0] == 3)  count+= chapas[i][1] * 42;  //multiplicando pelos metros quadrados de cada tipo
                }
                printf("\nHa em estoque %d metros quadrados de chapas.", count);
                break;

            case 7:
                if(cod == 0)
                {
                    printf("\nNao ha produtos cadastrados.");
                }
                printf("\nDigite o código da chapa que deseja alterar (1-%d): ", cod); //solicita Código
                scanf("%d", &entrada);
                printf("\nDigite a nova quantidade de chapas: "); //solicita nova qnt chapas
                scanf("%d", &count);
                chapas[entrada][1] = count; //altera a qnt pela nova
                printf("\n\nQuantidade alterada com sucesso.");
                break;

            case 8:
                break;
        }
        entrada = 8; //entrada=0 finaliza loop
    }
    return 0;
}
