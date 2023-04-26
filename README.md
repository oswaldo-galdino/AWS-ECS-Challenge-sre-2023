# TerraForm + DockerHub + AWS-ECS - Challenge-sre-2023
Repositório com conteúdo para criação de um container utilizando Terraform e AWS ECS com imagem feita através do docker build e enviada ao repositório ogjunior07 no DockerHub.

# Proposito: Automatizar instalação de um container Ubuntu com Nginx e customizações com Terraform utilizando AWS ECS
# Autor: Oswaldo Galdino - og.junior@hotmail.com
# ------------------------------------------------------------

Para a instalação do ambiente na amazon utilizando o recurso é preciso:

- Acessar o repositório no github https://github.com/oswaldo-jr/AWS-ECS-Challenge-sre-2023.git
-
	- Acesse a console da AWS;
	- Clique no ícone do CloudShell
	- Após o CloudShell inicializar copie e cole as linhas abaixo instalar o TerraForm:
  
	sudo yum install -y yum-utils
	sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
	sudo yum -y install terraform  
  
  Para a ultima linha será necessário apertar ENTER!
  
  	- wget https://challenge-sre-2023s.s3.amazonaws.com/aws-ecs-challenge-sre-2023.zip
    
	 
  - Descompacte o arquivo com unzip aws-ecs-challenge-sre-2023.zip
	- Altere as permissões do diretório com chmod +x aws-ecs-challenge-sre-2023
	- Acesse o diretório aws-ecs-challenge-sre-2023
   - Dento do diretório verifique o arquivo main.tf, nele verifique a linha que contem a informação "image":
       "image"     : "ogjunior07/sre:1.0", -> Indica o repositório no DockerHub/Imagem:TAG que será baixada para a ciração do container.
	- https://hub.docker.com/repository/docker/ogjunior07/sre/general
       
		- Dentro do diretório execute:
	
	        - terraform init
	        - terraform plan
	        - terraform apply
	
- Após o processo de provisionamento da infraestrutura terminar acesse a console da AWS e vá até Search e pesquise por "Elastic Container Service"
	- Dentro do serviço ECS na console da AWS clique em "Clusters" e poderá verificar informações a respeito do container em execução!
