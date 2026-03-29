# Aula Prática: Configuração de Roteamento Básico no Packet Tracer

## Objetivo

Compreender como ocorre a comunicação entre diferentes redes, configurando o roteamento básico em dispositivos no Packet Tracer e analisando o processo de resolução de endereços durante o envio de dados.

## Roteamento

Roteamento é o processo de encaminhar pacotes entre redes diferentes.
O roteador analisa o endereço IP de destino e decide por qual caminho enviar o pacote.

### Resolução de endereços

Antes de enviar um pacote na rede local, o dispositivo precisa descobrir o endereço MAC do próximo salto.

### Exemplo:

Se o PC quer enviar dados para outra rede:

* ele percebe que o destino está fora da sua rede;
* então envia o pacote para o gateway padrão;
* antes disso, descobre o MAC do gateway usando ARP.

## Topologia

* 2 PCs
* 1 Switch para cada rede
* 1 Roteador com 2 interfaces
* Cabos adequados

## Endereçamento

```text
Rede 1
Rede: 192.168.1.0/24
PC0: 192.168.1.10
Gateway: 192.168.1.1

Rede 2
Rede: 192.168.2.0/24
PC1: 192.168.2.10
Gateway: 192.168.2.1

Roteador
G0/0: 192.168.1.1 /24
G0/1: 192.168.2.1 /24
```

## Configuração do roteador

No roteador, entrar no CLI e configurar:

```bash
enable
configure terminal
interface gigabitEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface gigabitEthernet 0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit
end
write
```

* `ip address` define o endereço da interface;
* `no shutdown` ativa a interface;
* sem isso, a interface continua desligada.

# Testes

### Teste 1 – Comunicação dentro da mesma rede

Antes de testar entre redes, peça que observem a lógica:

* PC0 reconhece o gateway como pertencente à mesma rede;
* PC1 reconhece o gateway como pertencente à mesma rede.


### Ping para o gateway

* PC0:
```bash
ping 192.168.1.1
```

* PC1:
```bash
ping 192.168.2.1
```

## Usando o Simulador no Packet Tracer

1. O PC0 verifica o IP de destino.
2. Percebe que 192.168.2.10 está em outra rede.
3. Decide enviar o pacote ao gateway 192.168.1.1.
4. Se não souber o MAC do gateway, faz um ARP Request.
5. O roteador responde com ARP Reply.
6. O PC0 encapsula o pacote IP em um quadro Ethernet com MAC de destino do roteador.
7. O roteador recebe, analisa o IP de destino e encaminha para a outra rede.
8. Na rede 2, o roteador descobre o MAC do PC1, se necessário.
9. O pacote chega ao PC1.

# Atividade prática proposta


Monte no Packet Tracer uma rede com duas LANs interligadas por um roteador, configure os endereços IP, gateways e interfaces do roteador, e teste a comunicação entre os computadores das duas redes.

Desafios
1. Configurar a topologia corretamente.
2. Realizar o ping entre as máquinas.
Usar o modo Simulation para observar o ARP e o ICMP.
5. Explicar por escrito:
    * qual foi o papel do roteador;
    * quando ocorreu a resolução de endereços;
    * qual MAC foi descoberto primeiro;
    * por que o pacote precisou passar pelo gateway.

## Tabela de Endereçamento


| Dispositivo | Interface     |  Endereço IP |       Máscara |     Gateway |
| ----------- | ------------- | -----------: | ------------: | ----------: |
| PC0         | FastEthernet0 | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |
| PC1         | FastEthernet0 | 192.168.2.10 | 255.255.255.0 | 192.168.2.1 |
| R1          | G0/0          |  192.168.1.1 | 255.255.255.0 |           — |
| R1          | G0/1          |  192.168.2.1 | 255.255.255.0 |           — |
