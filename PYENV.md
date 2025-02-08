# Como Configurar o Ambiente Python 


## 📌 Passo 1: Atualizar os Pacotes do Sistema

1. Abra o **terminal** no WSL.
2. Atualize a lista de pacotes do sistema:

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 📌 Passo 2: Instalar Dependências Necessárias

Execute o seguinte comando para instalar as dependências:

```bash
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev \
libffi-dev liblzma-dev
```

## 📌 Passo 3: Instalar o Pyenv

1. Baixe e execute o script de instalação:

```bash
curl https://pyenv.run | bash
```

2. Adicione as configurações do Pyenv ao seu shell:

```bash
echo -e '\nexport PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
```

3. Aplique as mudanças executando:

```bash
source ~/.bashrc
```

---

## 📌 Passo 4: Verificar a Instalação

Verifique se o Pyenv foi instalado corretamente com:

```bash
pyenv --version
```

Se aparecer a versão do Pyenv, a instalação foi concluída com sucesso! 

---

## 📌 Passo 5: Instalar uma Versão do Python com o Pyenv

1. Liste as versões disponíveis do Python:

```bash
pyenv install --list
```

2. Instale uma versão específica (exemplo: Python 3.10.6):

```bash
pyenv install 3.10.6
```

3. Defina a versão instalada como padrão global:

```bash
pyenv global 3.10.6
```

4. Verifique a versão ativa do Python:

```bash
python --version
```

Agora, seu WSL está configurado com Pyenv! 
