## ⚠️ WinChaos - Educational System Simulation (Projeto001)
Este projeto é uma aplicação experimental desenvolvida em C# que explora a manipulação de componentes de baixo nível do Windows (Win32 API). Originalmente concebido como um exercício de Cibersegurança e UX Design, o programa simula um cenário de "falha crítica de sistema" para testar a resiliência da interface e a resposta do sistema operacional a processos persistentes e invasivos.

## 🔴 AVISO DE SEGURANÇA E LEGAL
Este software NÃO é um vírus real, mas utiliza técnicas comuns em malwares de simulação (pranks) para fins de aprendizado técnico.
Detecção: O Windows Defender ou outros antivírus irão detectá-lo como ameaça devido às suas funções de hook e registro.
Ambiente: Recomenda-se a execução apenas em ambientes controlados (Máquinas Virtuais).
Responsabilidade: Este projeto possui fins estritamente educacionais. O autor não se responsabiliza por qualquer uso indevido deste código.

## Tecnologias e Conceitos Utilizados
O projeto explora bibliotecas profundas do ecossistema Windows para demonstrar como aplicações interagem com o kernel:
P/Invoke & Win32 API: Interação direta via user32.dll para manipulação de cursor, trilhas de movimento e parâmetros globais.
Low-Level Keyboard Hooks: Implementação de hook global (SetWindowsHookEx) para filtragem de teclas de sistema (Alt+Tab, WinKey, Esc), demonstrando controle total de input.
Multithreading & TPL: Gerenciamento de múltiplas threads em modo STA (Single Thread Apartment) para criação dinâmica e recursiva de janelas pop-up.
Manipulação de Registro (Registry): Implementação de persistência local em CurrentVersion\Run para estudo de ciclo de vida de aplicações.
UI/UX Customizada: Criação de interfaces borderless (sem bordas) com feedback visual contínuo.

## Funcionalidades Técnicas
Simulação de Movimento Caótico: Algoritmo de jitter randômico aplicado ao cursor do sistema.
Gerenciamento de Persistência: Escrita em chaves do Registro do Windows para inicialização automática.
Comandos de Shell Críticos: Demonstração de execução de comandos de desligamento via ProcessStartInfo.
Interface Assíncrona: Uso de Task.Run e Threading para disparar janelas de erro em cascata sem travar o processo principal.

## Como Encerrar (Emergency Exit)
Caso a simulação dificulte o uso do computador, utilize o Kill-switch de Emergência implementado:

Mantenha pressionadas as teclas: CTRL + SHIFT
Enquanto segura, pressione a tecla: F12

O que acontece ao acionar o atalho:
Restaura a velocidade original do mouse e remove rastros.
Libera todos os ganchos (hooks) do teclado.
Encerra imediatamente todos os processos do WinChaos.

Requisitos e Execução
Tecnologias: C# 10 / .NET 6.0 / WinForms.
Execução:
Baixe a versão mais recente em [Releases].
Extraia todos os arquivos do .zip para uma pasta (mantenha as DLLs junto ao .exe).
Execute o WinChaos.exe.
