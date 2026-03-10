# 📸 Home Server: Gestão de Média & Infraestrutura Privada (Immich)

Este repositório documenta a implementação de uma instância do **Immich** num servidor doméstico, servindo como a espinha dorsal para a gestão de fotografias e vídeos da família, garantindo 100% de soberania de dados.

## 🚀 Visão Geral do Projeto
O objetivo central foi a criação de uma alternativa robusta ao Google Photos. Este servidor não é apenas uma galeria; é o núcleo de suporte para vários projetos da casa, incluindo o suporte para a agenda **mvbeautiful.com** e outros serviços críticos de automação.

## 🏗️ Hardware Utilizado
* **Máquina:** HP ProDesk (Intel Core i5)
* **Memória RAM:** 16GB (Upgrade estratégico para suportar múltiplos serviços simultâneos)
* **Armazenamento:** * SSD (Sistema Operativo e Docker Engines)
  * HDD Externo 2.5'' (320GB) dedicado exclusivamente ao armazenamento de média em `/mnt/immich_data`.

## 🖥️ Decisões de Engenharia & Usabilidade
### Ubuntu Desktop vs. Ubuntu Server
Embora esteja ciente de que a versão *Server* (CLI) consome substancialmente menos recursos, optei conscientemente pela instalação do **Ubuntu Desktop (LTS)**.

**Justificação:**
1. **Fator Humano:** Garante que, na minha ausência, qualquer membro do agregado familiar (mesmo sem formação técnica em terminal) consiga interagir com o servidor via interface gráfica para tarefas básicas de manutenção.
2. **Desempenho:** Com os **16GB de RAM** instalados, o *overhead* da interface gráfica é desprezível, mantendo o sistema extremamente fluido mesmo com múltiplos contentores Docker ativos.

## 🛠️ Stack Tecnológico
* **Containerização:** Docker & Docker Compose.
* **Base de Dados:** PostgreSQL 14 com extensão `pgvector`.
* **Cache:** Valkey (Redis alternative).
* **Reverse Proxy:** Nginx Proxy Manager (NPM).
* **Conectividade:** Cloudflare Zero Trust (Tunnels).



## 🔒 Camada de Segurança (Cybersecurity Focus)
Como parte do meu percurso em **CEH (Certified Ethical Hacker)**, a segurança foi prioridade:
* **Zero Exposure:** O IP doméstico nunca é exposto via Cloudflare Tunnel.
* **Certificação SSL:** HTTPS forçado em todos os domínios via Let's Encrypt.
* **Isolamento de Dados:** Utilização de variáveis de ambiente (`.env`) para proteger credenciais.

## 📈 Roadmap & Continuidade de Negócio
Este projeto encontra-se em **fase de desenvolvimento e expansão**. Atualmente, o armazenamento é suportado por um HDD de 2.5'', mas o plano de evolução prevê a substituição por **dois discos de 2TB cada, configurados em RAID**. 


## 💰 Eficiência Financeira & ROI (Return on Investment)
A implementação deste projeto foi pautada pela lógica de **redução de custos fixos**. 

* **Substituição de OPEX:** Ao internalizar o armazenamento (Self-Hosting), eliminámos a dependência de subscrições mensais de serviços como Google One ou iCloud.
* **Payback Period:** O investimento em hardware (HP ProDesk + RAM) paga-se em menos de 18 meses apenas com a poupança das mensalidades de Cloud que seriam necessárias para o volume de dados atual (320GB+).
* **Valorização do Ativo:** Além da poupança direta, o servidor agrega valor ao suportar outros projetos críticos, como a infraestrutura da agenda **mvbeautiful.com**.


📄 Download do Case Study Completo (PDF): [CLOUD_PROJECT.pdf](https://github.com/pmpg99/home-server-immich/blob/main/CLOUD_PROJECT.pdf)

Esta atualização visa aumentar a **segurança dos dados**, garantir a **alta disponibilidade** do serviço e zelar pela **continuidade de negócio/serviço**, eliminando pontos únicos de falha (SPOF) no armazenamento.

---
*Este servidor continua a ser o laboratório de testes e suporte para todos os projetos desenvolvidos em ambiente doméstico.*
