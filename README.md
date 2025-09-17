# ☁️ Resumo do Lab: Configurando Recursos e Dimensionamentos em Máquinas Virtuais - Microsoft Azure AZ-900
Este repositório reúne os principais aprendizados adquiridos durante o laboratório de **Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure** da plataforma [DIO.me](https://web.dio.me), Módulo 2, do qual estou atualmente participando.
O foco está nos benefícios e aplicações práticas da plataforma Microsoft Azure, explorando seus recursos e funcionalidades.
O Bootcamp oferece uma base sólida em tecnologias de nuvem, abordando desde os conceitos fundamentais até os componentes essenciais da arquitetura Azure. Entre os temas estudados estão: criação e gerenciamento de máquinas virtuais, configuração de bancos de dados e soluções de armazenamento, além de tópicos avançados como arquitetura em nuvem, governança, monitoramento e segurança de ambientes cloud. 

---

# 🧠 Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure

## 🎯 Objetivo

Este pequeno guia ensina como configurar os recursos de uma máquina virtual na Azure, incluindo CPU, memória, disco e rede, além de ajustar o dimensionamento conforme a necessidade do projeto.

---

## 🛠️ Etapa 1: Como Criar uma Máquina Virtual

1. Acesse o [Portal da Azure](https://portal.azure.com).
2. Vá em **Máquinas Virtuais** > **+ Criar** > **Máquina Virtual**.
3. Preencha os campos básicos:
   - Assinatura e Grupo de Recursos
   - Nome da VM
   - Região (ex: Brazil South 2)
   - Imagem (ex: Ubuntu Server 22.04 LTS ou Windows Server)
   - Tamanho da VM (veja abaixo sobre dimensionamento)

---

## 📏 Etapa 2: como Escolher o Tamanho da VM

O tamanho define a quantidade de vCPU, memória RAM e capacidade de rede.

| Tamanho | vCPU | RAM   | Uso recomendado     |
|---------|------|-------|---------------------|
| B1s     | 1    | 1 GB  | Testes leves        |
| D2s_v3  | 2    | 8 GB  | Web apps médios     |
| E4s_v3  | 4    | 32 GB | Banco de dados      |

🔹 Para alterar o tamanho:
- Clique em **Alterar tamanho** durante a criação ou depois, na aba **Configurações** da VM.

---

## ⚙️ Etapa 3: Como Configurar o Disco e a Rede

### Disco:
- Disco do SO: SSD padrão ou premium.
- Discos de dados: Adicione conforme a necessidade de armazenamento.

### Rede:
- Configure a interface de rede, IP público e grupo de segurança de rede (NSG).
- Libere portas como 22 (SSH) ou 3389 (RDP) conforme o sistema operacional.

---

## 📈 Etapa 4: Dimensionamento Vertical e Horizontal

### 🔼 Vertical (Scale Up):
- Aumenta recursos da VM (CPU, RAM).
- Vá em **Redimensionar** na VM e selecione um tamanho maior.

### 🔁 Horizontal (Scale Out):
- Cria múltiplas instâncias da VM.
- Use **Conjunto de Dimensionamento de Máquinas Virtuais (VMSS)** para distribuir carga.

---

## 🔒 Etapa 5: Segurança e Monitoramento

- Ative o **Microsoft Defender for Cloud** para proteção.
- Configure **Monitoramento** e **Alertas** via Azure Monitor.
- Use **Backup** para restaurar em caso de falhas.

---

## 📚 Recursos Adicionais

- [Documentação oficial da Microsoft](https://learn.microsoft.com/pt-br/azure/virtual-machines/)
- [Laboratório de Computação e Rede na DIO](https://web.dio.me/project/computacao-e-rede-laboratorio/learning/85b45fef-7863-4c43-a211-a1c4342f9cda?back=/track/microsoft-azure-az-900&tab=undefined&moduleId=undefined)
- [Tutorial oficial para criar e gerenciar VMs Windows](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/tutorial-manage-vm)
- [SQL do Azure para Iniciantes](https://learn.microsoft.com/pt-br/shows/azure-sql-for-beginners/)
- [Portal Microsoft Azure](https://portal.azure.com/#allservices)
- [Calculadora de Preços Azure](https://azure.microsoft.com/pt-br/pricing/calculator/?ef_id=_k_EAIaIQobChMI14z7o_fWjwMVc0FIAB3PYQApEAAYASACEgLE-fD_BwE_k_&OCID=AIDcmmzmnb0182_SEM__k_EAIaIQobChMI14z7o_fWjwMVc0FIAB3PYQApEAAYASACEgLE-fD_BwE_k_&gad_source=1&gad_campaignid=1635078708&gbraid=0AAAAADcJh_s0nlhmSLvv4COb6oAkGNm0s&gclid=EAIaIQobChMI14z7o_fWjwMVc0FIAB3PYQApEAAYASACEgLE-fD_BwE)
- [Assinatura do Azure](https://learn.microsoft.com/pt-br/azure/azure-resource-manager/management/azure-subscription-service-limits)
  

---

> 💡 Dica: Sempre revise os custos estimados da VM antes de criar, usando a [Calculadora de Preços da Azure](https://azure.microsoft.com/pt-br/pricing/calculator/).
---
## ✅ Conclusão
A compreensão dos principais componentes da arquitetura do Azure — como regiões e pares de região, zona de disponibilidade, grupos de recursos, assinaturas e grupos de gerenciamento — é essencial para estruturar ambientes de nuvem seguros, escaláveis e organizados. Esses elementos formam a base da governança e do controle de recursos dentro da plataforma, permitindo que profissionais de tecnologia planejem, implementem e mantenham soluções eficientes no Azure.

Este material serve como apoio para quem está iniciando na jornada de computação em nuvem com Azure, oferecendo uma base sólida para futuras aplicações, certificações ou projetos profissionais.
> Este conteúdo faz parte do projeto **Construindo Arquiteturas no Azure - Laboratório** da plataforma DIO.me.

---
 
### 📚 Recursos Complementares
 
📎 Link do curso: [Microsoft Azure AZ-900 - DIO.me](https://web.dio.me/lab/computacao-da-nuvem-laboratorio/learning/6d6083cf-0291-428d-a5f2-c93166e6874d) 
