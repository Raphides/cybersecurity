# Data Carving

É quando tentamos extrair informações úteis de arquivos para análise forense. É muito usado na análise de memória, visto que no lixo de memória, é tudo bagunçado.

## Assinaturas
Todo arquivo tem metadados, como:
- Nome do arquivo;
- Data de criação;
- Última modificação;
- Dono e permissões; e
- Extensão do arquivo.

Nem todos esses dados são zerados numa limpa, portanto podemos uar esses metadados para identificar a que aquele trecho de memória se referia.

## Cálculo de hash.
Procurar um hash pre conhecido na memória.

## Ferramentas
Há ferramentas também que pegam esse lixo de memória e indexam as informações. Algumas são:
- AccessData Forensics Toolkit FTK
- Autopsy (frontend do sleuth kit)
- OnTrack Easy Recovery
- The Sleuth Kit (open source)
- PhotoRec (especializada somente para DataCarvinf)
- IPED (open-source e brasileiro)
