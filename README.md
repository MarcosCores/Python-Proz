# Python-Proz
Exercícios realizados na disciplina 'Fundamentos de Programação', ministrada no curso de Desenvolvimento de Sistemas da Escola Proz

<hr>

### **Conceitos Básicos de Python**

**Q1.** Execute os dois comandos: print('Olá\mundo!') e print('Olá mundo!'). Explique a diferença entre eles.
```
A diferença é que print('Olá\mundo!') irá fazer uma quebra de linha, ex:
Olá
mundo!

Enquanto print('Olá mundo!') continuará na mesma linha, ex:
Olá mundo!
```
**Q2.** Elabore um programa que permita a entrada de dois valores, x e y, troque seus  valores entre si e então exiba os novos resultados.
```
print("Digite o primeiro numero")
num1 = input()
print("Digite o segundo numero")
num2 = input()


print (num1, num2)


lugartemp = num1
num1 = num2
num2= lugartemp


print ("O valor invertido de num1 é", num1, "e o valor invertido de num2 é", num2)

```
**Q3.**  crie um programa para converter uma temperatura da escala Celsius para a escala Fahrenheit. A fórmula para conversão é Fahrenheit = ((Celsius * 9) / 5 ) + 32.
```
print("Digite a temperatura em Celsius")
C = input() #str


C= int(C)


F=((C * 9) / 5 ) + 32.




print ("A conversão de temperatura em graus Fahrenheit é", F,".")

```
### **Listas, Tuplas e Dicionários**

**Q1.** Crie uma tupla com os signos do zodíaco e exiba os valores dessa tupla em tela.
```
# Criando uma tupla com os signos do zodíaco
signos_zodiaco = ("Áries", "Touro", "Gêmeos", "Câncer", "Leão", "Virgem", "Libra", "Escorpião", "Sagitário", "Capricórnio", "Aquário", "Peixes")

# Exibindo os valores da tupla na tela
print("Signos do Zodíaco:")
for signo in signos_zodiaco:
    print(signo)
```
**Q2.** Crie um dicionário para armazenar as características de um animal de estimação. Exiba em tela as informações armazenadas nesse dicionário.
```
# Criando um dicionário com as características de um animal de estimação
animal_estimacao = {
    "Nome": "Bolt",
    "Espécie": "Cachorro",
    "Raça": "Labrador",
    "Idade": 5,
    "Peso": 30.5,
    "Cor": "Marrom"
}

# Exibindo as informações armazenadas no dicionário
print("Características do animal de estimação:")
for chave, valor in animal_estimacao.items():
    print(f"{chave}: {valor}")
```
**Q3.**  Desenvolva um programa que armazenará números reais numa lista. A seguir, encontre o menor elemento da lista e a sua posição (índice) dentro da lista, mostre esses valores em tela.
```
# Criando uma lista de números reais
numeros_reais = [4.5, 2.3, 7.8, 1.2, 9.0, 5.6]

# Encontrando o menor elemento da lista e sua posição (índice)
menor_valor = min(numeros_reais)
indice_menor_valor = numeros_reais.index(menor_valor)

# Exibindo os valores na tela
print(f"A lista de números reais é: {numeros_reais}")
print(f"O menor valor da lista é: {menor_valor}")
print(f"A posição (índice) do menor valor na lista é: {indice_menor_valor}")
```
**Q4.** Desenvolva um programa que possua duas listas A e B com 5 elementos cada e então troque seus elementos, de forma que a lista A ficará com os elementos da lista B e vice- versa.
```
# Definindo as listas A e B com 5 elementos cada
A = [1, 2, 3, 4, 5]
B = [6, 7, 8, 9, 10]

# Exibindo as listas antes da troca
print("Antes da troca:")
print("Lista A:", A)
print("Lista B:", B)

# Trocando os elementos das listas
A, B = B, A

# Exibindo as listas após a troca
print("\nApós a troca:")
print("Lista A:", A)
print("Lista B:", B)
```
### **Condicionais**

**Q1.** Elabore um programa que permita a entrada de um número inteiro e diga se ele é par ou ímpar.
```

```
**Q2.** Exercícios 5 e 6 da página 150 da Apostila.
```

```
**Q3.**  Elabore um programa que calcule quantas notas de 50, 10 e 1 são necessárias para se pagar uma conta cujo valor é fornecido.
```

```
### **Laços de Repetição**

**Q1.** Desenvolva um programa que calcule e exiba a diferença entre o maior e o menor elemento de uma lista denominada VALORES. Os valores da lista devem ser lidos.
```
def main():
    # Ler os valores da lista fornecidos pelo usuário
    valores = input("Digite os valores separados por espaço: ").split()
   
    # Converter os valores para inteiros
    valores = [int(valor) for valor in valores]
   
    # Encontrar o maior e o menor valor da lista
    maior_valor = max(valores)
    menor_valor = min(valores)
   
    # Calcular a diferença entre o maior e o menor valor
    diferenca = maior_valor - menor_valor
   
    # Exibir a diferença calculada
    print(f"A diferença entre o maior e o menor valor é: {diferenca}")


# Executar a função principal
if __name__ == "__main__":
    main()

```
**Q2.** Desenvolvam um programa que escreva na tela um número inicial específico até um número final determinado. Os números inicial e final devem ser informados pelo usuário.
```
def main():
    # Solicitar ao usuário que insira o número inicial
    numero_inicial = int(input("Digite o número inicial: "))
   
    # Solicitar ao usuário que insira o número final
    numero_final = int(input("Digite o número final: "))
   
    # Escrever na tela os números do inicial até o final, incluindo ambos
    for numero in range(numero_inicial, numero_final + 1):
        print(numero)


# Executar a função principal
if __name__ == "__main__":
    main()

```
**Q3.**  Desenvolvam um programa que leia valores inteiros e encontre o maior e o menor deles. A leitura deve terminar se o usuário digitar zero (0).
```
def main():
    # Inicializar as variáveis maior e menor com None
    maior_valor = None
    menor_valor = None
   
    while True:
        # Ler o valor inteiro do usuário
        valor = int(input("Digite um valor inteiro (0 para terminar): "))
       
        # Verificar se o valor é zero para terminar a leitura
        if valor == 0:
            break
       
        # Atualizar maior e menor valor
        if maior_valor is None or valor > maior_valor:
            maior_valor = valor
        if menor_valor is None or valor < menor_valor:
            menor_valor = valor
   
    # Verificar se foram digitados valores (maior_valor e menor_valor não são None)
    if maior_valor is not None and menor_valor is not None:
        print(f"O maior valor digitado foi: {maior_valor}")
        print(f"O menor valor digitado foi: {menor_valor}")
    else:
        print("Nenhum valor foi digitado.")


# Executar a função principal
if __name__ == "__main__":
    main()


```
### **Validação de Dados, Funções e Módulos**

**Q1.** Faça um programa que leia e valide as seguintes informações:
* Nome: maior que 2 caracteres;
* Idade: entre 0 e 100;
* Salário: maior que zero;
* Sexo: 'f' ou 'm';
* Estado Civil: 's', 'c', 'v', 'd';
```

```
**Q2.** Crie um módulo que faça o cálculo da média aritmética das notas das Provas 1, Prova 2 e Prova 3 de um aluno. Este módulo deve ser importado (chamado) por meio de outro programa.
```

```
**Q3.**  Crie um módulo que faça o cálculo do IMC (Índice de Massa Corporal). O programa que for fazer a chamada desse módulo deverá classificar, através do valor retornado, se a pessoa está ou não acima do peso. A fórmula do IMC é: IMC = peso / altura².
```

```
**Q4.** Desenvolva um programa que possua uma função chamada de pagamento. Ele deverá receber as horas trabalhadas e o valor das horas. No final, o valor a ser pago para o trabalhador deverá ser retornado pela função e depois exibido na tela.
```

```
