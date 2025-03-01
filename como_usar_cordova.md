# Instalando o cordova
```bash
npm install -g cordova
cordova create MyApp
cd MyApp
```

# Adicionando Android
```bash
cordova platform add android
```

# Instalando as dependências necessárias
```bash
sudo apt install openjdk-17-jdk gradle
```

# Criando uma pasta para as ferramentas android
```bash
cd && mkdir Android && cd Android && mkdir Sdk
```

# Fazer o download das ferramentas de linha de comando "cmdline-tools"
- cmdline-tools: https://developer.android.com/studio?hl=pt-br#downloads

# Mover a pasta "cmdline-tools" para Android/Sdk

#baixar com o sdkmanager uma versão específica do build-tools
```bash
sdkmanager --sdk_root="/home/$USER/Android/Sdk/" "build-tools;34.0.0"
```

# Aceitar as licensas
```bash
yes | sdkmanager --sdk_root=/home/luiz_trindade/Android/Sdk --licenses
```

# Configurar variáveis de ambiente em ~/.bashrc
```bash
export ANDROID_HOME=$HOME/Android/Sdk
export ANDROID_SDK_ROOT=$ANDROID_HOME
export PATH=$ANDROID_HOME/build-tools/34.0.0:$PATH
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin:$PATH
```

# Recarregar as consigurações de bashrc
```bash
source ~/.bashrc
```

# Criar a aplicação
```bash
cordova run android
```
