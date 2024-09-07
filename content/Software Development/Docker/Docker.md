It is a platform that lets you package an application and all its dependencies into a container. This container can run anywhere, ensuring that the app works consistently, whether it's on your local machine, in a cloud environment, or wherever else you decide to throw it.

But how does it works?

## Namespaces for isolating processes

Docker uses **[[Linux Namespaces]]** to provide isolation, which means each container thinks it's got its own little universe to play in. It uses Linux namespaces to segregate the processes, so containers don't know about each other or what's going on in the host system. Docker applies several types of namespaces to achieve this isolation:

- **PID Namespace**: Isolates process IDs. Containers have their own process tree, so a process in one container can’t see processes in another container.

- **Network Namespace**: Each container gets its own network stack, which means it has its own interfaces, IP addresses, routing tables, etc.

- **Mount Namespace**: This isolates the filesystem, so a container only sees its own directories. It doesn’t have access to the host’s file system unless you explicitly share it.

- **UTS Namespace**: This is for isolating hostnames. A container can have its own hostname and domain name, and it doesn’t have to care about what the host is called.

- **IPC Namespace**: Isolates inter-process communication. Containers can only interact with processes and resources in their own little bubble, so no sharing of semaphores or message queues with others.

- **User Namespace**: Isolates user and group IDs. This means that a process inside a container might think it's running as root (how adorable), but on the host, it's actually running as a non-privileged user. This keeps your containers from ruining everything when you mess up.
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
