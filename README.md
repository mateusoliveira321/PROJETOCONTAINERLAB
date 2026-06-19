# PROJETOCONTAINERLAB
1. Introdução
Este laboratório teve como objetivo a emulação de uma topologia de rede utilizando a ferramenta Containerlab. O foco foi a criação de uma infraestrutura leve baseada em containers (utilizando a imagem nicolaka/netshoot), permitindo a configuração, teste de conectividade e análise de performance de uma rede composta por dois nós interconectados.

2. Topologia do Laboratório
A rede foi estruturada da seguinte forma:

Node-A: IP 10.0.0.1/24

Node-B: IP 10.0.0.2/24

Conexão: Link direto entre as interfaces eth1 de ambos os nós.

3. Procedimento e Resultados
3.1. Configuração e Conectividade
A rede foi inicializada com o containerlab, onde os endereços IP foram atribuídos manualmente aos nós. A conectividade foi validada com sucesso através do protocolo ICMP.

Evidência: O teste de ping entre os nós apresentou 0% de perda de pacotes, confirmando a estabilidade da camada de rede.

3.2. Análise de Performance
Foi realizado um teste de banda com a ferramenta iperf3. Os resultados foram:

Bitrate Médio: ~14.8 Gbits/sec.

Conclusão: A comunicação entre os containers apresentou alta performance, sendo ideal para testes de carga em ambientes emulados.

3.3. Monitoramento de Tráfego
Utilizou-se o tcpdump na interface eth1 para capturar o tráfego em tempo real. Foi possível observar a troca de pacotes ICMP (Echo Request e Echo Reply) entre os nós, validando a capacidade de inspeção de tráfego.

3.4. Teste de Aplicação
A comunicação de nível de aplicação foi testada utilizando o netcat (nc), onde mensagens enviadas entre o node-a e o node-b foram recebidas com sucesso, validando a camada de transporte (TCP/8080).

3.5. Análise de Falhas (Troubleshooting)
Foi simulada uma falha na camada de enlace desativando a interface (ip link set eth1 down). O resultado foi a interrupção imediata da conectividade, confirmada pela mensagem Destination Host Unreachable nos testes de ping. Este passo foi fundamental para validar o comportamento da rede em situações de erro.

4. Conclusão
O laboratório demonstrou com sucesso a eficiência do uso de contêineres para a emulação de redes. A ferramenta Containerlab mostrou-se ágil e robusta para criar topologias, permitindo realizar testes avançados de performance e análise de tráfego com baixo consumo de recursos.
