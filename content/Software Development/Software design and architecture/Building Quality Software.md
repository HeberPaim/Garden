## Processos comuns em engenharia de software
Requirement gathering
Design
Coding for quality
Testing
Releases
Documenting

#### Requirement Gathering
Processo de coletar e documentar o conjunto de necessidades que o software precisa atender.
Pode incluir um conjunto de casos que descreva as necessidades do negócio e os processos dos usuários que precisam ser implementadas no software.
Podem ser classificados em 4 categorias:
- Funcional
- Externo e interface de usuário
- Funcionalidade do sistema
- não funcionalidade

#### Design 

Consiste em transformar as necessidades do software em código.
Geralmente é quebrado em componentes menores para que se adequem às necessidades do documento de design com comportamentos. limites e interações claras. Esses componentes definem a arquitetura do sistema.

#### Coding for quality

Leva em conta as necessidades de qualidade de código, sendo as principais:

manutenibilidade
Legibilidade
Testabilidade 
Segurança

Código de qualidade deve preencher todos os requisitos sem defeitos, alem de ser 
- Limpo e consistente
- Fácil de ler e dar manutenção
- Bem documentado
- Eficiente

Tendo em vista isso, código de qualidade deve ser escrito utilizando *padrões de código*, usando linters para detectar erros de identação, sintaxe e despadronização e deve ser comentado para que seja mais fácil de entender e se modificar caso seja necessário.
#### Testing
É o processo de verificar se o software preenche os requisitos e não está com bugs.
Ajuda a identificar erros, gaps ou a falta de requisitos em cumprimento.
Garante a confiabilidade, segurança, performance e eficiencia do codigo escrito.
Pode ser automatizado ou manual

###### Teste unitário
Feito pelo desenvolvedor, dando prioridade aos menores componentes que podem ser isolados do sistema

###### Teste de integração
Quando um desenvolvimento é adicionado ao software de qual ele deve fazer parte, se testa novamente para garantir suas funcionalidades

###### System testing
Serve para garantir que o código implementado não teve impacto em outras áreas do sistema.

###### User acceptance testing (UAT) ou BETA
Quando o software é testado pelo usuário final para garantir que está tudo funcionando perfeitamente.
#### Releases
Geralmente existem 3 tipos de release
##### Alpha
- Select stakeholders
- May contain errors
- Preview of functioning version
- Design changes may occur

##### Beta
- All Stakeholders
- User testings
- meets requirements

##### General Availability
- Stable
- All Users

#### Documenting
Deve ser dado tanto para non-technical users como para technical-users
##### Documentação do sistema consiste em
- README files
- inline comments
- architecture and design documents
- verification informantion
- maintenance guides
##### Documentação do usuário consiste em
- Guia de usuário
- Videos instrutórios
- Manuais
- Online and inline help