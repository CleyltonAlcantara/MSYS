# MSYS2 para Windows

<h4>Plataforma de Distribuição e Construção de Software para Windows</h2>
O MSYS2 é uma coleção de ferramentas e bibliotecas que fornecem um ambiente fácil de usar para criar, instalar e executar software nativo do Windows.
<br/><br/>

## Instalação
1 -	Baixe o instalador: <a href="https://github.com/msys2/msys2-installer/releases/download/2025-02-21/msys2-x86_64-20250221.exe">msys2-x86_64-20250221.exe</a>  
2 - Execute o instalador (a instalação do MSYS2 requer o Windows 10 de 64 bits ou mais recente).  
3 -	Digite a pasta de instalação desejada (caminho curto somente ASCII em um volume NTFS, sem acentos, sem espaços, sem links simbólicos, sem subs ou unidades de rede, sem FAT).  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/Windows/Captura1.png">

4 - Quando terminar, clique em Concluir.  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/Windows/Captura2.png">

5 - Agora o MSYS2 está pronto para você e um terminal para o ambiente UCRT64 será iniciado.  

<img src="https://github.com/CleyltonAlcantara/MSYS/blob/main/Windows/Captura3.png">

6 - Você provavelmente vai querer instalar algumas ferramentas como o mingw-w64 GCC para começar a compilar projetos.  
Execute o seguinte comando:  

    $ pacman -S mingw-w64-ucrt-x86_64-gcc

7 - A janela do terminal mostrará a saída conforme abaixo. Pressione "Enter" para continuar:

    resolving dependencies...
    1looking for conflicting packages...
    Packages (15) mingw-w64-ucrt-x86_64-binutils-2.41-2
    mingw-w64-ucrt-x86_64-crt-git-11.0.0.r216.gffe883434-1
    mingw-w64-ucrt-x86_64-gcc-libs-13.2.0-2  mingw-w64-ucrt-x86_64-gmp-6.3.0-2
    mingw-w64-ucrt-x86_64-headers-git-11.0.0.r216.gffe883434-1
    mingw-w64-ucrt-x86_64-isl-0.26-1  mingw-w64-ucrt-x86_64-libiconv-1.17-3
    mingw-w64-ucrt-x86_64-libwinpthread-git-11.0.0.r216.gffe883434-1
    mingw-w64-ucrt-x86_64-mpc-1.3.1-2  mingw-w64-ucrt-x86_64-mpfr-4.2.1-2
    mingw-w64-ucrt-x86_64-windows-default-manifest-6.4-4
    mingw-w64-ucrt-x86_64-winpthreads-git-11.0.0.r216.gffe883434-1
    mingw-w64-ucrt-x86_64-zlib-1.3-1  mingw-w64-ucrt-x86_64-zstd-1.5.5-1
    mingw-w64-ucrt-x86_64-gcc-13.2.0-2

    Total Download Size:    49.38 MiB
    Total Installed Size:  418.82 MiB

    :: Proceed with installation? [Y/n]
    [... downloading and installation continues ...]

8 - Agora você pode ligar gccpara criar software para Windows.

    $ gcc --version
    gcc.exe (Rev2, Built by MSYS2 project) 13.2.0
    
9 - Após instalar o MSYS2, ele será atualizado via pacman, consulte o <a href="https://www.msys2.org/docs/updating/"> guia de atualização</a> para obter mais informações.
