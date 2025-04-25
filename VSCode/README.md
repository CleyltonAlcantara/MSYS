# MSYS2 para VSCode

<h4>Plataforma de Distribuição e Construção de Software para Windows que pode ser usando com o VS Code</h2>
O MSYS2 é uma coleção de ferramentas e bibliotecas que fornecem um ambiente fácil de usar para criar, instalar e executar.
<br/><br/>

## Pré-requisitos
1 - Instalar o <a href="https://code.visualstudio.com/download">Visual Studio Code</a>.  
2 - Instale a extensão <a href="https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools">C/C++ para o VS Code</a>. Você pode instalar a extensão C/C++ pesquisando por "C++" na visualização Extensões ( Ctrl+Shift+X ).  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/VSCode/Extension-C++.png">
<br/>

## Instalando a cadeia de ferramentas MinGW-w64

Obtenha a versão mais recente do MinGW-w64 via MSYS2, que fornece compilações nativas atualizadas do GCC, MinGW-w64 e outras ferramentas e bibliotecas C++ úteis. Isso fornecerá as ferramentas necessárias para compilar seu código, depurá-lo e configurá-lo para funcionar com o <a href="https://code.visualstudio.com/docs/editing/intellisense">IntelliSense</a>.  

Para instalar a cadeia de ferramentas MinGW-w64, assista a este <a href="https://youtu.be/oC69vlWofJQ">vídeo</a> ou siga os passos abaixo:  

1 - Você pode baixar o instalador mais recente na página do MSYS2 ou usar este <a href="https://github.com/msys2/msys2-installer/releases/download/2025-02-21/msys2-x86_64-20250221.exe">link direto para o instalador</a>.  
2 - Execute o instalador (a instalação do MSYS2 requer o Windows 8.1 de 64 bits ou mais recente).  
3 -	Digite a pasta de instalação desejada (caminho curto somente ASCII em um volume NTFS, sem acentos, sem espaços, sem links simbólicos, sem subs ou unidades de rede, sem FAT).  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/VSCode/Captura1.png">

4 - Quando terminar, clique em Concluir.  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/VSCode/Captura2.png">

5 - Ao concluir, certifique-se de que a caixa "Executar MSYS2 agora" esteja marcada e selecione " Concluir". Isso abrirá uma janela de terminal do MSYS2.  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/VSCode/Captura3.png">

6 -  Neste terminal, instale a cadeia de ferramentas MinGW-w64 executando o seguinte comando:  

```shell
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

7 - Aceite o número padrão de pacotes no grupo de cadeia de ferramentas pressionando __Enter__.  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/VSCode/Packages-toolchain-MSYS.png">

8 - Digite "Y" quando solicitado para prosseguir com a instalação e ao finalizar pode fechar a janela.  

9 - Adicione o caminho da sua pasta bin MinGW-w64 à variável de ambiente do path do Windows usando as seguintes etapas:  
    - Na barra de pesquisa do Windows, digite __Configurações__ para abrir as Configurações do Windows.  
    - Pesquise __Editar as variáveis de ambiente para sua conta__.  
    - Em suas variáveis ​​de usuário, selecione a variável __Path__ e depois selecione __Editar__.  
    - Selecione __Novo__ e adicione à lista a pasta de destino MinGW-w64 que você registrou durante o processo de instalação. Se você usou as configurações padrão acima, este será o caminho: ``` C:\msys64\ucrt64\bin ```.  
    - Selecione __OK__ e, em seguida, __OK__ novamente na janela Variáveis ​​de Ambiente para atualizar a PATH variável de ambiente. É necessário reabrir todas as janelas do console para que a PATH variável de ambiente atualizada fique disponível.
</br></br>

## Verifique sua instalação do MinGW

Para verificar se suas ferramentas MinGW-w64 estão instaladas e disponíveis corretamente, abra um novo prompt de comando e digite:
```shell
gcc --version
```
```shell
g++ --version
```
```shell
gdb --version
```
Você deverá ver uma saída informando quais versões do GCC, g++ e GDB você instalou. Se não for o caso:  
1 - Certifique-se de que a entrada da variável PATH corresponda ao local binário do MinGW-w64 onde a cadeia de ferramentas foi instalada. Se os compiladores não existirem nessa entrada PATH, certifique-se de ter seguido as instruções anteriores.
Se gcctiver a saída correta, mas não gdb, então você precisa instalar os pacotes que estão faltando no conjunto de ferramentas MinGW-w64.  
2 - Se durante a compilação você receber a mensagem "O valor de miDebuggerPath é inválido", uma das causas pode ser que você não tenha o mingw-w64-gdbpacote.


  
