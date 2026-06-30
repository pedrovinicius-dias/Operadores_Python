 Roteiro bala:Operadores em Python

Tempo estimado: 12–15 minutos | 4 Apresentadores | 

EU tive preguiça de fazer para cada exemplo, entao fiquem sabendo que vcs teram que explicar o codigo de exemplo direito

jesso Introdução & Operadores Aritméticos (Duração estimada: ~3,5 min)

Apresentador 1: "Bom dia uzubesquistao,  Meu nome é Gilson, um dono muito orgulhoso de um xeon que sempre passa dos 70(graus), foi Deus que me deu."


jesso "Se você começou a estudar progamaçao, achando que programar era criar inteligências artificiais utópicas para dominar o mundo, por que voce achou isso. Programar esta mais proxima da experiencia de conversar com um americano, sem saber ingles. Hoje, vamos destrinchar as leis da física da programação: os operadores Aritméticos, Relacionais e Lógicos."

CONCEITO "Cientificamente falando, como aponta a nossa pesquisa, operadores são símbolos que instruem o compilador ou interpretador a realizar operações matemáticas, lógicas e de comparação específicas. Eles são os verbos do código. Sem eles, as variáveis são só dados tristes e isolados na memória RAM."

OPERADORES ARITMÉTICOS "bem, os Aritméticos. No Python, temos os clássicos: + (Adição), - (Subtração), * (Multiplicação) e / (Divisão). Mas a nossa pesquisa destaca dois que confundem bastante: o % (Módulo, que é o resto da divisão) e o  (Exponenciação)."

jesso: "A ordem de prioridade aqui segue a escola: primeiro parênteses, depois exponenciação, multiplicação ou divisão, e só no fim soma ou subtração. nao tem nem como falhar aqui."

CÓDIGO REAL - Exemplo 1 e 2 

jesso: "Olha os exemplos práticos do nosso código. Primeiro, calculando o troco em uma compra comercial simples de balcão:"

Python
valor_pago = 50.00
valor_compra = 37.50
troco = valor_pago - valor_compra  # Subtração básica
print(f"Troco: R$ {troco:.2f}")     # R$ 12.50
jesso: "aqui vemos um exemplo mais complicado: dividir a conta do restaurante entre 4 amigos aplicando os 10% da gorjeta. Olha a matemática encadeada respeitando as prioridades:"

Python
conta_total = 120.00
num_amigos = 4
percentual_gorjeta = 10
gorjeta = conta_total * (percentual_gorjeta / 100)
total = conta_total + gorjeta
por_pessoa = total / num_amigos
print(f"Cada amigo paga: R$ {por_pessoa:.2f}")  # R$ 33.00
ANALOGIA DA PIZZA "Para entender o Módulo (%), pensa que você pediu uma pizza de 10 pedaços para 3 pessoas. A divisão normal daria dízima periódica. Mas se usarmos a divisão inteira 10 // 3, o Python diz: 'Cada um come 3 pedaços inteiros'. E se jogarmos no Módulo, 10 % 3, o resultado é 1. O módulo é esse 1 pedaço que sobrou na caixa e vai gerar uma briga generalizada."

jesso: "Agora, se você quer ver o computador sair da matemática e começar a julgar a sua vida, eu passo a bola para o Apresentador 2."


Apresentador 2 Operadores Relacionais  (Duração estimada: ~3,5 min)

(Apresentador 2 surge apontando para a tela, expressão julgadora. Zoom rápido).

Apresentador 2: "Calcular o preço de um lanche é moleza. Eu quero ver é quando o sistema precisa olhar para os seus dados e decidir se você tem direito a algo ou não. E e ai que usamos os Operadores Relacionais."

CONCEITO SEGUNDO A PESQUISA "Como estabelecido no nosso referencial científico, os operadores relacionais são usados para fazer comparações entre valores ou expressões do mesmo tipo. Eles olham o lado esquerdo, olham o lado direito e devolvem o que viram, binária: ou é True (Verdadeiro) ou é False (Falso). O tipo de dado final é sempre lógico."

Apresentador 2: "Na hierarquia de execução do Python, gravem isso : os cálculos matemáticos são feitos primeiro, e o julgamento relacional vem por último. Os símbolos oficiais que vocês encontram na tabela da nossa pesquisa são: == (Igual a), != (Diferente de), >(maior que), <(menor que), >=(maior ou igual a), e <=(menor ou igual a)."

O PERIGO DOS DOIS IGUAIS "Aqui mora o erro clássico. Um único sinal de igual (=) é atribuição, serve para guardar um dado. Dois sinais de igual (==) é uma comparação. Se você digitar meu_saldo = 1000000, você está forçando uma realidade alternativa no sistema. Se você digitar meu_saldo == 1000000, o Python vai olhar o seu extrato e responder: False."


Apresentador 2: "A analogia perfeita é o segurança de uma festa ou de um brinquedo de parque. Ele olha o seu RG e roda a linha de código do Nosso Exemplo 3:"

Python
idade = 16
print(f"Maior de idade? {idade >= 18}")  # Vai printar: False
Apresentador 2: "Ou o sistema da nossa própria faculdade aplicando a média mínima de aprovação, que é o Exemplo 4 do grupo:"

Python
nota_aluno = 7.5
nota_minima = 6.0
print(f"Aprovado? {nota_aluno >= nota_minima}")  # True
[EXERCÍCIO DO ARQUIVO] "Para exercitar os neurônios de quem tá assistindo, vamos puxar a Questão 5 do nosso arquivo Exercicios.md. Responda rápido mentalmente: 4 == 4.0 e 15 != 15. O que o Python responde? (Pausa dramática de 2 segundos). O Python responde True para a primeira, porque o valor numérico é idêntico mesmo um sendo float, e False para a segunda, porque 15 é igual a 15, então dizer que é diferente é uma mentira. Se você errou essa, sinto muito."

Apresentador 2: "Mas o mundo não é feito de uma comparação isolada. Para decisões complexas de verdade, o buraco é mais embaixo."


Apresentador 3  Operadores Lógicos (Duração estimada: ~3,5 min)


Apresentador 3: "Pois é. A vida real não é um morango feito de uma condição só. E se o sistema do banco precisar checar múltiplos fatores antes de liberar um dinheiro? É aqui que entra os Operadores Lógicos."

CONCEITO & TABELA VERDADE "A nossa pesquisa científica mostra que os operadores lógicos servem para avaliar dados quando há necessidade de fazer mais de uma comparação ao mesmo tempo. Eles recebem valores booleanos de entrada e cospem um booleano de saída. Em Python, eles são escritos por extenso, em inglês: and, or e not."

ANALOGIA CIENTÍFICA DO GRUPO "Se formos buscar a analogia contida no nosso relatório científico, pense em interruptores de luz. Se você ligar dois interruptores em série (um dependendo do outro em linha reta), a luz só acende se o primeiro E o segundo estiverem ligados. Isso é o and. Se eles estiverem em paralelo, caminhos separados, basta um estar ligado para a luz acender. Isso é o or. E o not é aquele interruptor invertido de fábrica: se você liga, ele apaga a luz."


Apresentador 3: "Olha como o Exemplo 5 simula a rigidez de uma aprovação de crédito bancário. O and é extremamente exigente, ele precisa que todas as condições sejam simultaneamente verdadeiras:"

Python
renda_suficiente = True
bom_historico = False
aprovado = renda_suficiente and bom_historico
print(f"Empréstimo aprovado? {aprovado}")  # Retorna: False
Apresentador 3: "Mesmo você sendo rico, se tiver o nome sujo, o and te rejeita. Agora veja o Exemplo 6, usando o or (que aceita qualquer negócio) e o not (o rebelde que inverte os estados lógicos):"

Python
esta_frio = False
esta_chovendo = True
dia_de_trabalho = True

levar_casaco = esta_frio or esta_chovendo  # True! Porque está chovendo.
folga = not dia_de_trabalho                 # False! Se trabalha, não é folga.
Apresentador 3: "Perfeito. Mas agora você deve estar se perguntando: como essas três forças da natureza trabalham juntas em um software comercial de verdade? Deixo vocês com o mash que vai falar sobre aplicações práticas."



Apresentador 4 Aplicações Práticas & Conclusão (Duração estimada: ~4 min)


Apresentador 4: "assim como em um jogo de futebol, na progamaçao nada e definido por apenas 1 elemento, mas a junçao deles. A mágica acontece quando o eha uma uniao estavel. Nós documentamos o caso real de um grande E-commerce."

DEMONSTRAÇÃO DO CÓDIGO DO E-COMMERCE

Apresentador 4: "Acompanhem comigo a estrutura desse algoritmo que roda por trás de quase toda loja virtual que você gasta seu salário:"

Python
valor_carrinho = 180.00
peso_kg = 2.5
cliente_premium = True
cupom_valido = "DESC10"

# 1. Os Aritméticos calculam os valores financeiros
frete = 0 if valor_carrinho >= 150 else peso_kg * 8
desconto = valor_carrinho * 0.10 if cupom_valido == "DESC10" else 0
total = valor_carrinho - desconto + frete

# 2. Relacionais e Lógicos combinados ditam a regra de negócio
pedido_prioritario = (valor_carrinho > 100) and (cliente_premium or peso_kg < 1)
Apresentador 4: "Perceberam o fluxo de dados? A aritmética gera os números brutos, os relacionais pegam esses números e transformam em pacotes de verdadeiro ou falso, e a lógica envelopa tudo isso para tomar a decisão final da empresa. É assim que o aplicativo de entrega calcula sua taxa, o banco decide se bloqueia seu cartão e os jogos processam se o seu personagem tomou dano ou não."

