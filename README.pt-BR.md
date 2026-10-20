<p align="center">
  <img src="assets/logo-mark@4x.png" width="96" alt="Logo do OssHQ: um predinho em pixel art" />
</p>

<h1 align="center">OssHQ</h1>

<p align="center">
  <b>O QG em pixel art dos seus agentes de IA.</b><br />
  Cada sessão do Claude Code e do Codex vira um atleta: trabalha sentado na mesa, treina jiu-jitsu quando fica à toa e
  gradua com o trabalho que entrega.
</p>

<p align="center"><a href="README.md">English</a> · <b>Português</b></p>

<p align="center">
  <img src="assets/osshq-qg.png" width="900" alt="O QG do OssHQ: em cima a recepção, a sala do founder, o açaí e as salas dos projetos, com os agentes nas mesas; embaixo o vestiário, a Academia com o tatame e mais salas" />
</p>

## Instalar

**Pelo seu agente, o jeito mais fácil.** Cole isto no Claude Code (no terminal, no VS Code ou no app) ou no Codex. Ele
roda o instalador oficial e te conta o que ficou:

```text
Instale o OssHQ na minha máquina com o instalador oficial (sem sudo, para o meu usuário):

curl -fsSL https://github.com/jvttrindade/osshq/releases/latest/download/install.sh | sh

A saída do instalador já diz o endereço do QG, o que ficou conectado (Claude Code e Codex) e, se precisar, a linha para pôr no PATH: não precisa rodar mais nada para conferir.
No fim, me resuma isso e me lembre de rodar /reload-plugins nas sessões do Claude Code que já estavam abertas e, se eu uso o Codex, de aprovar os hooks do OssHQ em /hooks.
```

O agente pede a sua permissão para rodar o comando, e pronto.

**Ou pelo terminal:**

```sh
curl -fsSL https://github.com/jvttrindade/osshq/releases/latest/download/install.sh | sh
```

O QG abre em **http://localhost:4747**. Abra o Claude Code ou o Codex em qualquer projeto e veja o seu agente chegar.

**Precisa de:** macOS 13.5 ou mais novo (Apple Silicon ou Intel) ou Linux (x64 ou arm64), e Claude Code (2.1.287 ou
mais novo) ou Codex.
O Node.js vem dentro do app: sem npm, git nem Docker.

## O que você ganha

- **Uma sala por projeto, um atleta por agente.** Você vê de relance quem está trabalhando, quem terminou e quem
  levantou a mão porque **precisa de você**.
- **Responda pelo QG.** Aprove ou recuse pedidos de permissão e mande mensagem para o agente sem caçar o terminal
  certo.
- **O seu uso, ao vivo.** Uso de 5 horas e da semana de cada conta do Claude Code.
- **A faixa é conquistada.** Todo agente começa na branca e gradua pelo trabalho que entrega, com os graus no caminho.
  Ninguém ganha faixa de presente.
- **A Academia.** Quem fica à toa põe o kimono e rola no tatame, com pontos da IBJJF, árbitro e o cumprimento na beira
  do tatame. Oss.

## Comandos

| Comando | O que faz |
| --- | --- |
| `osshq` | Liga o QG, se preciso, e abre no navegador |
| `osshq status` | Versão, endereço e se o QG está no ar |
| `osshq stop` · `osshq start` | Desliga ou liga o QG |
| `osshq update` | Baixa e instala a versão mais nova |
| `osshq setup` | Instala (de novo) o mod do Claude Code e os hooks do Codex |
| `osshq mod status` · `osshq codex status` | Confere o mod em cada conta do Claude Code e os hooks do Codex |
| `osshq uninstall --sim` | Tira o mod, os hooks, o serviço e o app (seus dados ficam em `~/.osshq`) |

A configuração fica em `~/.osshq/osshq.env`, uma variável por linha (por exemplo `OSSHQ_PORT=4848`).

## O que o instalador faz

1. Baixa o app do seu sistema nas [Releases](../../releases) deste repositório e confere o SHA-256.
2. Instala em `~/.osshq/app` e põe o comando `osshq` em `~/.local/bin`.
3. Instala o mod do OssHQ em cada conta do Claude Code pelo próprio `claude plugin`, e os hooks em
   `~/.codex/hooks.json` (com backup). O Codex só roda hook novo depois que você aprova em `/hooks`.
4. Cadastra um serviço que liga com o computador (LaunchAgent no macOS, systemd do usuário no Linux), para o QG ficar
   sempre no ar. Ele só escuta em `127.0.0.1`.

Rodar o mesmo comando de novo atualiza o app e mantém os seus dados.

## Privacidade

O OssHQ roda no seu computador. Ele lê os arquivos de sessão que o Claude Code e o Codex já gravam e nunca os manda
para lugar nenhum. Não lê as suas credenciais. A única chamada para fora é a verificação de versão nova nas releases
deste repositório, a cada 6 horas; `OSSHQ_UPDATE_CHECK=0` no `~/.osshq/osshq.env` desliga.

## Fale com a gente

Achou um erro ou tem uma ideia? [Abra uma issue](../../issues). Este repositório guarda as releases, o instalador e as
issues; o código-fonte do app não é publicado aqui.

## Licença

O OssHQ é da T.EDT: as versões publicadas aqui são de uso gratuito, mas o código não é aberto. Os termos estão no
[LICENSE](LICENSE), que também vai dentro do app; ao instalar, você aceita essa licença.

O OssHQ nasceu do [Habblaud](https://github.com/marmottajr/habblaud), de Márcio Junior (MIT). O aviso dele fica no fim
do `LICENSE`, e os dos outros componentes vão dentro do app, em `THIRD_PARTY_NOTICES.md`. A foto de Hélio Gracie na
parede da Academia é de Satorijits, no [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Helio_Gracie_in_2004.jpg),
sob [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).

<p align="center"><i>Fight for life, live for fight.</i><br />Feito pela T.EDT · Trindade Educação Tecnológica</p>
