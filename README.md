# Nosdu Controle Financeiro - PWA Edition

## 📱 Sobre o Aplicativo

**Nosdu** é um aplicativo de controle financeiro pessoal que funciona completamente offline, com armazenamento nativo de dados no seu dispositivo. Agora com suporte completo a **Progressive Web App (PWA)**, permitindo instalação direta na tela inicial.

## ✨ Recursos PWA Implementados

### 1. **Instalação na Tela Inicial**
- Adicione o app à tela inicial do seu dispositivo
- Funciona como um aplicativo nativo
- Acesso rápido sem abrir o navegador

### 2. **Modo Offline Completo**
- Service Worker registrado para cache de arquivos
- Funciona 100% offline após primeiro acesso
- Sincronização automática quando online

### 3. **Tela Inicial (Splash Screen)**
- Animação profissional ao iniciar o app
- Logo animado com efeito bounce
- Indicador de carregamento elegante
- Desaparece automaticamente após 2.5 segundos

### 4. **Armazenamento Local**
- IndexedDB para dados estruturados
- LocalStorage como fallback
- Backup e restauração de dados
- Persistência de dados entre sessões

### 5. **Ícones Responsivos**
- Ícone de 192x192px para tela inicial
- Ícone de 512x512px para splash screens
- Suporte a ícones maskable para Android

## 📁 Arquivos Inclusos

```
nosdu_pwa/
├── index.html              # Aplicativo principal (HTML + CSS + JS)
├── manifest.json           # Configuração PWA
├── service-worker.js       # Service Worker para cache
├── icon-192.png           # Ícone 192x192px
├── icon-512.png           # Ícone 512x512px
└── README.md              # Esta documentação
```

## 🚀 Como Usar

### Instalação no Navegador

#### **Android (Chrome/Firefox)**
1. Abra o arquivo `index.html` no navegador
2. Toque no menu (⋮) → "Instalar aplicativo"
3. Confirme a instalação
4. O app aparecerá na tela inicial

#### **iOS (Safari)**
1. Abra o arquivo `index.html` no Safari
2. Toque em Compartilhar (↗️)
3. Selecione "Adicionar à Tela Inicial"
4. Nomeie como "Nosdu" e confirme

#### **Desktop (Chrome/Edge)**
1. Abra o arquivo `index.html`
2. Clique no ícone de instalação (⬇️) na barra de endereço
3. Confirme a instalação
4. O app abrirá em uma janela separada

### Hospedagem Online

Para usar o PWA online, hospede os arquivos em um servidor HTTPS:

```bash
# Exemplo com Python
python -m http.server 8000

# Exemplo com Node.js
npx http-server -p 8000
```

Acesse via `https://seu-dominio.com`

## 💾 Funcionalidades Principais

### Gerenciamento de Entradas e Saídas
- Adicione entradas de dinheiro (salários, recebimentos)
- Registre saídas (gastos, despesas)
- Categorize automaticamente
- Adicione descrições para "Outros" itens

### Relatórios e Análises
- Resumo mensal com saldo total
- Gráficos de entradas por categoria
- Gráficos de saídas por categoria
- Timeline com últimas 10 movimentações

### Backup e Restauração
- Exporte seus dados para arquivo JSON
- Restaure dados de backups anteriores
- Proteção contra perda de dados

### Modo Offline
- Funciona completamente sem internet
- Dados sincronizados quando online
- Acesso rápido via ícone na tela inicial

## 🔧 Configuração Técnica

### Manifest.json
Define as propriedades do PWA:
- Nome e ícones do aplicativo
- Cor de tema (#2563eb - Azul)
- Modo de exibição standalone
- Orientação portrait

### Service Worker
Implementa estratégia "Cache First":
- Arquivos em cache são servidos primeiro
- Fallback para rede se não estiver em cache
- Limpeza automática de caches antigos

### Splash Screen
Animações CSS com:
- Logo com efeito bounce
- Barra de carregamento animada
- Fade out automático após 2.5s
- Compatível com todos os navegadores

## 📊 Dados Armazenados

Os dados são salvos localmente em:
- **IndexedDB**: Armazenamento principal (estruturado)
- **LocalStorage**: Backup de configurações

Estrutura de dados:
```javascript
{
  entradas: [
    {
      id: timestamp,
      valor: number,
      desc: string,
      cat: string,
      data: YYYY-MM-DD,
      hora: HH:MM,
      timestamp: milliseconds
    }
  ],
  saidas: [...],
  mesReferencia: "YYYY-MM",
  historicoMensal: [...]
}
```

## 🎨 Tema e Cores

O aplicativo usa um tema escuro profissional:
- **Fundo Primário**: #0f172a
- **Fundo Secundário**: #020617
- **Azul Destaque**: #2563eb
- **Verde (Entradas)**: #22c55e
- **Vermelho (Saídas)**: #ef4444
- **Laranja (Avisos)**: #d97706

## 🔒 Segurança

- Dados armazenados localmente no dispositivo
- Sem envio de dados para servidores externos
- Confirmação de segurança antes de zerar dados
- Backup manual para proteção adicional

## 📱 Compatibilidade

| Navegador | Android | iOS | Desktop |
|-----------|---------|-----|---------|
| Chrome | ✅ | ✅ | ✅ |
| Firefox | ✅ | ⚠️ | ✅ |
| Safari | ⚠️ | ✅ | ✅ |
| Edge | ✅ | ✅ | ✅ |

✅ = Suporte completo | ⚠️ = Suporte parcial

## 🐛 Troubleshooting

### App não instala
- Certifique-se de usar HTTPS (em produção)
- Limpe o cache do navegador
- Tente em outro navegador

### Dados não sincronizam
- Verifique a conexão com internet
- Limpe o cache do service worker
- Reinstale o aplicativo

### Splash screen não desaparece
- Atualize a página
- Limpe o cache do navegador
- Verifique o console para erros

## 📝 Licença

Este aplicativo é fornecido como está, para uso pessoal.

## 🤝 Suporte

Para problemas ou sugestões, verifique:
- Console do navegador (F12 → Console)
- Dados armazenados (F12 → Application)
- Service Worker status (F12 → Application → Service Workers)

---

**Versão**: 2.0 PWA Edition  
**Última Atualização**: 2026  
**Status**: ✅ Pronto para Produção
