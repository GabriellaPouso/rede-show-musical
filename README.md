# Projeto de Rede para Show Musical

## Objetivo do Projeto
Este projeto tem como objetivo criar uma infraestrutura de rede para o show da banda de Miguel, facilitando a comunicação entre os membros da equipe de produção que estarão espalhados pelo teatro. A solução implementada visa garantir que todos os membros da equipe possam se comunicar facilmente, mantendo todos informados e assegurando que nada esteja fugindo do controle durante o evento.

## Descrição da Topologia
A topologia implementada é uma **rede estrela**, onde:
- Um switch central atua como ponto de conexão para todos os dispositivos
- Quatro computadores estão conectados ao switch, cada um representando um membro da equipe de produção
- Todos os dispositivos se comunicam através do switch central
- A topologia estrela foi escolhida por sua simplicidade, facilidade de manutenção e pela vantagem de que se um computador falhar, os outros continuam funcionando normalmente

## Endereçamento IP Utilizado
Todos os dispositivos estão configurados na mesma sub-rede (192.168.1.0/24):

| Dispositivo | Nome | Endereço IP | Máscara de Sub-rede | Gateway Padrão |
|-------------|------|-------------|---------------------|----------------|
| PC1 | Técnico_Som | 192.168.1.11 | 255.255.255.0 | 192.168.1.1 |
| PC2 | Iluminação | 192.168.1.12 | 255.255.255.0 | 192.168.1.1 |
| PC3 | Coordenação | 192.168.1.13 | 255.255.255.0 | 192.168.1.1 |
| PC4 | Direção | 192.168.1.14 | 255.255.255.0 | 192.168.1.1 |

## Equipamentos Virtuais Utilizados
- 1 Switch Cisco 2960 (ou similar)
- 4 PCs com interfaces de rede Ethernet
- Cabos de conexão straight-through Ethernet

## Resultados dos Testes de Comunicação
Foram realizados testes de ping entre todos os dispositivos da rede, confirmando a conectividade total. Resultados:

- Do PC "Técnico_Som" para:
  - "Iluminação" (192.168.1.12): 4 pacotes enviados, 4 recebidos (100% sucesso)
  - "Coordenação" (192.168.1.13): 4 pacotes enviados, 4 recebidos (100% sucesso)
  - "Direção" (192.168.1.14): 4 pacotes enviados, 4 recebidos (100% sucesso)

- Todos os outros PCs também conseguiram se comunicar entre si com 100% de sucesso nos testes de ping.

## Instruções para Abrir e Testar o Projeto

### Requisitos
- Cisco Packet Tracer versão 7.0 ou superior instalado

### Passos para Abrir o Projeto
1. Faça o download do arquivo "Rede_Show_Miguel.pkt"
2. Abra o Cisco Packet Tracer
3. No menu "File", selecione "Open"
4. Navegue até o local onde o arquivo foi salvo e selecione-o
5. O projeto será aberto com a topologia completa

### Passos para Testar a Conectividade
1. Clique em qualquer PC da topologia
2. Vá para a aba "Desktop"
3. Abra o "Command Prompt"
4. Execute o comando `ping` seguido do endereço IP de outro computador da rede:
   ```
   ping 192.168.1.11
   ping 192.168.1.12
   ping 192.168.1.13
   ping 192.168.1.14
   ```
5. Verifique se todos os pings têm resposta, confirmando que a comunicação está funcionando corretamente

### Screenshots
Este repositório inclui:
- Screenshot da topologia completa
- Screenshots dos resultados dos comandos ping de cada computador

## Conclusão
A rede implementada atende completamente aos requisitos do projeto, fornecendo uma solução eficiente e confiável para a comunicação da equipe de produção durante o show da banda de Miguel. A topologia estrela escolhida oferece uma boa relação custo-benefício e facilidade de manutenção, sendo ideal para este cenário.
