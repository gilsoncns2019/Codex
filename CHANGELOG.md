# Changelog

Todas as mudanças notáveis neste projeto serão documentadas neste arquivo.

O formato é baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/),
e este projeto adere ao [Versionamento Semântico](https://semver.org/lang/pt-BR/).

## [1.0.0] - 2024-01-15

### Adicionado
- **Processamento Inteligente de PDFs**
  - Extração robusta de texto usando PDF.js
  - Suporte a metadados de documentos (autor, título, data de criação)
  - Validação automática de arquivos PDF

- **Integração com Google Gemini**
  - Cliente completo para API Gemini 2.5 Flash e Pro
  - Geração de resumos executivos estruturados
  - Extração automática de conceitos-chave categorizados
  - Criação de perguntas e respostas educativas
  - Validação de chave da API com teste de conexão

- **Sistema Multiagente**
  - Agente de Ingestão para processamento de PDFs
  - Cliente Gemini para análise semântica
  - Orquestrador para coordenação de fluxo de trabalho
  - Processamento assíncrono via Web Workers

- **Geração de Conteúdo Avançado**
  - Formatação rica em Markdown com frontmatter YAML
  - Diagramas Mermaid automáticos (mapas mentais, fluxogramas, timelines)
  - Formatação LaTeX para expressões matemáticas
  - Suporte a ícones via plugin Iconize
  - Tabelas estruturadas para metadados

- **Interface de Usuário Moderna**
  - Modal de progresso com indicadores visuais de etapas
  - Seletor de arquivos avançado com drag & drop
  - Preview de PDFs antes do processamento
  - Lista de PDFs existentes no vault
  - Feedback visual em tempo real

- **Configurações Abrangentes**
  - Aba de configurações integrada ao Obsidian
  - Controle granular sobre conteúdo gerado
  - Configuração de pasta de saída personalizada
  - Opções de formatação (LaTeX, Mermaid, ícones)
  - Preparação para funcionalidades OCR futuras

- **Comandos e Integração**
  - Ícone na ribbon para acesso rápido
  - Comandos na paleta (Ctrl+P)
  - Detecção automática de PDFs via drag & drop
  - Processamento de arquivo ativo
  - Teste de conexão com Gemini

- **Arquitetura Robusta**
  - TypeScript com tipagem completa
  - Tratamento abrangente de erros
  - Sistema de logs detalhado
  - Compilação otimizada com esbuild
  - Estrutura modular e extensível

### Técnico
- **Dependências Principais**
  - `@google/generative-ai`: ^0.21.0
  - `pdfjs-dist`: ^4.0.379
  - `obsidian`: ^1.2.5
  - `typescript`: ^5.7.2
  - `esbuild`: ^0.25.0

- **Estrutura do Projeto**
  ```
  src/
  ├── main.ts              # Classe principal do plugin
  ├── settings.ts          # Interface de configurações
  ├── types.ts             # Definições TypeScript
  ├── web-worker.ts        # Processamento assíncrono
  ├── agents/              # Agentes especializados
  │   ├── geminiClient.ts  # Cliente da API Gemini
  │   ├── ingestionAgent.ts # Extração de PDF
  │   └── orchestrator.ts  # Coordenação dos agentes
  ├── utils/               # Utilitários
  │   ├── markdownFormatter.ts # Formatação de saída
  │   ├── diagramGenerator.ts  # Geração de diagramas
  │   └── latexFormatter.ts    # Formatação LaTeX
  └── ui/                  # Interface de usuário
      ├── progressModal.ts # Modal de progresso
      └── fileSelector.ts  # Seletor de arquivos
  ```

- **Recursos de Desenvolvimento**
  - Sistema de testes automatizados
  - Scripts de build e desenvolvimento
  - Configuração ESLint e Prettier
  - Documentação técnica completa

### Segurança
- Armazenamento seguro de chaves da API
- Validação de entrada para todos os dados do usuário
- Processamento local de PDFs (sem envio para serviços externos)
- Controle total do usuário sobre dados enviados para Gemini

## [Não Lançado]

### Planejado para v1.1.0
- **OCR para PDFs Escaneados**
  - Integração com Tesseract.js para processamento local
  - Suporte a serviços de OCR em nuvem
  - Detecção automática de PDFs que precisam de OCR

- **Processamento em Lote**
  - Seleção múltipla de arquivos
  - Processamento paralelo otimizado
  - Relatório de progresso consolidado

- **Templates Personalizáveis**
  - Editor de templates de saída
  - Biblioteca de templates pré-definidos
  - Variáveis dinâmicas para personalização

### Planejado para v1.2.0
- **Suporte a Múltiplos Formatos**
  - Documentos DOCX
  - Arquivos de texto simples
  - Páginas web (via URL)

- **Integração com Outros LLMs**
  - Suporte a OpenAI GPT
  - Integração com Claude (Anthropic)
  - Sistema de fallback entre modelos

- **Análise Avançada**
  - Análise de sentimento
  - Detecção de tópicos
  - Extração de entidades nomeadas

### Planejado para v2.0.0
- **Interface Gráfica Avançada**
  - Painel lateral dedicado
  - Editor visual de notas
  - Preview em tempo real

- **Colaboração**
  - Compartilhamento de templates
  - Sincronização de configurações
  - Comentários e anotações colaborativas

- **Integração com Bases de Conhecimento**
  - Conexão com Notion
  - Integração com Roam Research
  - Sincronização com Zotero

## Problemas Conhecidos

### v1.0.0
- PDFs com proteção por senha não são suportados
- Arquivos muito grandes (>50MB) podem causar lentidão
- OCR ainda não implementado para PDFs escaneados
- Processamento limitado a um arquivo por vez

### Limitações Técnicas
- Dependente de conexão com internet para API Gemini
- Requer chave da API Google (gratuita com limites)
- Processamento pode ser lento para documentos muito longos

## Migração

### De Versões Beta
Se você estava usando uma versão beta ou de desenvolvimento:

1. **Backup**: Faça backup de suas configurações e notas importantes
2. **Desinstalar**: Remova a versão antiga completamente
3. **Instalar**: Siga o guia de instalação para v1.0.0
4. **Reconfigurar**: Insira novamente sua chave da API Gemini

### Compatibilidade
- **Obsidian**: Requer versão 0.15.0 ou superior
- **Node.js**: Requer versão 16 ou superior para desenvolvimento
- **Navegadores**: Compatível com Chromium, Firefox e Safari

## Contribuições

### v1.0.0 - Equipe de Desenvolvimento
- **Manus AI**: Desenvolvimento principal, arquitetura e documentação
- **Comunidade Obsidian**: Feedback e testes beta
- **Google**: API Gemini e documentação

### Agradecimentos Especiais
- Equipe do Obsidian pelo excelente framework de plugins
- Comunidade open source pelas bibliotecas utilizadas
- Beta testers que forneceram feedback valioso

---

Para mais informações sobre cada versão, consulte as [releases no GitHub](https://github.com/seu-usuario/obsidian-codex-plugin/releases).

