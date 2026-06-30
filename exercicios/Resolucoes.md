# Resoluções — Grupo 2: Operadores

> Arquivo complementar ao `Exercicios.md`.

---

## Operadores Aritméticos

**1.** Qual o resultado de `7 + 3 * 2`?

**Resposta: 13**

A multiplicação tem prioridade sobre a adição na ordem das operações. Portanto:
- Passo 1: `3 * 2 = 6`
- Passo 2: `7 + 6 = 13`

Se quisesse forçar a soma primeiro, seria necessário usar parênteses: `(7 + 3) * 2 = 20`.

---

**2.** Qual o resultado de `10 % 3`? O que o operador `%` representa?

**Resposta: 1**

O operador `%` é o **módulo** — ele retorna o **resto** da divisão inteira entre dois números.
- `10 ÷ 3 = 3` com resto `1`
- Portanto `10 % 3 = 1`

---

**3.** Escreva a expressão que calcula a área de um quadrado de lado 4.

**Resposta: `4 * 4` → 16**

A área de um quadrado é calculada pelo lado elevado ao quadrado. Em Python:
```python
lado = 4
area = lado * lado   # ou lado ** 2
print(area)          # 16
```

---

**4.** Qual o resultado de `2 ** 3`? O que o operador `**` representa?

**Resposta: 8**

O operador `**` é a **exponenciação**. `2 ** 3` significa 2 elevado à potência 3:
- `2 ** 3 = 2 × 2 × 2 = 8`

---

## Operadores Relacionais

**5.** As expressões são verdadeiras ou falsas?

| Expressão | Resultado | Justificativa |
|---|---|---|
| `10 > 7` | **True** | 10 é maior que 7. |
| `4 == 4.0` | **True** | Em Python, inteiro e float com o mesmo valor são considerados iguais. |
| `15 != 15` | **False** | 15 é igual a 15, portanto a comparação de "diferente" é falsa. |

---

**6.** Expressão que verifica se a nota é suficiente para aprovação (mínimo 6):

**Resposta:**
```python
nota >= 6
```

Se `nota = 7.5`, o resultado será `True` (aprovado). Se `nota = 5.0`, o resultado será `False` (reprovado).

---

**7.** Qual a saída do código?

```python
x = 8
print(x >= 10)   # False — 8 não é maior ou igual a 10
print(x != 8)    # False — 8 é igual a 8, então "diferente" é falso
print(x < 10)    # True  — 8 é menor que 10
```

**Saída:**
```
False
False
True
```

---

## Operadores Lógicos

**8.** As expressões são verdadeiras ou falsas?

| Expressão | Resultado | Justificativa |
|---|---|---|
| `(3 > 2) and (5 > 10)` | **False** | `3 > 2` é True, mas `5 > 10` é False. O `and` exige que **ambas** sejam verdadeiras. |
| `(3 > 2) or (5 > 10)` | **True** | `3 > 2` é True. O `or` exige que **pelo menos uma** seja verdadeira. |
| `not (3 > 2)` | **False** | `3 > 2` é True, e o `not` inverte para False. |

---

**9.** Condição para tirar a carteira de motorista:

**Resposta:**
```python
idade >= 18 and fez_exame == True
```

Ambas as condições precisam ser verdadeiras ao mesmo tempo, por isso usa-se o `and`. Exemplo completo:
```python
idade = 20
fez_exame = True

if idade >= 18 and fez_exame == True:
    print("Pode tirar a carteira!")
else:
    print("Não pode tirar a carteira.")
```

---

**10.** Qual a saída do código?

```python
a = True
b = False

print(a and b)   # False — True AND False = False
print(a or b)    # True  — True OR False  = True
print(not a)     # False — NOT True       = False
```

**Saída:**
```
False
True
False
```
