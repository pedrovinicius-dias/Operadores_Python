# Aplicações Práticas — Operadores Aritméticos, Relacionais e Lógicos

> Este material complementa a pesquisa do Grupo 2, mostrando como os três tipos de operadores aparecem **combinados** em situações reais de programação — não mais isolados como nos exemplos básicos, mas trabalhando juntos para resolver um problema completo.

---

## 1. E-commerce: Carrinho de compras com frete grátis e cupom

**Contexto:** sistemas de loja virtual precisam calcular o total da compra, verificar se o cliente tem direito a frete grátis e aplicar um cupom de desconto — tudo na mesma regra de negócio.

```python
valor_carrinho = 180.00
peso_kg = 2.5
cliente_premium = True
cupom_valido = "DESC10"

# Aritméticos: calcula frete e desconto
frete = 0 if valor_carrinho >= 150 else peso_kg * 8
desconto = valor_carrinho * 0.10 if cupom_valido == "DESC10" else 0
total = valor_carrinho - desconto + frete

# Relacionais + Lógicos: define se o pedido é prioritário
pedido_prioritario = (valor_carrinho > 100) and (cliente_premium or peso_kg < 1)

print(f"Frete: R$ {frete:.2f}")
print(f"Desconto: R$ {desconto:.2f}")
print(f"Total a pagar: R$ {total:.2f}")
print(f"Entrega prioritária? {pedido_prioritario}")
```

**O que acontece:** o operador aritmético (`*`, `-`, `+`) calcula valores; o relacional (`>=`, `>`, `<`) decide regras de corte (frete grátis acima de R$150); o lógico (`and`, `or`) combina duas condições de negócio diferentes para liberar a entrega prioritária.

---

## 2. Jogos: Sistema de dano e condição de vitória

**Contexto:** em qualquer jogo simples, o personagem perde vida (aritmética), o jogo verifica se ele ainda está vivo (relacional) e decide se houve vitória combinando vida e tempo restante (lógica).

```python
vida_inicial = 100
dano_recebido = 35
vida_atual = vida_inicial - dano_recebido

tem_escudo = True
inimigos_derrotados = 5
tempo_restante = 12  # segundos

# Relacional: o personagem ainda está vivo?
esta_vivo = vida_atual > 0

# Lógico: condição de vitória — só vence se estiver vivo
# E (derrotou todos os inimigos OU o tempo acabou com escudo ativo)
venceu = esta_vivo and (inimigos_derrotados >= 5 or (tempo_restante <= 0 and tem_escudo))

print(f"Vida atual: {vida_atual}")
print(f"Está vivo? {esta_vivo}")
print(f"Venceu a fase? {venceu}")
```

**O que acontece:** a subtração calcula o dano acumulado; `>` verifica se a vida chegou a zero; `and`/`or` montam a regra completa de vitória, que tem mais de uma forma de ser alcançada.

---

## 3. Saúde: Triagem simples de pronto-atendimento

**Contexto:** sistemas de triagem hospitalar classificam o paciente combinando medições (aritmética não é usada aqui diretamente, mas a comparação de múltiplos sinais vitais é constante) com regras lógicas de urgência.

```python
temperatura = 39.2       # °C
saturacao_oxigenio = 91  # %
pressao_sistolica = 85   # mmHg

febre_alta = temperatura >= 39.0
saturacao_baixa = saturacao_oxigenio < 92
pressao_baixa = pressao_sistolica < 90

# Combina três sinais: é urgente se PELO MENOS DOIS indicadores estiverem alterados
indicadores_alterados = sum([febre_alta, saturacao_baixa, pressao_baixa])
urgente = indicadores_alterados >= 2

print(f"Febre alta? {febre_alta}")
print(f"Saturação baixa? {saturacao_baixa}")
print(f"Pressão baixa? {pressao_baixa}")
print(f"Classificar como urgente? {urgente}")
```

**O que acontece:** cada sinal vital vira uma condição booleana via operador relacional; a soma aritmética dos `True`/`False` (Python trata `True` como 1 e `False` como 0) conta quantos indicadores estão alterados; o relacional final decide a urgência.

---

## 4. IoT: Termostato inteligente

**Contexto:** dispositivos domésticos (ar-condicionado, termostatos) tomam decisões automáticas comparando sensores e combinando preferências do usuário.

```python
temperatura_atual = 29.5
temperatura_desejada = 23.0
modo_economia = True
horario_atual = 14  # 24h

diferenca = temperatura_atual - temperatura_desejada  # aritmético

precisa_resfriar = diferenca > 1.5            # relacional
horario_de_pico = 18 <= horario_atual <= 21   # relacional encadeado

# Liga o ar apenas se precisar resfriar E (não estiver em modo economia OU não for horário de pico)
ligar_ar_condicionado = precisa_resfriar and (not modo_economia or not horario_de_pico)

print(f"Diferença de temperatura: {diferenca:.1f}°C")
print(f"Ligar ar-condicionado? {ligar_ar_condicionado}")
```

**O que acontece:** a subtração mede o quanto a temperatura está fora do desejado; comparações relacionais (inclusive encadeadas, `18 <= horario_atual <= 21`) identificam o horário de pico; `not` inverte as preferências para criar a regra final de economia de energia.

---

## 5. Finanças: Aprovação de cartão de crédito

**Contexto:** instituições financeiras usam fórmulas (aritmética) para calcular o score e depois aplicam várias regras (relacional + lógico) para aprovar ou não um crédito.

```python
renda_mensal = 4500.00
divida_mensal = 1200.00
score_credito = 720
tem_restricao = False

comprometimento_renda = (divida_mensal / renda_mensal) * 100  # aritmético, em %

renda_aprovada = renda_mensal >= 2000
score_aprovado = score_credito >= 650
comprometimento_ok = comprometimento_renda <= 30

aprovado = renda_aprovada and score_aprovado and comprometimento_ok and not tem_restricao

print(f"Comprometimento de renda: {comprometimento_renda:.1f}%")
print(f"Crédito aprovado? {aprovado}")
```

**O que acontece:** a divisão e multiplicação calculam o percentual de renda comprometida; cada regra do banco vira uma comparação relacional; o `and` exige que **todas** sejam verdadeiras, e o `not` bloqueia o crédito caso exista qualquer restrição cadastral.

---

## Por que combinar os três tipos importa

| Sozinho | Combinado |
|---|---|
| Aritmético calcula um número | Esse número alimenta uma comparação |
| Relacional gera um `True`/`False` isolado | Vários `True`/`False` se combinam com `and`/`or`/`not` |
| Lógico junta condições soltas | A condição final decide uma ação real do sistema (aprovar, alertar, ligar, bloquear) |

Em praticamente todo sistema real — de um app de delivery a um sistema bancário — os três tipos de operadores trabalham em conjunto: **a aritmética gera os números, a relacional transforma números em decisões binárias, e a lógica combina essas decisões em uma regra de negócio final.**

---

## Exercício de fixação

Tente prever a saída antes de rodar:

```python
saldo = 250.00
limite_cheque_especial = 100.00
valor_compra = 320.00

saldo_disponivel = saldo + limite_cheque_especial
compra_permitida = valor_compra <= saldo_disponivel and valor_compra > 0

print(compra_permitida)
```

<details>
<summary>Resposta</summary>

`saldo_disponivel = 350.00`. Como `320 <= 350` é `True` e `320 > 0` também é `True`, o resultado de `compra_permitida` é **`True`**.
</details>
