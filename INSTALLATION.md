# Guia de Instalação - Plugin Codex

Este guia fornece instruções detalhadas para instalar e configurar o Plugin Codex no Obsidian.

## Pré-requisitos

### Software Necessário
- **Obsidian**: Versão 0.15.0 ou superior
- **Chave da API Google Gemini**: Gratuita em [Google AI Studio](https://makersuite.google.com/app/apikey)

### Plugins Recomendados (Opcionais)
- **Iconize**: Para exibir ícones nas notas geradas
- **LaTeX Suite**: Para edição avançada de equações matemáticas
- **Mermaid**: Para renderização de diagramas (geralmente já incluído no Obsidian)

## Métodos de Instalação

### Método 1: Instalação Manual (Recomendado para Desenvolvimento)

#### Passo 1: Baixar o Plugin
1. Baixe ou clone este repositório
2. Extraia os arquivos se necessário

#### Passo 2: Localizar a Pasta de Plugins
1. Abra o Obsidian
2. Vá para **Configurações** → **Sobre**
3. Clique em **Mostrar pasta do cofre**
4. Navegue até a pasta `.obsidian/plugins/`
5. Se a pasta `plugins` não existir, crie-a

#### Passo 3: Instalar o Plugin
1. Copie a pasta do plugin para `.obsidian/plugins/obsidian-codex/`
2. Abra um terminal na pasta do plugin
3. Execute os seguintes comandos:
   ```bash
   npm install
   npm run build
   ```

#### Passo 4: Ativar o Plugin
1. No Obsidian, vá para **Configurações** → **Plugins da comunidade**
2. Certifique-se de que "Plugins da comunidade" estão habilitados
3. Encontre "Codex - AI Document Processor" na lista
4. Ative o plugin usando o botão de alternância

### Método 2: Via BRAT (Beta Reviewers Auto-update Tool)

#### Passo 1: Instalar BRAT
1. No Obsidian, vá para **Configurações** → **Plugins da comunidade**
2. Procure por "BRAT" e instale-o
3. Ative o plugin BRAT

#### Passo 2: Adicionar o Plugin Codex
1. Abra as configurações do BRAT
2. Clique em "Add Beta plugin"
3. Cole a URL do repositório: `https://github.com/seu-usuario/obsidian-codex-plugin`
4. Clique em "Add Plugin"

#### Passo 3: Ativar o Plugin
1. Vá para **Configurações** → **Plugins da comunidade**
2. Encontre "Codex - AI Document Processor"
3. Ative o plugin

### Método 3: Instalação via Release (Futuro)

*Este método estará disponível quando o plugin for aprovado na loja oficial do Obsidian.*

## Configuração Inicial

### 1. Obter Chave da API Gemini

#### Passo 1: Acessar Google AI Studio
1. Vá para [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Faça login com sua conta Google
3. Clique em "Create API Key"
4. Escolha um projeto existente ou crie um novo
5. Copie a chave gerada

#### Passo 2: Configurar no Plugin
1. No Obsidian, vá para **Configurações** → **Codex**
2. Cole sua chave da API no campo "Chave da API Gemini"
3. Escolha o modelo (recomendado: Gemini 2.5 Flash)
4. Clique em "Salvar"

### 2. Testar a Conexão

1. Use o comando **Ctrl+P** (ou **Cmd+P** no Mac)
2. Digite "Testar Conexão com Gemini"
3. Execute o comando
4. Verifique se aparece a mensagem de sucesso

### 3. Configurar Preferências

#### Pasta de Saída
- Defina onde as notas geradas serão salvas
- Padrão: "Codex Generated Notes"

#### Conteúdo das Notas
- **Resumo**: Gera resumo executivo do documento
- **Conceitos-Chave**: Extrai e categoriza conceitos importantes
- **Perguntas e Respostas**: Cria Q&A educativo
- **Diagramas Mermaid**: Gera visualizações (mapas mentais, fluxogramas)
- **Fórmulas LaTeX**: Formata expressões matemáticas
- **Ícones**: Adiciona ícones às notas (requer plugin Iconize)

#### OCR (Futuro)
- **Habilitar OCR**: Para PDFs escaneados
- **Provedor**: Tesseract (local) ou serviços em nuvem

## Verificação da Instalação

### Teste Básico
1. Clique no ícone do Codex na barra lateral (ícone de documento)
2. Se o modal de seleção de arquivo aparecer, a instalação foi bem-sucedida

### Teste Completo
1. Prepare um PDF pequeno (1-5 páginas)
2. Use o plugin para processá-lo
3. Verifique se a nota é gerada corretamente

## Solução de Problemas

### Plugin Não Aparece na Lista
- **Causa**: Pasta incorreta ou arquivos ausentes
- **Solução**: 
  1. Verifique se a pasta está em `.obsidian/plugins/obsidian-codex/`
  2. Certifique-se de que `manifest.json` e `main.js` estão presentes
  3. Reinicie o Obsidian

### Erro "Chave da API Inválida"
- **Causa**: Chave incorreta ou sem permissões
- **Solução**:
  1. Verifique se a chave foi copiada corretamente
  2. Confirme que a API Gemini está habilitada no Google Cloud
  3. Teste a conexão usando o comando específico

### Plugin Não Compila
- **Causa**: Dependências ausentes ou versão do Node.js incompatível
- **Solução**:
  1. Certifique-se de ter Node.js 16+ instalado
  2. Execute `npm install` novamente
  3. Tente `npm run build` em modo verbose: `npm run build -- --verbose`

### Processamento Muito Lento
- **Causa**: PDF muito grande ou conexão lenta
- **Solução**:
  1. Use PDFs menores (< 20 páginas) para teste
  2. Verifique sua conexão com a internet
  3. Considere usar o modelo Gemini Flash em vez do Pro

### Erro de Memória
- **Causa**: PDF muito grande ou muitos processamentos simultâneos
- **Solução**:
  1. Processe um PDF por vez
  2. Reinicie o Obsidian se necessário
  3. Use PDFs menores

## Atualizações

### Via BRAT
- O BRAT atualizará automaticamente o plugin quando houver novas versões

### Manual
1. Baixe a nova versão
2. Substitua os arquivos na pasta do plugin
3. Execute `npm run build` se necessário
4. Reinicie o Obsidian

## Desinstalação

### Remover Plugin
1. Vá para **Configurações** → **Plugins da comunidade**
2. Desative o plugin Codex
3. Exclua a pasta `.obsidian/plugins/obsidian-codex/`

### Limpar Dados
- As notas geradas permanecerão no seu vault
- As configurações serão removidas automaticamente

## Suporte

### Recursos de Ajuda
- **Documentação**: README.md no repositório
- **Issues**: [GitHub Issues](https://github.com/seu-usuario/obsidian-codex-plugin/issues)
- **Discussões**: [GitHub Discussions](https://github.com/seu-usuario/obsidian-codex-plugin/discussions)

### Comunidade
- **Discord**: Canal #plugin-dev no servidor oficial do Obsidian
- **Forum**: Seção de plugins da comunidade

### Relatório de Bugs
Ao reportar problemas, inclua:
1. Versão do Obsidian
2. Versão do plugin
3. Sistema operacional
4. Passos para reproduzir o erro
5. Logs do console (F12 → Console)

---

**Desenvolvido com ❤️ por Manus AI**

