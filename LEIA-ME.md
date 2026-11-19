# Sistema do Caçador — apps nativos (Android e iPhone)

Projeto Capacitor pronto. Os alarmes usam **notificações nativas agendadas**, então tocam com a tela bloqueada e com o app fechado.

## ANDROID — sem instalar nada no PC (GitHub gera o APK)
1. Crie uma conta grátis em github.com e um repositório novo (privado serve).
2. Envie TODO o conteúdo desta pasta para o repositório (botão "Add file → Upload files", arraste tudo, inclusive a pasta `.github`).
3. Abra a aba **Actions → "Gerar APK Android" → Run workflow**. Em ~5 minutos aparece o arquivo **Sistema-do-Cacador-APK** para baixar.
4. Descompacte, passe o `app-debug.apk` para o celular e instale (permita "fontes desconhecidas").
5. Abra o app → **Foco → Alarmes**: toque em **Ativar** (notificações) e depois em **Testar alarme**.
6. Android 12+: em Configurações do app → "Alarmes e lembretes" → permitir, e desative a otimização de bateria para o app, para o alarme ser pontual.

### Android pelo computador (alternativa)
Instale Node.js 18+ e Android Studio. Na pasta: `npm install`, `npx cap sync android`, `npx cap open android` → Build → Build APK(s).

## iPHONE (precisa de um Mac)
A Apple só permite compilar apps de iPhone no **Xcode (macOS)**.
1. No Mac: instale Node.js e Xcode. Na pasta: `npm install` e `npx cap sync ios`, depois `npx cap open ios`.
2. No Xcode: selecione o projeto **App** → Signing & Capabilities → escolha seu **Team** (Apple ID).
3. Conecte o iPhone, selecione-o como destino e clique ▶ Run.
   - Com Apple ID gratuito, o app instalado vale por **7 dias** (depois reinstale).
   - Para instalar de forma permanente (TestFlight / App Store) é preciso o **Apple Developer Program (US$ 99/ano)**.
4. No app: Foco → Alarmes → Ativar notificações. (O iPhone limita a 64 notificações agendadas; o app agenda as próximas 60.)
Sem Mac: serviços de build na nuvem com macOS (ex.: Codemagic) podem compilar, mas também exigem a conta de desenvolvedor para assinar.

## Observações
- Os dados ficam salvos no aparelho. Use Perfil → Backup para levar o progresso entre aparelhos.
- Mudou algo em `www/index.html`? Rode `npx cap sync` de novo.
