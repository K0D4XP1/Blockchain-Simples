# Blockchain-Simples
O que é o Blockchain?

O conceito veio de Stuart Haber e W. Scott Stornetta em um artigo que básicamente falava sobre como carimbar(Autenticar) um documento digital.
Blockchain é uma lista contínua e crescente de registros, chamados de blocos, que estão conectados e seguros usando criptografia.

	Blockchain precisa de um DADO(tudo aquilo que de certa forma possa virar informação), UM HASH ANTERIOR E UM HASH(Assinatura do bloco OU uma "Impressão digital do bloco" Algo único).
	Primeiro bloco se chama bloco genesis, todos os blocos são conectados por criptografia.

Compreendendo Hash SHA256:

Imagine uma pessoa que tenha uma impressão digital diferente, praticamente todos temos impressôes digitais diferentes uns dos outros.
1 em 60,000,000 tem a mesma impressão digital. Como o hash a impressão digital pode ser utilizada para identificar pessoas.

Criado pela NSA o SHA256 utilizado para vários projetos relacionados a criptografia, inclusive é o mais usado em blockchain. um hash sempre tem 64 caracteres.

5 requisitos para um algoritmo de hash:

1. Sem retorno : Não pode fazer o caminho de volta do documento pro hash, com o hash você não tem como restaurar o documento.

2. Determinístico : mesmo hash em qualquer lugar, não importa onde seja a assinatura precisa ser a mesma.

3. Processamento rápido: PRECISA GERAR HASH DE FORMA RÁPIDA.

4. Efeito avalanche: Qualquer alteração no arquivo (documento) seja ela qual for o hash precisa mudar completamente, ou seja, por mais que a alteração seja pequena a mudança precisa ser grande, no hash por completo.

5. Deve suportar colisões: A colisão é algo inevitável, NO CASO DE COLISÕES NATURAIS precisa estar ciente do acontecimento e suportar ela, por exemplo, duas pessoas com o mesmo hash é rarissimo mas pode acontecer então o algoritmo deve estar preparado. 
	No caso de COLISÕES ARTIFICIAIS, ou seja, causadas por Crackers e Hackers, um ataque onde um hacker gera um documento com nome do proprietario diferente mas com mesmo hash do documento original, deve ser suportado porém neste caso é muito mais dificil.
  
Registros Imutáveis:

O bloco (REGISTRO) não pode mais ser alterado após ser incluido na cadeia, caso seja alterado irá invalidar todos os sucessores dele, pois a alteração mudaria o hash e coincidentemente alteraria o "HASH ANTERIOR" do próximo bloco invalidando ele e todos os outros.

Redes P2P Distribuídas:

Seriam vários computadores conectados, a rede é verificada constantemente para ver se há algo que corrompa a integridade dos blocos.
Caso haja alteração, seja ela por erro de do sistema ou por ataque hacker, As outras máquinas "avisam" e a maquina que possui o erro verifica com base nas outras cadeias e corrige o erro.
Para um ataque bem sucedido o hacker teria que alterar pelomenos mais de 50% das máquinas em segundos ou minutos dependendo da rede.
Não importa o meio em que esteja sendo distribuído, o importante é a integridade e a privacidade dos blocos.

Como mineração funciona:

Nonce - Responsável pelo processamento, ele dá maior flexibilidade, apartir do momento que o nonce é mudado o bloco recebe um hash difrerente...
Um bloco pode ter várias transações.
O hash é um número(por isso podem haver operações aritmeticas), ele é hexadecimal e pode ser composto por números de 0 a 9 e letras de A a F.
Sempre é possível converter um número hexadecimal para um numero decimal, ele é compacto pois pode representar números maiores usando menos bits(caracteries).
A = 10
B = 11
C = 12
D = 13
E = 14
F = 15
Num sistema hexadecimal cada digito pode ter um valor maior, visualmente ele é menor porém representa a mesma coisa.

<b>Tudo isto exemplificado em uma simples aplicação de blockchain</b>

→→→ [■□□□□□□□□□] 10%
→→→ [■■□□□□□□□□] 20%
→→→ [■■■□□□□□□□] 30%
→→→ [■■■■□□□□□□] 40%
→→→ [■■■■■□□□□□] 50%
→→→ [■■■■■■□□□□] 60%
→→→ [■■■■■■■□□□] 70%
→→→ [■■■■■■■■□□] 80%
→→→ [■■■■■■■■■□] 90%

