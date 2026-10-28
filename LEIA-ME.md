# Mister Cuequinha: Missão Pó Mágico (Android)

Projeto Android pronto para virar APK. O jogo fica dentro do app (`app/src/main/assets`), roda sem internet, em tela cheia e na horizontal. As falas dos personagens usam a voz do próprio Android.

## Jeito 1: o GitHub gera o APK (sem instalar nada)

1. Crie uma conta grátis em github.com e clique em **New repository**. Dê um nome (por exemplo `mister-cuequinha`) e crie.
2. Na página do repositório, clique em **uploading an existing file** e arraste **todo o conteúdo desta pasta**, incluindo a pasta `.github`. Clique em **Commit changes**.
   - Se a pasta `.github` não subir arrastando, crie o arquivo pelo botão **Add file → Create new file**, com o nome `.github/workflows/gerar-apk.yml`, e cole o conteúdo do arquivo de mesmo nome.
3. Abra a aba **Actions**. A tarefa **Gerar APK** começa sozinha e leva uns 3 a 5 minutos.
4. Quando ficar verde, clique nela e baixe **MisterCuequinha-apk** em *Artifacts*. Dentro do zip está o `app-debug.apk`.

## Jeito 2: Android Studio

1. Instale o Android Studio e abra esta pasta (**File → Open**).
2. Se ele pedir para criar o Gradle Wrapper ou baixar o SDK, aceite.
3. Use **Build → Build App Bundle(s) / APK(s) → Build APK(s)**. O arquivo sai em `app/build/outputs/apk/debug/`.

## Instalar no celular

1. Envie o `app-debug.apk` para o celular (WhatsApp para você mesmo, Google Drive, cabo USB).
2. Toque no arquivo. O Android vai pedir para **permitir instalar apps desta fonte**: permita.
3. Se aparecer um aviso do Play Protect dizendo que o app é desconhecido, toque em **Instalar mesmo assim**. Isso acontece com qualquer app que não veio da Play Store.

## Voz dos personagens

Se os personagens não falarem, abra **Configurações → Sistema → Idiomas → Saída de conversão de texto em voz** e instale a voz em **Português (Brasil)** do Google.

## Publicar na Play Store (opcional)

Para a loja é preciso:

- uma conta de desenvolvedor Google Play (taxa única de US$ 25);
- gerar uma versão *release* assinada, em formato `.aab`, no Android Studio (**Build → Generate Signed App Bundle**);
- ícone de 512×512 (use `icone-512.png`), capturas de tela e uma política de privacidade;
- como o público é infantil, preencher o questionário do programa **Famílias** do Google Play.

## Onde mexer

| O quê | Arquivo |
|---|---|
| Jogo (fase, personagens, chefe, sons) | `app/src/main/assets/index.html` |
| Imagens da HQ usadas nas telas | `app/src/main/assets/img/` |
| Nome do app | `android:label` em `app/src/main/AndroidManifest.xml` |
| Ícone | `app/src/main/res/mipmap-*/ic_launcher.png` |
| Versão | `versionCode` e `versionName` em `app/build.gradle` |
