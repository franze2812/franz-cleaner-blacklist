# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Propósito

Este repositório mantém uma lista negra de pacotes Android maliciosos ou indesejados para uso com o Franzéribeiro Cleaner. A lista é consumida externamente por essa ferramenta para identificar e sinalizar aplicativos nocivos em dispositivos Android.

## Estrutura do Repositório

- `blacklist.txt` — Um nome de pacote Android por linha (ex.: `com.example.malware`). Atualmente com ~442 entradas, havendo duplicatas conhecidas no arquivo.
- `README.md` — Descrição breve do projeto em português.

## Convenções para o `blacklist.txt`

- Cada linha deve conter um nome de pacote Android válido no formato de domínio reverso (ex.: `com.vendor.appname`).
- Um pacote por linha, sem vírgulas, aspas ou comentários.
- O arquivo contém entradas duplicadas — ao adicionar novos pacotes, verificar duplicatas antes de commitar.
- Não há ordenação obrigatória, mas agrupar entradas relacionadas (mesmo fornecedor ou categoria) é o padrão adotado nos commits recentes.

## Tarefas Comuns

Verificar duplicatas:
```
sort blacklist.txt | uniq -d
```

Contar total de entradas:
```
wc -l blacklist.txt
```

Verificar se um pacote já está na lista:
```
grep -F "com.exemplo.pacote" blacklist.txt
```
