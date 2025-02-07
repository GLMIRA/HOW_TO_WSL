# HOW_TO_WSL
Guia de instalação do Windows Subsystem for Linux (WSL)

Esse é um guia para instalar o wsl 2 


## 📌Passo 1:
### 1. Verificar se a Virtualização da Bios esta Ativa 

1. Pressione as teclas `Win + R`, digite `cmd` e pressione **Enter**
2. digite o seguinte comando e pressione **Enter**

```bash:
    systeminfo
```   

3. Procure por "**Hyper-V Requirements**" (Requisitos do Hyper-V)

Se a linha "**Virtualization Enabled In Firmware**" (Virtualização habilitada no firmware)
estiver como **Yes**, então a virtualização está ativada.

### Como ativar

#### **INTEL** 

1. Reinicie o PC e entre na **BIOS** (F2, F10, DEL, ou ESC).

2. Vá para a aba **Advanced** ou **CPU Configuration**.

3. Encontre a opção `Intel VT-x`, `Intel Virtualization Technology ou Intel VT-d`.

4. **Ative** essa opção e **salve as configurações (F10 e Enter)**.

5. **Reinicie o PC**.

6. **Repita** a verificação para ter certeza que foi **ativado corretamente** 


#### **AMD**

1. Reinicie o PC e entre na **BIOS** (F2, F10, DEL, ou ESC).

2. Vá para a aba **Advanced** ou **CPU Configuration**.

3. Encontre a opção `SVM Mode`(Secure Virtual Machine) ou `AMD-V`(AMD Virtualization).

4. Altere para **Enable** e e **salve as configurações (F10 e Enter)**.

5. **Salve, e Saia**.

6. **Repita** a verificação para ter certeza que foi **ativado corretamente**.

7. **Desativando** o `hyper-v`(**se necessário**)
    
    No Caso do `AMD-V`, pode ser que gere algum conflito.
    1. **Abrir um Prompt como administrador**(Cmd.exe -> Executar como adiministrador)
    
    2. digite:
        ```bash
         bcdedit /set hypervisorlaunchtype off
        ``` 
    3. **Reinicie** o PC



## 📌Passo 2:
**Caso você esteja no Windows 11 esse passo não é nescessario**
### Verificar os pré-requistos do Sistema Operacional (OS)

1. Pressione `Win + r`, digite `winver` e pressione **Enter**.

2. Uma Janela deve abrir verefique se sua versão do **Windows 10** é igual ou superior 
a versão 1903 (Build 18362)

caso sua versão seja mais atiga acesse: [Etapa de instalação versão mais atigas](https://learn.microsoft.com/pt-br/windows/wsl/install-manual) 

## 📌 Passo 3:
### Instalando o Termial

1. Abra o menu iniciar.

2. Busque por Microssoft Store.

3. Na barra de pesquise Digite `Terminal`.

4. Instale o da Microssoft Corp.

## 📌 Passo 4:

### Instalação 

#### PowerShell

1. Abra o Menu Iniciar, digite `PowerShell`

2. Execute como adiministrador (para evitar conflitos)

3. Execute o comando abaixo 
 ```PowerShell
wsl --install
``` 
esse comando vai habilítará os recursos necessarios para a instalação do **WSL**
e instala a distribuição do ubuntu do Linux **essa distro PODE ser alterada depois**

**ATENÇÂO**:

O comando acima só funcionará se o WSL não estiver instalado. Se você executar `wsl --install` e vir o texto de ajuda do WSL, 
tente executar `wsl --list --online` para ver a lista de distribuições 
disponíveis e execute `wsl --install -d <DistroName>` para instalar uma distribuição. 

4. **Reinicie o PC**

#### Microsoft Store (Recomendado)

Antes de instalar qualquer versão **habilite** o WSL

1. No menu Iniciar busque por **PowerShell** e execute como adiministrador  

2. execute: 
```PowerShell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

3. Habilite o seu wsl 2 execute:
``` PowerShell
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

4. Defina o Wsl 2 como sua versão padrão
```PowerShell
wsl --set-default-version 2
```

5. **Reinice** sua maquina para aplicar as configurações.

6. No menu iniciar busque por Microsoft Store e execute.

7. Na barra de busca, pesquise por WSL.

8. Selecione a Distribuiçao de sua preferencia, e instale.

9. **Reinicie** sua maquina. 


## 📌 Passo 5:

### Executando

#### Executando pelo app do Terminal
1. No menu iniciar busque por Terminal

2. Va em adicionar nova guia e você vera a distribuiçao.

3. Ele ira aparecer uma mensagem de que esta instalando(isso demora um pouco).
dica: caso demore muito as vezes um `Ctrl + C`, resolve.

4. Configure o seu usuario e sua senha **Atençao:** O linux não mostra **nada nem a quantidade de caracteres 
digitados** então preste atenção no momento de por a senha voce ira usar muito ela futuramente. 

Pronto, agora é só se divertir.


#### Executando pelo proprio WSL
 
1. Abra o Menu Iniciar 

2. Busque pelo nome da distribuição que esta utilizando.

3. Execute, ele ira aparecer uma mensagem de que esta instalando(isso demora um pouco).
dica: caso demore muito as vezes um `Ctrl + C`, resolve.

4. Configure o seu usuario e sua senha **Atençao:** O linux não mostra **nada nem a quantidade de caracteres 
digitados** então preste atenção no momento de por a senha voce ira usar muito ela futuramente. 

Pronto, agora é só se divertir.

