Como funciona?

Namespaces = isolamento de processos

Processo pai Container 1 recebe varios filhos ainda no container 1 (que é o Namespace em si)


### Pilares 

##### Namespaces
Isola processos filhos, assim simulando a "maquina virtual".

##### Cgroups
Controla os recursos computacionais do container, ou seja, isola e limita os recursos disponiveis para o processo

#### Overlay File System

Trabalho com camadas para alterar apenas as diferenças quando são atualizadas as dependências e etc

#### Imagens
É um conjunto de dependências encadeadas numa árvore para utilização.
Criada por camadas para evitar dependencias "introcaveis". Tem nome e versão.
No Docker, existe o Dockerfile que é um arquivo DECLARATIVO utilizado para construir imagens.
A Imagem é Imutavel! 

O Image Registry funciona como se fosse um Git para as imagens de Docker. Tem commit, para tornar a alteração na imagem permanente, o pull para baixar a imagem atualizada e um push para adicionar ela ao Image Registry.

### Docker Host e Docker Client

Docker client cuida de:

- Containersd
- Run, Pull, Push
- Volumes
- Network (comunicacao entre containers)

Docker Host:
- Volumes
- Network
- Cache (Liga com o registry para dar pull e push)
- daemon - API

## Docker Commands

#### docker ps 
shows containers running

#### docker ps -a 
shows containers recently runned
