# Laboratório Prático – Configuração de Rede Doméstica

* 📍 Cisco Packet Tracer
* 🎯 Objetivo: Configurar corretamente uma rede doméstica funcional

## 📘 Situação Problema

Uma residência deseja montar sua rede doméstica com acesso cabeado e sem fio.

Você foi contratado para realizar a configuração completa da rede utilizando o Packet Tracer.

A rede deve permitir:

* Comunicação entre os computadores
* Distribuição automática de IP
* Conexão Wi-Fi protegida por senha
* Teste de conectividade entre dispositivos

🖥️ PARTE 1 – Montagem da Topologia

Monte a seguinte estrutura:
### 📌 Dispositivos obrigatórios:
 - 1 Wireless Router (WRT300N)
 - 2 PCs conectados via cabo
 - 1 Notebook conectado via Wi-Fi
 - 1 Smartphone conectado via Wi-Fi

### 📌 Conexões:
* PCs → Porta Ethernet do roteador
* Notebook e Smartphone → Conexão Wireless

## 🌐 PARTE 2 – Configuração da Rede

Configure o roteador com as seguintes especificações:

### 🔹 Rede Local (LAN)
|Configuração |	Valor |
|------|-------|
|IP do Roteador	| 192.168.10.1| 
|Máscara |	255.255.255.0 |

🔹 DHCP

|Configuração |	Valor |
|-----------|---------|
|DHCP	| Ativado |
|IP Inicial	| 192.168.10.50  | 
| Número máximo de usuários |	30  |


🔹 Wireless

|Configuração |	Valor |
|SSID |	Rede_Aula |
|Segurança	| WPA2 Personal  |
|Senha | Aula12345 |


## 🔎 PARTE 3 – Configuração dos Dispositivos

* Configure todos os dispositivos para obter IP automaticamente (DHCP).
* Verifique se todos receberam IP dentro da faixa correta.
* Registre o IP de cada dispositivo.

## 📡 PARTE 4 – Teste de Conectivade

Realize os seguintes testes:

* PC0 → ping PC1
* PC0 → ping Notebook
* Smartphone → ping PC1

Todos devem responder com sucesso.

## 📝 PARTE 5 –  Questões Teóricas

Responda:
1. Qual é o gateway da rede?
2. Qual é a faixa de IP distribuída pelo DHCP?
3. Qual a função do DHCP?
4. Qual a diferença entre LAN e WLAN?

## 📄PARTE 6 –  Entrega Obrigatória - Documentação da Atividade

Além da configuração no Packet Tracer, o aluno deverá documentar todo o processo realizado, simulando um relatório técnico de implantação de rede.

# 🖨️ Relatório de Configuração de Rede

## 1️⃣ Registro com Prints de Tela (Obrigatório)

Você deverá capturar e inserir no relatório prints das seguintes etapas:

### 📌 Montagem da Topologia

*Tela completa mostrando todos os dispositivos conectados.*

### 📌 Configuração do Roteador

- **Tela da aba Setup (LAN configurada)**


- **Tela do DHCP habilitado**


- **Tela da configuração do SSID**


- **Tela da configuração de segurança WPA2**


---

### 📌 Configuração dos Dispositivos

- **Tela mostrando IP automático (DHCP) de:**

- **PC0**

- **PC1**

- **Notebook**


- **Smartphone**


---

### 📌 Testes de Conectividade

- **Print do comando:**

## 📚 Estrutura do Relatório

O documento deve conter:
* Capa (Nome, Turma, Data)
* Objetivo da atividade
* Topologia da rede
* Etapas de configuração
* Prints organizados e identificados
* Respostas dissertativas
* Conclusão final (mínimo 5 linhas)

## Regras Importantes

* Não serão aceitos apenas prints sem explicação.
* Não serão aceitas respostas copiadas da internet.
* Prints devem estar legíveis.
* O arquivo deve ser entregue em PDF. Enviar para o e-mail fornecido durante a aula.