# 🖥️ Intranet Simples – Projeto de Redes (Cisco Packet Tracer)

Este projeto é uma **Intranet funcional** construída passo a passo no **Cisco Packet Tracer**, com o objetivo de aplicar os principais conceitos de **redes locais (LAN)**, **endereçamento IPv4**, e **serviços internos** como **DHCP, Web e DNS**.

---

## 📘 Objetivo

Criar uma rede local completa, partindo de uma topologia simples com *Hub* e evoluindo até uma intranet corporativa com servidores dedicados e configuração automatizada de IPs.

---

## 🧩 Estrutura da Rede

A topologia final contém:

| Componente | Função | Observações |
|-------------|--------|-------------|
| **PCs Clientes (LAN)** | Dispositivos de usuários | Recebem IP automaticamente via DHCP |
| **Switch** | Interconexão local | Encaminha pacotes com base nos endereços MAC |
| **Roteador** | Interliga redes diferentes | Atua como gateway padrão |
| **Servidor DHCP** | Atribui IPs automaticamente | Configurado no próprio roteador |
| **Servidor Web (HTTP)** | Hospeda página interna `index.html` | IP fixo configurado manualmente |
| **Servidor DNS** | Mapeia nomes para IPs internos | Exemplo: `www.fabrica.com` → IP do servidor web |

---

## ⚙️ Serviços Configurados

### 🔹 DHCP (Dynamic Host Configuration Protocol)
- **Função:** automatiza a distribuição de IPs.
- **Configurações principais:**
  ```bash
  ip dhcp pool INTRANET
  network 192.168.x.0 255.255.255.0
  default-router 192.168.x.1
  dns-server 9.0.9.9
  ```
- **Processo:** Discover → Offer → Request → Acknowledge (DORA).

---

### 🔹 Servidor Web (Intranet)
- **IP:** fixo (ex: `192.168.x.10`)
- **Serviço HTTP:** ativado.
- **Página:** `index.html` com conteúdo simples de teste.
- **Acesso interno:** feito via navegador dos PCs, usando o IP do servidor ou o nome de domínio configurado.

---

### 🔹 Servidor DNS
- **IP:** 9.0.9.9 (fixo)
- **Mapeamento:** `www.fabrica.com` → IP do servidor web.
- **Integração com DHCP:** o endereço DNS é enviado automaticamente aos clientes.
- **Resultado:** PCs acessam a intranet digitando `www.fabrica.com` em vez do IP.

---

## 🌐 Endereçamento IP

| Rede | Tipo | Faixa | Máscara |
|-------|------|--------|----------|
| LAN Principal | Privada | 192.168.x.0 | 255.255.255.0 |
| Servidor Web/DNS | Estático | 192.168.x.10 / 9.0.9.9 | 255.255.255.0 |
| Gateway | Padrão | 192.168.x.1 | — |

- Classes utilizadas: **Classe C** (rede pequena/média).
- Endereços privados e públicos demonstrados para fins educacionais.

---

## 🧠 Conceitos Aplicados

- **ICMP (Ping):** verificação de conectividade.
- **ARP:** mapeamento IP ↔ MAC.
- **Switch:** comutação inteligente e redução de broadcast.
- **Máscara de sub-rede:** separação de rede e host.
- **Roteador:** interligação de sub-redes e gateway padrão.
- **DHCP:** atribuição dinâmica de IPs.
- **DNS:** resolução de nomes internos.
- **Servidor Web:** disponibilização de páginas locais (intranet).

---

## 🚀 Testes Realizados

1. **Ping** entre PCs → conectividade interna.
2. **Ping** entre redes → funcionamento do roteador.
3. **Navegação interna:** `http://192.168.x.10` ou `http://www.fabrica.com`.
4. **Renovação DHCP:** PCs recebem IP, gateway e DNS automaticamente.

---

## 🧱 Requisitos para Abrir o Projeto

- **Cisco Packet Tracer** versão **8.2 ou superior**.
- Abrir o arquivo: `Intranet-Simples.pkt`.
- Simular a rede e testar via:
  - `ping`
  - navegador interno
  - `ipconfig /all`

---

## 🧾 Conclusão

Este projeto representa a **evolução de uma rede simples até uma intranet completa**, incluindo:

- Conectividade local eficiente com **Switch**  
- Comunicação entre redes com **Roteador**  
- Automação com **DHCP**  
- Serviços empresariais com **Web e DNS internos**  

🔹 **Resultado:** uma topologia de laboratório que replica o funcionamento básico de redes corporativas reais, com conceitos fundamentais de TCP/IP aplicados na prática.

---

## 👨‍💻 Autor
**Pedro**  
Projeto desenvolvido como parte do aprendizado em **Redes de Computadores (Alura)**.  
Arquivo principal: `Intranet-Simples.pkt`
