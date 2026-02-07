# WinCaos - Simulação Educacional de Sistema

Este projeto é uma aplicação experimental desenvolvida em **C#** que explora a manipulação de componentes de baixo nível do Windows (**Win32 API**). Originalmente concebido como um exercício de **Cibersegurança e UX Design**, o programa simula um cenário de "falha crítica de sistema" para testar a resiliência da interface e a resposta do sistema operacional a processos persistentes e invasivos.

## AVISO DE SEGURANÇA E LEGAL
**Este software NÃO é um vírus real**, mas utiliza técnicas comuns em malwares de simulação (*pranks*) para fins de aprendizado técnico.

* **[DETECÇÃO]:** O Windows Defender ou outros antivírus irão detectá-lo como ameaça devido às suas funções de **hook** e **registro**.
* **[AMBIENTE]:** Recomenda-se a execução apenas em ambientes controlados (**Máquinas Virtuais**).
* **[RESPONSABILIDADE]:** Este projeto possui fins estritamente educacionais. O autor não se responsabiliza por qualquer uso indevido deste código.

## TECNOLOGIAS E CONCEITOS UTILIZADOS
O projeto explora bibliotecas profundas do ecossistema Windows para demonstrar como aplicações interagem com o **kernel**:

* **`P/Invoke & Win32 API`**: Interação direta via `user32.dll` para manipulação de cursor, trilhas de movimento e parâmetros globais do sistema.
* **`Low-Level Keyboard Hooks`**: Implementação de um **Hook global** (`SetWindowsHookEx`) para filtragem de teclas de sistema (`Alt+Tab`, `WinKey`, `Esc`), demonstrando conhecimento em segurança e controle de input.
* **`Multithreading & TPL`**: Gerenciamento de múltiplas threads em modo **STA (Single Thread Apartment)** para criação dinâmica e recursiva de janelas.
* **`Registry Manipulation`**: Implementação de **persistência local** em `CurrentVersion\Run` para estudo de ciclo de vida de aplicações.
* **`UI/UX Customizada`**: Criação de interfaces *borderless* com feedback visual e sonoro em tempo real.

## FUNCIONALIDADES TÉCNICAS
* **[Simulação de Movimento Caótico]**: Algoritmo de **jitter randômico** aplicado ao cursor do sistema.
* **[Gerenciamento de Persistência]**: Escrita em chaves de **Run** do Registro do Windows para estudo de inicialização automática.
* **[Comandos de Shell Críticos]**: Integração com processos de desligamento do sistema via `ProcessStartInfo` com privilégios de execução.
* **[Interface Assíncrona]**: Gerenciamento de múltiplas janelas pop-up usando `Task.Run` e `Threading` para disparar notificações em cascata.

## COMO ENCERRAR (KILL-SWITCH)
Se você rodou o programa e deseja encerrar, utilize o **Kill-switch de Emergência**:

1. Mantenha pressionadas as teclas: **`CTRL` + `SHIFT`**
2. Enquanto segura elas, pressione a tecla: **`F12`**

**O que o protocolo de encerramento faz:**
* Restaura a **velocidade normal** do mouse e remove rastros.
* Libera os **ganchos (hooks)** do teclado.
* Encerra imediatamente todos os processos do **WinCaos**.

## 📦 REQUISITOS E EXECUÇÃO
* **Stack**: C# 10 / .NET 6.0 / Windows Forms (WinForms).
* **Instruções**:
    1. Baixe o arquivo `.zip` 
    2. Extraia o conteúdo (É fundamental manter as **DLLs** na mesma pasta do executável).
    3. Execute o **`WinCaos.exe`**.
