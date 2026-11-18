# Prática 3 – Implementação e Análise de Protocolos de Consenso Distribuído

## Descrição do projeto

Este projeto foi desenvolvido como atividade prática da disciplina de Sistemas Distribuídos, com o objetivo de simular o funcionamento de uma plataforma de pagamentos digitais utilizando mecanismos de consenso, replicação de dados e tolerância a falhas.

A simulação utiliza cinco nós que representam servidores responsáveis pelo processamento e armazenamento de transações financeiras. O sistema busca manter a consistência das informações mesmo diante de falhas de servidores, indisponibilidade e partições de rede.

## Objetivos

- Implementar e analisar diferentes abordagens de consenso distribuído.
- Simular falhas e indisponibilidade de servidores.
- Implementar mecanismos de detecção de falhas e eleição de liderança.
- Aplicar quórum para operações de leitura e escrita.
- Testar a recuperação e sincronização de réplicas.
- Comparar os resultados das implementações.

## Implementações

Foram desenvolvidas duas abordagens:

**1. Primário-Secundário**

Um nó atua como primário, coordenando as operações e replicando as transações para os nós secundários. A implementação utiliza quórum, heartbeat, detecção de falhas, eleição de novo líder e recuperação de réplicas.

**2. Raft Simplificado**

Implementação didática baseada em conceitos do protocolo Raft, incluindo eleição de líder, votação por maioria, controle de termos e replicação de registros.

## Cenários de teste

Foram realizados 12 cenários para cada implementação, envolvendo:

- Processamento de transações em condições normais;
- Indisponibilidade de dois ou mais servidores;
- Recuperação e sincronização de nós;
- Falha do líder e eleição de um substituto;
- Perda de quórum;
- Identificação de transações duplicadas;
- Partições de rede e restauração da comunicação;
- Verificação da consistência dos dados.

## Resultados obtidos

A implementação Primário-Secundário apresentou funcionamento satisfatório, aprovando seis transações e mantendo os cinco nós sincronizados ao final dos testes. Também conseguiu detectar falhas, eleger um novo líder e recuperar réplicas.

A implementação Raft Simplificado apresentou problemas na replicação dos registros, resultando na rejeição das transações. Apesar de ter realizado uma eleição de liderança, foram necessários ajustes para garantir o funcionamento adequado do protocolo.

Os testes também permitiram observar o comportamento do sistema diante do Teorema CAP, demonstrando que a ausência de quórum pode impedir temporariamente as operações para preservar a consistência dos dados.

## Tecnologias utilizadas

- Python
- Google Colab
- Threads e sincronização
- Estruturas de dados para simulação de nós e transações

## Conclusão

A atividade possibilitou aplicar conceitos de sistemas distribuídos por meio da implementação e dos testes de diferentes abordagens de consenso. Os resultados demonstraram a importância da replicação, da detecção de falhas, da eleição de liderança e da recuperação de servidores para garantir a confiabilidade de sistemas que dependem da consistência dos dados, como plataformas de pagamentos digitais.

## Autora

Anna Beatriz Pena
- Engenharia da Computação, UNIVERSIDADE VEIGA DE ALMEIDA
