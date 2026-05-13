### Projeto Devops - Ronaldo Guinalz Filho

### Objetivo
Este projeto tem como objetivo implementar um fluxo de **CI/CD** completo para aplicações containerizadas, utilizando **Docker**, **Terraform** e **GitHub Actions**.  
A solução garante consistência de ambiente, automação da infraestrutura e deploys rápidos e seguros na AWS.

---

### Ferramentas e Tecnologias

#### Linux/Unix
- Edição, permissões, conexões remotas via SSH

#### AWS 
- Criação e configuração de instâncias **EC2**, **IAM**, **VPC**, **Security Groups**
- **AWS CLI** configurado e funcional

#### Docker
- Diferença entre **imagem** e **container**
- Comandos essenciais (`build`, `run`, `push`, `pull`)
- Dockerfile 

#### Terraform
- Implementar um fluxo de **CI/CD** para aplicações containerizadas, garantindo consistência de ambiente, 
- automação da infraestrutura e deploys rápidos e seguros na AWS.

##### Git/GitHub
- Comandos (`clone`, `add`, `commit`, `push`, `pull`)
- Criação e gerenciamento de repositórios
- Orquestração de fluxos de build e deploy
- Gerenciamento de secrets, aprovações, state locking e drift detection. 

---

#### Fluxo do Projeto

```text
   ┌───────────────┐
   │   Developer   │
   └───────┬───────┘
           │ Push/Commit
           ▼
   ┌───────────────────────┐
   │   GitHub Actions CI   │
   │  - Build Docker Image │
   │  - Push to ECR        │
   └─────────┬─────────────┘
             │
             ▼
   ┌───────────────────────┐
   │   Terraform IaC       │
   │  - Provision Infra    │
   │  - Configure EC2/VPC  │
   └─────────┬─────────────┘
             │
             ▼
   ┌───────────────────────┐
   │   AWS EC2 Instance    │
   │  - Pull Image from ECR│
   │  - Run Container      │
   └───────────────────────┘
