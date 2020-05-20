# projetotecinfo
Atividades

#include <stdio.h>
#include <iostream>
#include <math.h>
using namespace std;

/**
 * Turma: Terça - Noite
 * Disciplina: Introdução à programação I
 * Professor: Rachel Pernambuco
 * Aluno: Jamilli Vitória Oliveira 
 * Matricula: 201908105101
 * Data:15/05/2020
 *
 * 1) Atividade: Fazer um programa em C++ e exibir:
 * 1.Soma de dois numeros
 * 2.O produto do primeiro pelo quadrado do segundo    
 * 3.O quadrado do primerio numero
 * 4.A raiz quadrada da soma dos quadrados 
 * 5.O seno da diferença do primeiro numero pelo segundo
 * 6.O modulo do primeiro numero
*/

//1.Soma de dois numeros
double somaDoisNumeros(int a, int b)
{
    return (a + b);
}

//2.O produto do primeiro pelo quadrado do segundo 
double produtoDoPrimeiro(int a, int b)
{
    return (a * pow(b,2));
}

//3.O quadrado do primerio numero
double quadradoDoPrimeiro(int a, int b)
{
    return (pow(a,2));
}

//4.A raiz quadrada da soma dos quadrados 
double raizQuadradaSoma(int a, int b)
{
    return sqrt( pow(a,2)+pow(b,2) );
}

//5.O seno da diferença do primeiro numero pelo segundo
double senoDoisNumero(int a, int b)
{
    return sin(a-b);
}

// 6.O modulo do primeiro numero
double moduloNumero(int a, int b)
{
    return abs(a);
}

int main()
{
    //variaveis
    double pnumero, snumero;

    //leitura dos dados
    cout <<"Ler o primeiro numero: ";
    cin >>pnumero;

    cout <<"Ler o segundo numero: ";
    cin >>snumero;

    //resultados
    cout << "\n 1) Resultado = " << somaDoisNumeros(pnumero, snumero) << "\n";
    cout << "\n 2) Resultado = " << produtoDoPrimeiro(pnumero, snumero) << "\n";
    cout << "\n 3) Resultado = " << quadradoDoPrimeiro(pnumero, snumero) << "\n";
    cout << "\n 4) Resultado = " << raizQuadradaSoma(pnumero, snumero) << "\n";
    cout << "\n 5) Resultado = " << senoDoisNumero(pnumero, snumero) << "\n";
    cout << "\n 6) Resultado = " << moduloNumero(pnumero, snumero) << "\n";

    return 0;
} 
 questao2.cpp 

#include <stdio.h>
#include <iostream>
#include <math.h>
#include <iomanip>
using namespace std;

/**
 * Turma: Terça - Noite
 * Disciplina: Introdução à programação I
 * Professor: Rachel Pernambuco
* Aluno: Jamilli Vitória Oliveira 
* Matricular: 201908105101
* Data:15/05/2020
*
* 2)Atividade: 
* Escreve  um programa na linguagem C++, onde serao feitas leituras de um 
* numero de eleitores de um pais, o numero de votos nulos, brancos e validos
* Escrever e tambem calcular o percentual que cada um vai representar em 
* relacao ao total dos seus eleitores nessa votacao. 
*/

/*  OBSERVAÇÃO 
    observacao o numero de percentual baseado no numero de eleitores e não em numero de votos validos
    confirmar com o professor, questao com duplo sentido!
*/

float pnulos(int neleitores,int vnulos ){
    return (vnulos*100/neleitores);
}

float pbrancos(int neleitores,int vbrancos ){
    return (vbrancos*100/neleitores);
}

float pvalidos(int neleitores,int vvalidos ){
    return (vvalidos*100/neleitores);
}


int main()
{
    //variaveis
    double neleitores,vnulos,vbrancos,vvalidos;

    //leitura dos dados
    cout <<"Ler o numero de eleitores: ";
    cin >>neleitores;

    cout <<"Ler o numero de votos nulos: ";
    cin >>vnulos;

    cout <<"Ler o numero de votos brancos: ";
    cin >>vbrancos;

    cout <<"Ler o numero de votos validos: ";
    cin >>vvalidos;

    //resultados
    cout << "\n Percentagem de votos nulos:   "<< setprecision (2) << fixed << pnulos(neleitores,vnulos)<<"% \n";
    cout << "\n Percentagem de votos brancos: "<< setprecision (2) << fixed << pbrancos(neleitores,vbrancos)<<"% \n";
    cout << "\n Percentagem de votos validos: "<< setprecision (2) << fixed << pvalidos(neleitores,vvalidos)<<"% \n";

    return 0;
} 
 
 questao3.cpp 

#include <stdio.h>
#include <iostream>
#include <math.h>
#include <iomanip>
using namespace std;

/**
 * Turma: Terça - Noite
 * Disciplina: Introdução à programação I
 * Professor: Rachel Pernambuco
 * Aluno: Jamilli Vitória Oliveira 
 * Matricular: 201908105101
 * Data:15/05/2020
 * 
 * 3) Atividade: Escreve um programa que cadastre o nome, altura, o peso, o cpf e o sexo 
 * de algumas pessoas. Com os dados cadastrados em seguinda localizar uma
 * pessoas atraves do cpf e imprimir o seu IMC.
 * 
 * Obs.: o cadastro é continuo sem flag de parada!
 * 
*/

//Estrutra pessoa
struct Pessoa {
  string nome;
  double altura;
  double peso;
  char sexo;
  double cpf;
};

//constante para fixa o tamanho do vetor
const int tvetor = 5;

//Vetor com os registro das pessoas
Pessoa pessoa[tvetor];

//Calculo e try catch: tratamento de excessoes
double imc(double altura, double peso){

    try{
        return (peso/altura);
    }catch (int e){
        cout << "An exception occurred. Exception Nr. " << e << '\n';
    return 0;
  }

}


// validar se foi digitado corretamente s ou m
void validarSexo(Pessoa pessoa[], int i){
        while (pessoa[i].sexo !='h' && pessoa[i].sexo !='n' )
        {
            cout << "Informar sexo: h->homem ou m->mulher! ";
            cin >>pessoa[i].sexo;
        }
}

//validar nome
// validar se foi digitado corretamente s ou m
void validarNome(Pessoa pessoa[], int i){
        while (pessoa[i].nome == "")
        {
            cout << "Nome invalido! ";
            cin >>pessoa[i].sexo;
        }
}

//validar altura
void validarAltura(Pessoa pessoa[], int i){
        while (pessoa[i].altura <= 0 || pessoa[i].altura >5)
        {
            cout << "Valor invalido altura >0 e altura < 5: ";
            cin >>pessoa[i].altura;
        }
} 

//validar peso
void validarPeso(Pessoa pessoa[], int i){
        while (pessoa[i].peso <= 0 || pessoa[i].peso >200)
        {
            cout << "Valor invalido peso >0 e peso < 200: ";
            cin >>pessoa[i].peso;
        }
} 


//validar cpf: valida apenas o tamanho!
void validarCpf(Pessoa pessoa[], int i){
        while (pessoa[i].cpf <= 0)
        {
            cout << "Cpf invalido!";
            cin >>pessoa[i].cpf;
        }
} 


//procedimento para realizar busca por CPF
void buscarCpf(Pessoa pessoa[], double cpf){

    bool naoencontrou = true;

    if(cpf != 0 && cpf != NULL){
        for (int i = 0; i < tvetor; i++)
        {
            if(pessoa[i].cpf ==cpf){
                cout << "\n Massa Corporea: "<<setprecision (2) << fixed<<imc(pessoa[i].altura,pessoa[i].peso)<<" \n ";
                naoencontrou = false;
                break;
            }
        }
    }

    if(naoencontrou == true){
        cout<< "\n Cpf nao cadastrado!";
    }

}


int main()
{
    //variaveis
    double cpf = 0;
    cout << "\n .: Cadastrar Pessoa:. \n";

    //leitura dos dados
    //o cadastro é continuo sem flag de parada!
    for (int i = 0; i < tvetor; i++)
    {
        /* nome */
        cout << "Informar nome: ";
        cin >>pessoa[i].nome;
        validarNome(pessoa,i);

        /* altura */
        cout << "Informar altura: ";
        cin >>pessoa[i].altura;
        validarAltura(pessoa,i);

        /* peso */
        cout << "Informar peso: ";
        cin >>pessoa[i].peso;
        validarPeso(pessoa,i);

         /* sexo */
        cout << "Informar sexo[h/m]: ";
        cin >>pessoa[i].sexo;
        validarSexo(pessoa,i);

         /* cpf */
        cout << "Informar cpf: ";
        cin >>pessoa[i].cpf;
        validarCpf(pessoa,i);

    }

    //Busca  pessoa por cpf   
    cout << "\n .: Busca por cpf:. ";
    cout << "\n Inserir cpf:  ";
    cin >>cpf;
    buscarCpf(pessoa,cpf);

    return 0;
} 
 
 questao4.cpp 


#include <stdio.h>
#include <iostream>
#include <math.h>
#include <iomanip>
using namespace std;

/**
 * Turma: Terça - Noite
 * Disciplina: Introdução à programação I
 * Professor: Rachel Pernambuco
 * Aluno: Jamilli Vitória Oliveira 
 * Matricular: 201908105101
 * Data:15/05/2020
 * 
 * 4) Atividade: 
 * 4)Fazer um programa de cadastrados de usuario, onde deve conter os segintes  campos:
 *  nome
 *  cpf
 *  sexo
 *  telefone
 *  rg
 *  idade
 * 
 * Cadastro terminar quando vc determinar no sistema
 * O programa deve conter no minimo cadastro e buscar e a busca sera feria
 * pelo CPF do usuario cadastrado.
 * 
*/

//Estrutra pessoa
struct Pessoa {
  string nome;
  double telefone;
  double idade;
  char sexo;
  double cpf;
};

//constante para fixa o tamanho do vetor
const int tvetor = 5;

//Vetor com os registro das pessoas
Pessoa pessoa[tvetor];



// validar se foi digitado corretamente s ou m
void validarSexo(Pessoa pessoa[], int i){
        while (pessoa[i].sexo !='h' && pessoa[i].sexo !='n' )
        {
            cout << "Informar sexo: h->homem ou m->mulher! ";
            cin >>pessoa[i].sexo;
        }
}

//validar nome
// validar se foi digitado corretamente s ou m
void validarNome(Pessoa pessoa[], int i){
        while (pessoa[i].nome == "")
        {
            cout << "Nome invalido! ";
            cin >>pessoa[i].sexo;
        }
}

//validar altura
void validarIdade(Pessoa pessoa[], int i){
        while (pessoa[i].idade <= 0 || pessoa[i].idade >999)
        {
            cout << "Valor invalido idade >0 e idade < 999: ";
            cin >>pessoa[i].idade;
        }
} 

//validar peso
void validarTelefone(Pessoa pessoa[], int i){
        while (pessoa[i].telefone <= 0)
        {
            cout << "Valor telefone! ";
            cin >>pessoa[i].telefone;
        }
} 


//validar cpf: valida apenas o tamanho!
void validarCpf(Pessoa pessoa[], int i){
        while (pessoa[i].cpf <= 0)
        {
            cout << "Cpf invalido!";
            cin >>pessoa[i].cpf;
        }
} 


//procedimento para realizar busca por CPF
void buscarCpf(Pessoa pessoa[], double cpf){

    bool naoencontrou = true;

    if(cpf != 0 && cpf != NULL){
        for (int i = 0; i < tvetor; i++)
        {
            if(pessoa[i].cpf ==cpf){
                cout<<"\n Usuario Cadastrado!";
                cout<<" \n Nome: "<<pessoa[i].nome<<" \n";
                naoencontrou = false;
                break;
            }
        }
    }

    if(naoencontrou == true){
        cout<< "\n Cpf nao cadastrado!";
    }

}


int main()
{
    //variaveis
    double cpf;
    char flag;

    cout << "\n .:: Cadastrar Pessoa ::. \n";

    //leitura dos dados
    //o cadastro é continuo com flag de parada!
    for (int i = 0; i < tvetor; i++)
    {
        /* nome */
        cout << "Informar nome: ";
        cin >>pessoa[i].nome;
        validarNome(pessoa,i);

        /* idade */
        cout << "Informar idade: ";
        cin >>pessoa[i].idade;
        validarIdade(pessoa,i);

        /* Telefone */
        cout << "Informar Telefone: ";
        cin >>pessoa[i].telefone;
        validarTelefone(pessoa,i);

         /* sexo */
        cout << "Informar sexo[h/m]: ";
        cin >>pessoa[i].sexo;
        validarSexo(pessoa,i);

         /* cpf */
        cout << "Informar Cpf: ";
        cin >>pessoa[i].cpf;
        validarCpf(pessoa,i);


        /* flag de parada */
        cout << "Continuar s-sim ou x-sair: ";
        cin >>flag;

        if(flag=='x'){
            break;
        }

    }

    //Busca  pessoa por cpf   
    cout << "\n .: Busca por cpf:. ";
    cout << "\n Inserir cpf:  ";
    cin >>cpf;
    buscarCpf(pessoa,cpf);

    return 0;
} 
