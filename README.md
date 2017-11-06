# Bazuca-de-medicina

#include <stdio.h>
#include <string.h>
/*1 - Ordem crescente de cdigo de doadores*/
/*2 - Ordem alfabética de nomes de doadores*/
/*3 - Ordem alfabética de tipos sanguíneos e fator RH*/
int main(int argc, char **argv)
{
    int i,j,n,op;


    struct
    {
        int codigo;
        char nome[51];
        char tipo[3];
        char fatorRH;
    } BDS[100],aux;

    scanf("%d",&n);

    for(i=0; i<n; i++)
    {
        printf("Código do Doador: ");
        scanf("%d",&BDS[i].codigo);
        printf("Nome do Doador: ");
        scanf(" %[^\n]",BDS[i].nome);
        printf("Tipo sanguíneo: ");
        scanf(" %[^\n]",BDS[i].tipo);
        printf("Fator RH: ");
        scanf(" %c",&BDS[i].fatorRH);

        printf("\n");
    }

    scanf("%d",&op);

    switch(op)
    {
    /*1 - Ordem crescente de cdigo de doadores*/
    case 1:

        for(i=0; i<n; i++)
        {
            for(j=i+1; j<n; j++)
            {
                if(BDS[i].codigo > BDS[j].codigo)
                {
                    aux = BDS[i];
                    BDS[i] = BDS[j];
                    BDS[j] = aux;
                }
            }

        }

        for(i=0; i<n; i++)
        {
            printf("Código do Doador: %d\n",BDS[i].codigo);
            printf("Nome do Doador: %s\n",BDS[i].nome);
            printf("Tipo Sanguíneo: %s\n",BDS[i].tipo);
            printf("Fator RH: %c\n",BDS[i].fatorRH);
            printf("\n");
        }
        break;
    /*2 - Ordem alfabética de nomes de doadores*/
    case 2:

        for(i=0;i<n;i++)
        {
            for(j=0;j<n;j++)
            {

                if(BDS[i].nome < BDS[j].nome)
                {
                  aux = BDS[i];
                    BDS[i] = BDS[j];
                    BDS[j] = aux;
                }

            }
        }

        for(i=0; i<n; i++)
        {
            printf("Código do Doador: %d\n",BDS[i].codigo);
            printf("Nome do Doador: %s\n",BDS[i].nome);
            printf("Tipo Sanguíneo: %s\n",BDS[i].tipo);
            printf("Fator RH: %c\n",BDS[i].fatorRH);
            printf("\n");
        }

        break;
    /*3 - Ordem alfabética de tipos sanguíneos e fator RH*/
    case 3:

        for(i=0;i<n;i++)
        {
            for(j=0;j<n;j++)
            {

                if(strcmp(BDS[i].tipo,BDS[j].tipo)<0)
                {
                    aux = BDS[i];
                    BDS[i] = BDS[j];
                    BDS[j] = aux;
                }
                else if(strcmp(BDS[i].tipo,BDS[j].tipo))
                {
                    if(BDS[i].fatorRH>BDS[j].fatorRH)
                    {
                    aux = BDS[i];
                    BDS[i] = BDS[j];
                    BDS[j] = aux;
                    }
                }

            }
        }



        for(i=0; i<n; i++)
        {
            printf("Código do Doador: %d\n",BDS[i].codigo);
            printf("Nome do Doador: %s\n",BDS[i].nome);
            printf("Tipo Sanguíneo: %s\n",BDS[i].tipo);
            printf("Fator RH: %c\n",BDS[i].fatorRH);
            printf("\n");
        }

        break;
    }

    return 0;
}
