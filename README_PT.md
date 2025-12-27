# MagenticUI

<div align="center">
  <img src="docs/img/magui-readme-logo.svg" alt="MagenticUI Logo" width="200">

  _Automatize suas tarefas web enquanto você mantém o controle_

  [![Versão PyPI](https://img.shields.io/pypi/v/magentic_ui.svg)](https://pypi.python.org/pypi/magentic_ui)
  [![Licença](https://img.shields.io/pypi/l/magentic_ui.svg)](https://pypi.python.org/pypi/magentic_ui)
  ![Versões Python](https://img.shields.io/badge/python-3.10%20%7C%203.11%20%7C%203.12%20%7C%203.13-blue)
</div>

---

## 🚀 Visão Geral

O MagenticUI é um **protótipo de pesquisa** com uma interface centrada no ser humano, alimentada por um sistema de agentes múltiplos. Ele pode navegar na web, realizar ações, gerar e executar código, e analisar arquivos. O projeto foi desenhado para mantê-lo no comando, garantindo controle total sobre fluxos de trabalho automatizados.

![MagenticUI Demo](https://github.com/user-attachments/assets/7975fc26-1a18-4acb-8bf9-321171eeade7)

## ⚡ Início Rápido

### 🔰 Pré-requisitos

Antes de instalar, leia os pré-requisitos com atenção. O MagenticUI requer **Docker** para funcionar. Se você estiver no **Windows**, precisará do **WSL2**. Recomendamos o uso do [uv](https://docs.astral.sh/uv/getting-started/installation/) para uma instalação mais rápida. Se estiver usando **Mac** ou **Linux**, pode pular a etapa do WSL2.

### 💻 Instalação e Execução

bash
# 1. Crie e ative um ambiente virtual
python3 -m venv .venv
source .venv/bin/activate

# 2. Instale o MagenticUI
pip install magentic-ui --upgrade

# 3. Defina sua chave de API (exemplo para OpenAI)
export OPENAI_API_KEY=<SUA_CHAVE_API>

# 4. Execute a aplicação
magentic-ui --port 8081


Em execução, acesse a interface em **[http://localhost:8081](http://localhost:8081)**.

### 🐳 Modo Sem Docker

Caso não consiga configurar o Docker, é possível executar uma versão limitada do MagenticUI que não suporta execução de código, navegação em arquivos ou exibição do navegador:

bash
magentic-ui --run-without-docker --port 8081


### 🖥️ Interface de Linha de Comando (CLI)

Para operação sem interface gráfica, use o CLI:

bash
magentic-cli --work-dir CAMINHO/PARA/ARMAZENAR/DADOS


### 🔌 Provedores Opcionais

Para usar modelos da **Azure** ou **Ollama**, instale as dependências opcionais:

bash
# Para Azure
pip install magentic-ui[azure]

# Para Ollama
pip install magentic-ui[ollama]


---

## 🧩 Arquitetura

O MagenticUI orquestra um sistema de agentes múltiplos para resolver tarefas complexas. Veja como funciona:

<p align="center">
  <img src="./docs/img/magenticui_running.png" alt="Arquitetura do MagenticUI" height="400">
</p>

1.  **Intenção do Usuário**: Você fornece uma tarefa de alto nível (ex: "Encontre o melhor voo para Tóquio").
2.  **Orquestrador**: O agente central divide a tarefa e delega sub-tarefas para agentes especializados.
3.  **Agentes Especializados**:
    *   **Agente Web**: Navega na web, clica em links e preenche formulários usando um navegador controlado.
    *   **Agente de Código**: Escreve e executa código Python para processar dados ou gerar visualizações.
    *   **Agente de Arquivos**: Lê, escreve e gerencia arquivos dentro do espaço de trabalho seguro.
4.  **Humano no Loop**: Em momentos críticos, o MagenticUI pausa e solicita sua aprovação ou input antes de prosseguir. Isso garante segurança e precisão.

### Casos de Uso

*   **Navegação Web Complexa**: Filtrar resultados de voos ou encontrar links em sites pessoais não indexados por motores de busca.
*   **Preenchimento de Formulários**: Automatizar entrada de dados repetitiva em formulários web.
*   **Web + Código**: Buscar dados da web e gerar gráficos ou relatórios imediatamente.

---

## 🛠️ Solução de Problemas

Para problemas comuns de instalação e suas soluções, consulte o [documento de solução de problemas](TROUBLESHOOTING.md).

Se você encontrar problemas com o Docker, certifique-se de que:
1.  O Docker Desktop está em execução.
2.  Seu usuário tem permissão para executar comandos do Docker.
3.  (Windows) O backend WSL2 está ativado nas configurações do Docker.

---

## 🤝 Contribuindo

Seja bem-vindo! Consulte nosso [Guia de Contribuição](CONTRIBUTING.md) para detalhes sobre como começar.

---

## 📄 Licença

Este projeto é licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.
