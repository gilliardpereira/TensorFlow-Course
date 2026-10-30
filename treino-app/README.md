# Ducale Fitness

App web de rotina de musculação personalizada para a academia do prédio (equipamentos Lion Fitness, halteres, kettlebells, Cross Smith, Leg Press 45°, Puxada 2 em 1, área funcional e cardio).

## O que faz

- **Avaliação inicial:** nome, sexo, idade, peso, altura, objetivo, nível, dias por semana, tempo por treino, dores/limitações e triagem de saúde (PAR-Q).
- **Rotina gerada automaticamente:** divisão (corpo inteiro, empurrar/puxar/pernas ou superiores/inferiores) conforme nível e dias; séries, faixa de repetições, descanso e “reps na reserva” conforme objetivo; troca exercícios contraindicados (joelho, lombar, ombro, punho, pressão alta); fase de adaptação de 2 semanas para iniciantes.
- **Treino do dia:** aquecimento, instruções e erros comuns de cada exercício, registro de carga/reps por série, timer de descanso, sugestão de carga (dupla progressão), cardio com zonas de FC e alongamentos.
- **Evolução:** histórico, tendência por exercício e peso corporal.
- **Bioimpedância (opcional):** anexar foto/print do laudo, colar texto ou digitar valores. A IA analisa e sugere ajustes que podem ser aplicados à rotina. Sem bioimpedância o app funciona normalmente; sem IA, mostra uma leitura por faixas de referência.

## Arquivos

- `app.html` – fonte (versão publicada no claude.ai).
- `index.html` – documento completo para abrir em qualquer navegador; gerado por `./build.sh`.

## Onde os dados ficam

- No claude.ai: na conta de cada pessoa (privado; cada morador tem o próprio perfil). A IA usa o Claude da própria pessoa.
- Fora do claude.ai (`index.html`): no navegador do aparelho. Para a IA, informe uma chave da API Anthropic na aba Perfil (fica salva só no navegador).

> Não substitui orientação médica ou de um profissional de Educação Física.

## APK Android

- `android/` é um app Android simples (WebView) que leva o `index.html` dentro do APK e funciona offline. Os dados ficam no celular.
- O workflow `.github/workflows/ducale-apk.yml` compila o APK a cada push que altera `treino-app/`. O arquivo fica na página **Releases** do repositório (e também como artefato na aba **Actions**).
- **Ícone:** coloque o logo como `treino-app/logo.png` (quadrado, de preferência 1024×1024) e faça commit; o próximo build usa o logo como ícone.
- Para compilar localmente: rode `./build.sh` e abra `android/` no Android Studio.
- A chave de assinatura (`android/app/ducale.keystore`, senha `android`) é fixa para que atualizações instalem por cima da versão anterior. Ela serve só para distribuição direta do APK, não para a Play Store.
