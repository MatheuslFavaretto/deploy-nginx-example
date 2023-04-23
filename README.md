# Deploy de uma Aplicação nginx com Argocd

![github_original_wordmark_logo_icon_146506](https://user-images.githubusercontent.com/116848225/233849163-de53febc-5f3d-429d-a6c1-abbea6ab73ed.png)
![folder_type_minikube_icon_129889](https://user-images.githubusercontent.com/116848225/233849176-205eeed9-c9ee-4033-afea-d5b6cee7a35b.png)
![argo_logo_icon_247561](https://user-images.githubusercontent.com/116848225/233849185-bef5ce15-3743-452f-a136-e6d07e766e45.png)


## Este repositório contém informações sobre como usar o ArgoCD, uma ferramenta de entrega contínua (CD) para Kubernetes.
Instalação

### Para instalar o ArgoCD, você pode seguir estas etapas:

Crie o namespace do ArgoCD:

> kubectl create namespace argocd

Adicione o repositório do ArgoCD ao Helm:

> helm repo add argo https://argoproj.github.io/argo-helm

Instale o operador do ArgoCD:

> helm install argocd argo/argo-cd --namespace argocd

### Para usar o ArgoCD, siga estas etapas:

Crie um aplicativo no ArgoCD:

> kubectl apply -f <APP_YAML_FILE>

Verifique o status do aplicativo:

> argocd app get <APP_NAME>

### Clone o repositorio com o comando 

> argocd app create <APP_NAME> --repo https://github.com/MatheuslFavaretto/deploy-nginx-example.git --path . --dest-server <seu cluster> --dest-namespace default

### Sincronize o aplicativo com as definições de configuração:

> argocd app sync <APP_NAME>

### Veja o registro do aplicativo:

> argocd app logs <APP_NAME>

Gerencie o ciclo de vida do aplicativo usando o painel da interface do usuário do ArgoCD.


![image](https://user-images.githubusercontent.com/116848225/233849108-31782889-f7fc-4286-821c-03f736ef0b51.png)


