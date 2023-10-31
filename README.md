1. Atualização do Sistema
Antes de instalar qualquer software, é sempre uma boa prática atualizar o repositório e o sistema. Abra o terminal e execute:
sudo apt update
sudo apt upgrade

2. Instalação do Java
O Jenkins é escrito em Java, portanto, precisamos ter o Java instalado. Vamos instalar o OpenJDK: sudo apt install openjdk-11-jdk

Verifique a instalação:
java -version

3. Instalação do Jenkins
Adicione a chave do repositório do Jenkins:
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins

4. Inicialização do Jenkins
sudo systemctl start jenkins

Para que o Jenkins inicie automaticamente ao iniciar o sistema, execute:
sudo systemctl enable jenkins

5. Configuração Inicial do Jenkins
No navegador, vá para: http://localhost:8080

A primeira vez que você acessar, será solicitado que você forneça a senha inicial. Você pode encontrar esta senha no seguinte arquivo:
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

Cole a senha no navegador e clique em "Continue".
Em seguida, escolha os plugins que deseja instalar. Para iniciantes, é recomendado escolher "Install suggested plugins"

6. Conexão com o GitHub
No Jenkins, vá para "Manage Jenkins" > "Manage Plugins" > "Available" e procure por "GitHub". Instale o plugin "GitHub".

Após a instalação, vá para "Manage Jenkins" > "Configure System".

Procure a seção "GitHub" e clique em "Add GitHub Server" > "GitHub Server".

Na seção "API URL", mantenha o valor padrão ("https://api.github.com").

Em "Credentials", clique em "Add" e escolha "Jenkins". Aqui, você fornecerá suas credenciais do GitHub. Escolha "Username with password", insira seu nome de usuário e senha do GitHub (ou token de acesso pessoal) e clique em "Add".

Selecione as credenciais que você acabou de adicionar na lista suspensa.

Salve a configuração.

Pronto! Agora o Jenkins está instalado no seu sistema Ubuntu e está conectado à sua conta do GitHub





