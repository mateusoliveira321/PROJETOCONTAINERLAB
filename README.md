Relatório Técnico: Implementação de Laboratório com Containerlab
1. Introdução
Este relatório documenta a implementação de um laboratório de redes virtualizado utilizando o Containerlab. O objetivo foi a criação de uma rede ponto-a-ponto entre dois nós (node-a e node-b) para validar a comunicação em camada de rede e transporte.

2. Topologia do Laboratório
A topologia consiste em dois nós interconectados diretamente via interface eth1:

Node-A: IP 10.0.0.1/24

Node-B: IP 10.0.0.2/24

3. Evidências do Laboratório
3.1. Deploy da Topologia
O deploy foi executado com sucesso, garantindo a criação dos contêineres em estado running.
<img width="512" height="139" alt="image" src="https://github.com/user-attachments/assets/6a5a64f1-ae26-4c9d-842e-0da00edd4d3e" />


3.2. Configuração de Rede
Foi validada a configuração das interfaces de rede (eth1) e endereçamento IP em ambos os nós.
<img width="512" height="389" alt="image_3afec2" src="https://github.com/user-attachments/assets/e2e32485-922a-47fd-8bbb-e7f57a111c29" />


3.3. Conectividade e Monitoramento
A conectividade foi validada via ICMP. O tcpdump foi utilizado para monitorar o tráfego gerado pelo ping,
<img width="463" height="512" alt="image_3afea8" src="https://github.com/user-attachments/assets/525e2151-4c52-494e-985c-7a48aa454ee8" />

 confirmando 0% de perda de pacotes.

3.4. Teste de Aplicação e Resiliência
Teste do Netcat (nc) para comunicação TCP e simulação de falha ao desativar a interface (ip link set eth1 down).

<img width="463" height="512" alt="image_3afea3" src="https://github.com/user-attachments/assets/e8c5727f-e577-415d-9f31-9b811ba2ac53" />


4. Conclusão
O laboratório demonstrou a eficácia do Containerlab na orquestração de redes. A configuração foi validada com sucesso, provando a conectividade, capacidade de inspeção de tráfego e resiliência da topologia emulada.
