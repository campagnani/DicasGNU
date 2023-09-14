# Dicas úteis para operar o sistema operacional GNU

<div style="text-align: right;">Thalles Oliveira Campagnani</div>
<div style="text-align: right;">Engenheiro Mecatrônico / CEFET-MG</div>
<div style="text-align: right;">Mestrando em Ciências e Técnicas Nucleares no Departamento de Engenharia Nuclear / UFMG</div>




## Atalhos para abrir o terminal

O terminal é uma importante ferramenta para operar o sistema operacional GNU, logo mais vamos entender o porquê.
Nada de medo da tela preta! Vamos logo aprender a abrir ele:

#### Abrir o emulador de terminal na interface gráfica:

| Ctrl + Alt + t |
|---|
| Já abre logado no seu usuário.|
| Abre direto no diretório do usuário: /home/nome_do_usuario |
| Nem todos computadores têm esse atalho configurado. |



| F4 |
|---|
|Só funciona no gerenciador de arquivos!! |
|Também logado no seu usuário.|
|Abre direto na pasta que você estava no gerenciador de arquivos.|



|Shift + F4|
|---|
|A diferença é que em alguns gerenciador de arquivos o comando anterior abre o |
|emulador de terminal acoplado ao gerenciador de arquivos, e este abre em uma janela separada.|
|Já outros não existe esse atalho, e o comando anterior abre direto em uma janela separada.|


#### Abrir o terminal no ttyX (tela preta):
|Ctrl + Alt + Fx|
|---|
|Fx pode ser F1, F2, F3 F4, F5, F6 ou F7|
|F1 abre o tty1, e assim sucessivamente|
|Geralmente no tty1 ou tty7 se encontra a interface gráfica, e o restante são tty disponíveis para ser usados.|
|Para voltar a interface gráfica basta usar o atalho com F1 ou F7.|
|Muito útil para resolver problemas quando a interface gráfica está inacessível.|







## Função das teclas do teclado no terminal (e atalhos)


Aprenda a navegar pela linha de comandos sem passar raiva. Geralmente estamos acostumados a usar o mouse para controlar o cursor, selecionar palavras, etc. E estamos acostumados a editar textos. Na linha de comandos do terminal não iremos conseguir usar o mouse e não estamos editando um texto, então algumas teclas tem até outras funções, como a seta para cima e para baixo. Então vamos lá:


|Tecla|Função|
|-|-|
|SetaDireita|Obviamente move o cursor uma posição para direita.|
|SetaEsquerda|Obviamente move o cursor uma posição para esquerda.|
|SetaCima|Não obviamente, mas move para o último comando executado (recua no histórico de comandos)|
|SetaBaixo|Avança do histórico de comandos.|

Lembre-se: você está em uma linha de comandos (e não um texto), logo só existe 
uma dimensão (sentido esquerda-direita), então as teclas cima-baixo servem para navegar no 
histórico de comandos.


|Atalhos Setas|Função|
|-|-|
|Ctrl + SetaEsquerda|Recua o cursor para o começo de uma palavra, ou palavra anterior.|
|Ctrl + SetaDireta|Avança o cursor para o começo da próxima palavra.|

Nada de ficar segurando SetaEsquerda/Direita!!! Use Ctrl + Seta.


|Tecla|Função|
|-|-|
|HOME|Move o cursor para o início da linha de comandos
|END|Move o cursor para o final da linha de comandos
|PageUp|Vai para o primeiro comando salvo no histórico (mais antigo).
|PageDown|Vai para o último comando salvo no histórico (mais novo).

|Tecla|Função|
|-|-|
|BackSpace|Apaga o caractere anterior ao cursor.
|Del|Apaga o caractere em cima do cursor.
|Alt + BackSpace|Apaga a palavra anterior ao cursor.
|Ctrl + Del|Apaga a palavra na frente do cursor.

Nada de ficar segurando BackSpace!!

|Tecla|Função|
|-|-|
|TAB|Completa a palavra que você está digitando (Somente se for única opção)|
|TAB TAB|(TAB TAB significa pressionar duas vezes consecutivas)|
||Mostra as possíveis opções de completar a palavra que você está digitando. (Somente se existir 2 ou mais opções)
||Se existir somente uma opção ele vai completar.
||Se não existir ele não vai fazer nada (talvez faça um barulho do tipo beep)





## Comandos básicos (na verdade programas)

O sistema operacional GNU (Gnu is Not Unix) é um clone do sistema operacional Unix feito por hackers (e seu nome é logicamente uma ironia feito pelos mesmos).

O shell padrão do GNU é o BASH (Bourne-Again SHell) que é um clone do Bourne shell, que era o shell padrão do Unix na sua versão 7 (e logicamente seu nome também é uma ironia).

Isso significa que quem irá interpretar tudo que você digitar na linha de comandos será o Bash. O Bash tem uma sintaxe de comandos própria que você pode se aprofundar pesquisando na internet, mas basicamente nós vamos usar o Bash só para rodar programas. Por exemplo, quando executamos o comando “ls” na verdade estamos executando um programa chamado “ls”, que naturalmente é um clone do “ls” que existia no Unix. 

Ser um clone quer dizer que eles escreveram do zero um programa com mesmo nome, que faz a mesma função, mas que foi feito totalmente por outras pessoas, logo eles não devem satisfação para os criadores do programa original. No caso do “ls” vocês podem ver o código fonte neste endereço: https://github.com/wertarbyte/coreutils/blob/master/src/ls.c Reparem no copyright, como podem ver ele foi escrito pela primeira vez em 1985. Curiosidade: ele é escrito (até hoje) em linguagem C.

Portanto “ls” e outros comandos que vamos ver agora, são programas, e não propriamente a sintaxe do Bash. Um comando que seria um exemplo de sintaxe do Bash seria o comando “if”, que somente executa os comandos seguintes se a condição passada for verdadeira.

List

ls				Liste os arquivos do diretório atual.

ls /exemplo/exemploxxx/	Liste os arquivos do diretório /exemplo/exemploxxx/

ls -l				Liste os arquivos no diretório atual com informações detalhadas.

ls -a				Liste todos os arquivos no diretório atual, incluindo os ocultos.


ChangeDiretory	

cd 				Mude o diretório para o padrão (pasta do usuário)

cd /exemplo/exemploxxx/	Mude o diretório para /exemplo/exemploxxx/


MakeDiretory

mkdir nome_exemplo	Crie uma pasta no diretório atual com o nome nome_exemplo

mkdir /ex1/ex2/ex3 	Crie uma pasta no diretório /ex1/ex2/ com o nome ex3
				Caso não exista ex1 e/ou ex2 irá acusar erro.

mkdir -p /ex1/ex2/ex3	Crie uma pasta no diretório /ex1/ex2/ com o nome ex3.
				Caso não exista ex1 e/ou ex2:
					Se necessário crie ex1 em /
					Depois, se necessário, crie ex2 em /ex1/
					Por fim, crie ex3 dentro de /ex1/ex2/


Copy

cp ex1 ex2			Crie o arquivo ex2 dentro do diretório atual copiando o conteúdo de ex1
				Outro olhar: “Crie uma cópia de ex1 com o nome ex2”

cp -r ex1 ex2 		Caso ex1 seja uma pasta e esteja dentro do diretório atual, crie uma pasta ex2 e copie tudo
				o que tem dentro da ex1 para dentro.
				Outro olhar: “Crie uma cópia da pasta ex1 com o nome ex2 e com tudo que tem dentro”



Move

mv ex1 ex2			




Remove

rm ex1			Remova o arquivo ex1


