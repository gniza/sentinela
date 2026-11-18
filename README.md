# Sentinela

Monitor que roda no navegador e registra tudo o que tira o foco da página: alt-tab, troca de aba, janelas e notificações que aparecem por cima, requisições de rede, atalhos de teclado e mais. Cada evento vai para uma linha do tempo, e ao voltar para a página aparece um resumo do que aconteceu enquanto você estava fora.

## Como usar

Abra o `index.html` no navegador (ou publique com GitHub Pages) e deixe a aba em primeiro plano. Não precisa instalar nada.

- **Testar**: dispara uma requisição de rede; depois dê alt-tab ou troque de aba para ver o registro de foco.
- **Som**: liga um bipe a cada alerta.
- **Tela cheia**: deixa o monitoramento mais rígido; sair da tela cheia gera alerta.
- **Copiar registro**: copia a linha do tempo como texto.

## O que é detectado

| Evento | Como |
| --- | --- |
| Alt-tab / troca de janela | `blur` / `focus` da janela, com duração fora |
| Troca de aba, minimizar, bloquear tela | `visibilitychange` |
| Pop-up, notificação ou diálogo que fica por cima | perda de foco com a aba ainda visível |
| Requisições de rede da página | `fetch`, `XMLHttpRequest`, `WebSocket`, `sendBeacon` e `PerformanceObserver` |
| Pop-ups e alertas abertos por script | `window.open`, `alert`, `confirm`, `prompt`, `Notification` |
| Atalhos | Alt, Win/Cmd, Ctrl+Tab, PrintScreen, DevTools, Ctrl+T/N/W |
| Outros | copiar/colar, clique direito, tela cheia, redimensionar, conexão, inatividade, travamentos |

## Limites

Um site não consegue ver outros programas, notificações que não roubam o foco nem o tráfego de rede do resto do computador — o navegador isola a página de propósito. Para monitorar o sistema inteiro é preciso um programa instalado.
