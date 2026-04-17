# Rotas estáticas

Rotas estáticas são caminhos definidos manualmente no roteador para indicar para onde enviar pacotes destinados a outras redes.

> 👉 Ou seja:

Você diz explicitamente ao roteador:
**“Para chegar nessa rede, envie por esse caminho.”**

## 🔧 Quando usar?

* ✔️ Redes pequenas
* ✔️ Topologias simples
* ✔️ Ambientes de laboratório
* ✔️ Quando você quer controle total da rota

> ❌ Não recomendado para redes grandes (muita manutenção manual)

## ⚙️ Como funciona?

O roteador analisa o destino do pacote e consulta sua tabela de roteamento:

Se existir uma rota estática → ele usa essa rota
Se não existir → pacote é descartado (ou usa rota padrão)

## 🧾 Sintaxe (Cisco)
```bash
ip route [REDE_DESTINO] [MASCARA] [PROXIMO_SALTO]
```
## Utilizando po Cenário

![alt text](imagens/enderecamento_subneting.png)

* 🔹 No R1 (para alcançar rede 192.168.2.0)

```bash
ip route 192.168.2.0 255.255.255.0 200.198.2.10
```

* 🔹No R2:
```bash
ip route 192.168.1.0 255.255.255.0 200.198.2.9
```

## 🔁 Fluxo do Tráfego
*  PC da rede 192.168.1.x envia pacote
*  Vai para o gateway (R1)
*  R1 consulta rota estática
* Encaminha para R2
* R2 entrega ao destino