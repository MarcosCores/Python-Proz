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
# Solicita ao usuário que insira um número inteiro
numero = int(input("Digite um número inteiro: "))


# Verifica se o número é par ou ímpar
if numero % 2 == 0:
    print(f"O número {numero} é par.")
else:
    print(f"O número {numero} é ímpar.")

```
**Q2.** Exercícios 5 e 6 da página 150 da Apostila.
```
def calcular_inss(salario_bruto):
    if salario_bruto <= 1693.72:
        inss = salario_bruto * 0.08
    elif salario_bruto <= 2822.90:
        inss = (1693.72 * 0.08) + ((salario_bruto - 1693.72) * 0.09)
    elif salario_bruto <= 5645.80:
        inss = (1693.72 * 0.08) + ((2822.90 - 1693.72) * 0.09) + ((salario_bruto - 2822.90) * 0.11)
    else:
        # Para salários acima do teto do INSS, a contribuição é calculada sobre o teto.
        inss = (1693.72 * 0.08) + ((2822.90 - 1693.72) * 0.09) + ((5645.80 - 2822.90) * 0.11)


    return inss


def calcular_salario_liquido(salario_bruto):
    inss = calcular_inss(salario_bruto)
    salario_liquido = salario_bruto - inss
    return salario_liquido


# Entrada do usuário
salario_bruto = float(input("Digite o valor do salário bruto: R$ "))


# Cálculos
inss = calcular_inss(salario_bruto)
salario_liquido = calcular_salario_liquido(salario_bruto)


# Exibição dos resultados
print(f"Salário Bruto: R$ {salario_bruto:.2f}")
print(f"Contribuição ao INSS: R$ {inss:.2f}")
print(f"Salário Líquido: R$ {salario_liquido:.2f}")

```
**Q3.**  Elabore um programa que calcule quantas notas de 50, 10 e 1 são necessárias para se pagar uma conta cujo valor é fornecido.
```
# Solicita o valor da conta ao usuário
valor = int(input("Digite o valor da conta: "))




# Calcula a quantidade de notas de 50, 10 e 1
notas_50 = valor // 50
valor_restante = valor % 50




notas_10 = valor_restante // 10
valor_restante = valor_restante % 10




notas_1 = valor_restante // 1




# Exibe o resultado
print(f"Para pagar a conta de {valor} reais, você precisará de:")
print(f"{notas_50} notas de 50 reais")
print(f"{notas_10} notas de 10 reais")
print(f"{notas_1} notas de 1 real")





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
def validar_nome(nome):
    return len(nome) > 2

def validar_idade(idade):
    return 0 <= idade <= 100

def validar_salario(salario):
    return salario > 0

def validar_sexo(sexo):
    return sexo in ['f', 'm']

def validar_estado_civil(estado_civil):
    return estado_civil in ['s', 'c', 'v', 'd']

# Programa principal
def main():
    while True:
        nome = input("Digite o nome (maior que 2 caracteres): ")
        if validar_nome(nome):
            break
        print("Nome inválido!")

    while True:
        try:
            idade = int(input("Digite a idade (entre 0 e 100): "))
            if validar_idade(idade):
                break
            print("Idade inválida!")
        except ValueError:
            print("Por favor, insira um número válido!")

    while True:
        try:
            salario = float(input("Digite o salário (maior que zero): "))
            if validar_salario(salario):
                break
            print("Salário inválido!")
        except ValueError:
            print("Por favor, insira um número válido!")

    while True:
        sexo = input("Digite o sexo ('f' ou 'm'): ").lower()
        if validar_sexo(sexo):
            break
        print("Sexo inválido!")

    while True:
        estado_civil = input("Digite o estado civil ('s', 'c', 'v', 'd'): ").lower()
        if validar_estado_civil(estado_civil):
            break
        print("Estado civil inválido!")

    print("\n--- Dados Validados com Sucesso ---")
    print(f"Nome: {nome}\nIdade: {idade}\nSalário: R${salario:.2f}\nSexo: {sexo}\nEstado Civil: {estado_civil}")

if __name__ == "__main__":
    main()

```
**Q2.** Crie um módulo que faça o cálculo da média aritmética das notas das Provas 1, Prova 2 e Prova 3 de um aluno. Este módulo deve ser importado (chamado) por meio de outro programa.
```
def calcular_media(p1, p2, p3):
    return (p1 + p2 + p3) / 3

def main():
    print("--- Cálculo da Média Aritmética ---")
    try:
        p1 = float(input("Digite a nota da Prova 1: "))
        p2 = float(input("Digite a nota da Prova 2: "))
        p3 = float(input("Digite a nota da Prova 3: "))
        media = calcular_media(p1, p2, p3)
        print(f"A média aritmética é: {media:.2f}")
    except ValueError:
        print("Por favor, insira valores válidos.")

if __name__ == "__main__":
    main()

```
**Q3.**  Crie um módulo que faça o cálculo do IMC (Índice de Massa Corporal). O programa que for fazer a chamada desse módulo deverá classificar, através do valor retornado, se a pessoa está ou não acima do peso. A fórmula do IMC é: IMC = peso / altura².
```
def calcular_imc(peso, altura):
    return peso / (altura ** 2)

def classificar_imc(imc):
    if imc < 18.5:
        return "Abaixo do peso"
    elif 18.5 <= imc < 24.9:
        return "Peso normal"
    elif 25 <= imc < 29.9:
        return "Sobrepeso"
    elif 30 <= imc < 34.9:
        return "Obesidade grau 1"
    elif 35 <= imc < 39.9:
        return "Obesidade grau 2"
    else:
        return "Obesidade grau 3"

def main():
    print("--- Cálculo do IMC ---")
    try:
        peso = float(input("Digite o peso (em kg): "))
        altura = float(input("Digite a altura (em metros): "))
        imc = calcular_imc(peso, altura)
        classificacao = classificar_imc(imc)
        print(f"Seu IMC é: {imc:.2f}")
        print(f"Classificação: {classificacao}")
    except ValueError:
        print("Por favor, insira valores válidos.")

if __name__ == "__main__":
    main()

```
**Q4.** Desenvolva um programa que possua uma função chamada de pagamento. Ele deverá receber as horas trabalhadas e o valor das horas. No final, o valor a ser pago para o trabalhador deverá ser retornado pela função e depois exibido na tela.
```
def calcular_pagamento(horas_trabalhadas, valor_hora):
    return horas_trabalhadas * valor_hora

def main():
    print("--- Cálculo do Pagamento ---")
    try:
        horas = float(input("Digite o número de horas trabalhadas: "))
        valor_hora = float(input("Digite o valor por hora (R$): "))
        total = calcular_pagamento(horas, valor_hora)
        print(f"Valor total a ser pago: R${total:.2f}")
    except ValueError:
        print("Por favor, insira valores válidos.")

if __name__ == "__main__":
    main()

```
