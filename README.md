# linguagem-C
exercicios basicos atv 01


#include <stdio.h>
#include <stdlib.h>
#include <string.h>


/* 2020002928_MarcioFerreiraViana */




struct aluno {

	char nome[100];    // Nome do aluno com no máximo 100 caracteres
	double matricula;  // Matrícula do Aluno
	int idade;         // Idade do Aluno
	char sexo;         // M (masculino) ou F (feminino)
	float nota1;       // Nota 1
	float nota2;       // Nota 2
	float nota3;       // Nota 3
	float media;       // Media das provas dos candidatos. Determina a pontuacao final do candidato
	char situacao[10]; // APROVADO, REPROVADO
};


int main(int argc, char *argv[]) {

	struct aluno alunos[5];
	int contador =0;
	for ( contador =0; contador<5; contador++) {



		// Entrada de dados:

		// Matricula do aluno
		printf("Entrada de Dados\n");
		printf("********************************\n");

		printf("Matricula: ");
		scanf("%lf",&alunos[contador].matricula);
		fflush (stdin); //Limpar o buffer do teclado
		// Nome do aluno
		printf("Nome: ");
		scanf("%[^\n]",alunos[contador].nome);
		fflush (stdin); //Limpar o buffer do teclado
		printf("Idade: ");
		scanf("%d",&alunos[contador].idade);
		fflush (stdin); //Limpar o buffer do teclado
		// Sexo do aluno
		printf("Sexo (M/F): ");
		scanf("%c",&alunos[contador].sexo);
		fflush (stdin);//Limpar o buffer do teclado
		// Notas 1, 2 e 3
		printf("Nota 01: ");
		scanf("%f",&alunos[contador].nota1);
		fflush (stdin);//Limpar o buffer do teclado
		printf("Nota 02: ");
		scanf("%f",&alunos[contador].nota2);
		fflush (stdin);//Limpar o buffer do teclado
		printf("Nota 03: ");
		scanf("%f",&alunos[contador].nota3);
		fflush (stdin);//Limpar o buffer do teclado

		// Calcular a média
		alunos[contador].media = (float) (alunos[contador].nota1+alunos[contador].nota2+alunos[contador].nota3) / 3;

		// Definir a situação do Aluno: APROVADO ou REPROVADO
		if (alunos[contador].media >= 6.0)
		{
			// Atribuir a string APROVADO a variável situacao
			strcpy( alunos[contador].situacao, "APROVADO");
		}
		else
		{
			// Atribuir a string REPROVADO a variável situacao
			strcpy( alunos[contador].situacao, "REPROVADO");

		}

		// Saída de dados:
		printf("\nSaida de Dados\n");
		printf("********************************\n");
		printf("Matricula = %.0lf\n",alunos[contador].matricula);
		printf("Nome      = %s\n",alunos[contador].nome);
		printf("Idade     = %d\n",alunos[contador].idade);
		printf("Sexo(M/F) = %c\n",alunos[contador].sexo);
		printf("Nota 01   = %.2f\n",alunos[contador].nota1);
		printf("Nota 02   = %.2f\n",alunos[contador].nota2);
		printf("Nota 03   = %.2f\n",alunos[contador].nota3);
		printf("Media     = %.2f\n",alunos[contador].media);
		printf("Situacao  = %s\n",alunos[contador].situacao);

	}
	int ta=0;
	int tr=0;
	for (contador=0; contador<5; contador++) {

		if (alunos[contador].media >= 6.0)
		{
			ta++;

		}
		else
		{

			tr++;

		}


	}
	printf("total de aproados %d\n",ta);
	printf("total de reprovados %d\n",tr);
	system("pause");
	return 0;
}