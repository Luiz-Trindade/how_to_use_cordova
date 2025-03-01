# Instalando o Cordova
```bash
npm install -g cordova
cordova create MyApp
cd MyApp
```

# Adicionando Android
```bash
cordova platform add android
```

# Instalando dependências
```bash
sudo apt install openjdk-17-jdk gradle -y
```

# Criando pastas para o SDK
```bash
mkdir -p $HOME/Android/Sdk
```

# Baixar as ferramentas de linha de comando "cmdline-tools" manualmente
## https://developer.android.com/studio?hl=pt-br#downloads
## Após o download, mover "cmdline-tools" para ~/Android/Sdk/

# Criar a pasta "latest" dentro de cmdline-tools com todo conteúdo de cmdline-tools
```bash
Antes: $HOME/Android/Sdk/cmdline-tools
Depois: $HOME/Android/Sdk/cmdline-tools/latest
```

# Configurar variáveis de ambiente
```bash
echo 'export ANDROID_HOME=$HOME/Android/Sdk
export ANDROID_SDK_ROOT=$ANDROID_HOME
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin >> ~/.bashrc
```

# Baixar SDKs necessários
```bash
sdkmanager --install "platform-tools" "platforms;android-34" "build-tools;34.0.0" "emulator"
```

# Aceitar licenças
```bash
yes | sdkmanager --licenses
```

# Atualizar a configuração de ~/.bashrc
```bash
source ~/.bashrc
```

# Criar a aplicação
```bash
cordova run android
```
