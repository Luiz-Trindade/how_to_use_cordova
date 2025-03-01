# Instalando o Cordova
npm install -g cordova
cordova create MyApp
cd MyApp

# Adicionando Android
cordova platform add android

# Instalando dependências
sudo apt install openjdk-17-jdk gradle -y

# Criando pastas para o SDK
mkdir -p $HOME/Android/Sdk

# Baixar as ferramentas de linha de comando "cmdline-tools" manualmente
# https://developer.android.com/studio?hl=pt-br#downloads
# Após o download, mover "cmdline-tools" para ~/Android/Sdk/

# Criar a pasta "latest" dentro de cmdline-tools
mv $HOME/Android/Sdk/cmdline-tools $HOME/Android/Sdk/cmdline-tools/latest

# Baixar SDKs necessários
sdkmanager --install "platform-tools" "platforms;android-34" "build-tools;34.0.0" "emulator"

# Aceitar licenças
yes | sdkmanager --licenses

# Configurar variáveis de ambiente
echo 'export ANDROID_HOME=$HOME/Android/Sdk
export ANDROID_SDK_ROOT=$ANDROID_HOME
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin:$PATH
export PATH=$ANDROID_HOME/platform-tools:$PATH
export PATH=$ANDROID_HOME/emulator:$PATH
export PATH=$ANDROID_HOME/build-tools/34.0.0:$PATH' >> ~/.bashrc

source ~/.bashrc

# Criar a aplicação
cordova run android
