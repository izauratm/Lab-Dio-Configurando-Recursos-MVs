# <h1 align="center">🖥️ Resumo do Lab: Configurando Recursos e Dimensionamentos em Máquinas Virtuais - Microsoft Azure AZ-900</h1>
Este repositório reúne os principais aprendizados adquiridos durante o curso **Computação e Rede** da plataforma [DIO.me](https://web.dio.me), Arquitetura e Serviços Azure - Módulo 2. O foco está nos benefícios e aplicações práticas da plataforma Microsoft Azure, explorando seus recursos e funcionalidades.
O Bootcamp oferece uma base sólida em tecnologias de nuvem, abordando desde os conceitos fundamentais até os componentes essenciais da arquitetura Azure. Entre os temas estudados estão: criação e gerenciamento de máquinas virtuais, configuração de bancos de dados e soluções de armazenamento, além de tópicos avançados como arquitetura em nuvem, governança, monitoramento e segurança de ambientes cloud. 

---

## 🎯 Objetivo
Este pequeno guia ensina como configurar os recursos de uma máquina virtual na Azure, incluindo CPU, memória, disco e rede, além de ajustar o dimensionamento conforme a necessidade do projeto.

---

## 🛠️ Etapa 1: Como Criar uma Máquina Virtual

1. Acesse o [Portal da Azure](https://portal.azure.com).
2. Vá em **Máquinas Virtuais** > **+ Criar** > **Máquina Virtual**.
3. Preencha os campos básicos:
   - Assinatura e Grupo de Recursos
   - Nome da VM
   - Região (ex: Brazil South)
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
## 🔰A seguir, um guia dos passos 'Criar Máquina Virtual - Microsoft Azure':
### Aba 1: Básico = Esta é a primeira tela (aba) de configuração. Define a base da VM.
- Grupo de Recursos: É um contêiner lógico que agrupa recursos do Azure. Use um grupo de recursos para organizar e gerenciar todos os ativos da sua VM (como discos e rede) em um só lugar.
- Nome da Máquina Virtual: Escolha um nome claro e descritivo para sua VM. Exemplo: `minha-vm-webserver`. 
- Região: Selecione a região geográfica mais próxima de seus usuários para reduzir a latência. Por exemplo, se o público está no Brasil, escolha a região Brazil South.
* **Opções de Disponibilidade:**
   * **Conjunto de Disponibilidade:** Garante que a VM não seja afetada por falhas em um único servidor físico. É ideal para aplicações com alta disponibilidade.
   * **Zonas de Disponibilidade:** Protege a VM contra falhas em um data center inteiro, replicando-a em diferentes zonas físicas. É a melhor opção para resiliência máxima.
- Imagem: Escolha o sistema operacional da sua VM (ex: Windows Server, Ubuntu Server).
- Tamanho: Selecione o tamanho da VM, que define a quantidade de vCPU (processador) e RAM. É aqui que dimensionamos o poder de processamento. A Azure oferece tamanhos otimizados para diferentes cenários, como uso geral, computação intensiva ou memória.

### Aba 2: Discos = Configura o armazenamento da VM.
 * **Tipo de Disco do SO:** Escolhe o tipo de disco para o sistema operacional.
    * **SSD Premium:** Para cargas de trabalho de alta performance (bancos de dados, aplicações críticas).
    * **SSD Standard:** Um bom equilíbrio entre desempenho e custo.
    * **HDD Standard:** Mais barato, ideal para dados que não exigem alta velocidade.
- Discos de Dados: Adiciona discos adicionais para armazenar os dados, como arquivos de banco de dados ou logs, separados do disco do sistema operacional.

### Aba 3: Rede = Esta aba é crucial para a conectividade da VM.
- Rede Virtual (VNet): Um isolamento lógico para a VM, atuando como sua própria rede privada na nuvem.
- Endereço IP Público: Um endereço IP para permitir acesso à VM pela internet.
- Portas de Entrada: Define quais portas (como 80 para HTTP ou 22 para SSH) estarão abertas para tráfego externo. Atenção: Mantenha as portas fechadas por padrão e abra apenas as que são realmente necessárias por segurança.

### Aba 4: Gerenciamento = Esta seção oferece ferramentas para gerenciar a VM.
- Diagnóstico de inicialização: Ativado por padrão, permite visualizar a tela de inicialização da VM, o que é útil para solucionar problemas.
- Identidade Gerenciada: Permite que a VM se autentique em outros serviços do Azure (como bancos de dados ou armazenamento) de forma segura, sem a necessidade de gerenciar credenciais.

### Aba 5: Monitoramento = Configura como a VM será monitorada.
- Diagnóstico de Convidado do SO: Coleta métricas de desempenho do sistema operacional, como uso de CPU e memória. É fundamental para monitorar a saúde da VM e ajustar o dimensionamento.

### Aba 6: Avançado =  Contém configurações mais específicas. 
- Extensões: Adiciona funcionalidades extras, como a instalação de um antivírus ou um agente de monitoramento.
- Dados de Usuário: Execute aqui os scripts de configuração na primeira inicialização da VM.

### Aba 7: Marcas
- As Marcas (ou Tags) são pares de nome/valor que ajudam a categorizar e organizar seus recursos. Use-as para rastrear custos, proprietários ou ambientes (ex: Ambiente: Produção, Projeto: Webapp).
### Aba 8: Revisar + Criar
- Aqui você revisa todas as suas configurações. A Azure também realiza uma validação automática para garantir que tudo está correto. Após a validação, clique em Criar para provisionar a sua VM.

## 📚 Recursos Adicionais
- [Documentação oficial da Microsoft](https://learn.microsoft.com/pt-br/azure/virtual-machines/)
- [Tutorial oficial para criar e gerenciar VMs Windows](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/tutorial-manage-vm)
- [SQL do Azure para Iniciantes](https://learn.microsoft.com/pt-br/shows/azure-sql-for-beginners/)
- [Portal Microsoft Azure](https://portal.azure.com/#allservices)
- [Calculadora de Preços Azure](https://azure.microsoft.com/pt-br/pricing/calculator/?ef_id=_k_EAIaIQobChMI14z7o_fWjwMVc0FIAB3PYQApEAAYASACEgLE-fD_BwE_k_&OCID=AIDcmmzmnb0182_SEM__k_EAIaIQobChMI14z7o_fWjwMVc0FIAB3PYQApEAAYASACEgLE-fD_BwE_k_&gad_source=1&gad_campaignid=1635078708&gbraid=0AAAAADcJh_s0nlhmSLvv4COb6oAkGNm0s&gclid=EAIaIQobChMI14z7o_fWjwMVc0FIAB3PYQApEAAYASACEgLE-fD_BwE)  
- [Assinatura do Azure](https://learn.microsoft.com/pt-br/azure/azure-resource-manager/management/azure-subscription-service-limits)
> 💡 Dica: Sempre revise os custos estimados da VM antes de criar!  


---
## ✅ Conclusão
Ao seguir este resumido guia, você será capaz de criar e dimensionar suas máquinas virtuais de forma eficiente e segura.

Este material serve como apoio para quem está iniciando na jornada de computação em nuvem com Azure, oferecendo uma base sólida para futuras aplicações, certificações ou projetos profissionais.
> Este conteúdo faz parte do projeto **Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure - Laboratório** da plataforma DIO.me.

---
 
📎 Link do curso: [Microsoft Azure AZ-900 - DIO.me](https://web.dio.me/track/microsoft-azure-az-900) 

---

### Licença

Este projeto está licenciado sob os termos da [Licença MIT](LICENSE).

<img alt="Static Badge" src="https://img.shields.io/badge/license-MIT-green">
