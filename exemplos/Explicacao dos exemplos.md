# Explicação dos Exemplos — `exemplos_operadores.py`

Este arquivo explica, passo a passo, cada um dos 6 exemplos presentes no arquivo `exemplos_operadores.py`.

---

## Operadores Aritméticos

### Exemplo 1 — Troco na compra

```python
valor_pago   = 50.00
valor_compra = 37.50
troco = valor_pago - valor_compra
```

**O que faz:** Simula o cálculo de troco em um caixa de loja. O operador `-` (subtração) é aplicado entre o valor que o cliente entregou e o valor da compra, resultando no valor a ser devolvido.

**Por que usar:** Demonstra o uso mais básico da subtração em um contexto real e cotidiano. O resultado é formatado com `:.2f` para exibir exatamente duas casas decimais, como em um sistema de caixa real.

---

### Exemplo 2 — Divisão de conta e gorjeta

```python
gorjeta    = conta_total * (percentual_gorjeta / 100)
total      = conta_total + gorjeta
por_pessoa = total / num_amigos
```

**O que faz:** Calcula o valor que cada pessoa deve pagar ao dividir uma conta de restaurante, já incluindo a gorjeta.

**Por que usar:** Combina três operadores aritméticos em sequência (`*`, `/`, `+`), mostrando que eles podem ser encadeados em uma situação prática. Também ilustra a precedência: a divisão dentro do parêntese é resolvida primeiro.

---

## Operadores Relacionais

### Exemplo 3 — Controle de acesso por idade

```python
idade = 16
print(f"Tem 18 anos?         {idade == 18}")
print(f"É menor de idade?    {idade < 18}")
print(f"Pode entrar (18+)?   {idade >= 18}")
```

**O que faz:** Verifica se uma pessoa tem permissão de entrar em um local com restrição de idade, usando três comparações diferentes sobre a mesma variável.

**Por que usar:** Mostra na prática como `==`, `<` e `>=` retornam `True` ou `False`, e como esse resultado pode ser usado diretamente em um `if` para tomar uma decisão no programa.

---

### Exemplo 4 — Aprovação escolar

```python
nota_aluno  = 7.5
nota_minima = 6.0
print(f"Aprovado?       {nota_aluno >= nota_minima}")
print(f"Reprovado?      {nota_aluno < nota_minima}")
print(f"Nota exata mín? {nota_aluno == nota_minima}")
```

**O que faz:** Compara a nota de um aluno com a nota mínima de aprovação usando `>=`, `<` e `==`.

**Por que usar:** Reforça que operadores relacionais funcionam também com números decimais (`float`), não apenas inteiros, e que o resultado sempre será `True` ou `False` — nunca um número.

---

## Operadores Lógicos

### Exemplo 5 — Aprovação de empréstimo (AND)

```python
renda_suficiente = True
bom_historico    = False
aprovado = renda_suficiente and bom_historico
```

**O que faz:** Simula a lógica de aprovação de crédito de um banco: o empréstimo só é aprovado se **as duas** condições forem verdadeiras ao mesmo tempo.

**Por que usar:** Demonstra o comportamento do `and` de forma clara — mesmo que `renda_suficiente` seja `True`, o resultado final é `False` porque `bom_historico` é `False`. O `and` é restritivo: precisa de tudo verdadeiro.

---

### Exemplo 6 — Levar casaco (OR) e dia de folga (NOT)

```python
levar_casaco = esta_frio or esta_chovendo
folga        = not dia_de_trabalho
```

**O que faz:** Usa o `or` para decidir se vale a pena levar um casaco (basta uma das condições ser verdadeira) e o `not` para inverter se é um dia de trabalho em um dia de folga.

**Por que usar:** Apresenta `or` e `not` juntos no mesmo exemplo, mostrando o contraste entre os dois: o `or` combina condições (basta uma ser verdadeira), enquanto o `not` simplesmente inverte o valor lógico de uma única condição.
