# 📦 Logística Master - Sistema de Gestão de Ponto e Ocorrências

![Versão](https://img.shields.io/badge/versão-20.0-blue)
![Licença](https://img.shields.io/badge/licença-MIT-green)
![Plataforma](https://img.shields.io/badge/plataforma-web-orange)

Sistema completo de gestão logística para controle de ponto eletrônico, tarefas, ocorrências (CIEs) e dashboard gerencial. Funciona 100% no navegador, sem necessidade de servidor ou banco de dados.

## 📋 Índice

- [Funcionalidades](#-funcionalidades)
- [Capturas de Tela](#-capturas-de-tela)
- [Como Usar](#-como-usar)
- [Instalação](#-instalação)
- [Backup e Compartilhamento](#-backup-e-compartilhamento)
- [Estrutura de Dados](#-estrutura-de-dados)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Compatibilidade](#-compatibilidade)
- [Solução de Problemas](#-solução-de-problemas)
- [Contribuição](#-contribuição)
- [Licença](#-licença)

## ✨ Funcionalidades

### 📊 Dashboard
- Visão geral da equipe (total, presentes, atrasados, ausentes)
- Resumo de ausências por motivo
- Estatísticas de tarefas (total, pendentes, concluídas)
- Estatísticas de CIEs (total, hoje, abertas)
- Alertas de limite por função
- Alertas de CIEs críticas com animação

### ⏰ Ponto Diário
- Registro de ponto por funcionário
- Status: Presente, Atraso, Falta, Atestado, Licença, Férias, Serviço externo
- Campo para tempo de atraso (minutos)
- Filtro por nome/função
- Virada de dia automática com salvamento em histórico

### ✅ Tarefas
- Criação de tarefas com responsável
- Prioridade (Baixa, Média, Alta)
- Status (Pendente, Em andamento, Concluída)
- Data de criação automática
- Reset automático para pendente no novo dia

### 👥 Equipe
- Cadastro completo de funcionários
- Matrícula única
- Funções: Motorista, Motociclista, Pedestre, Bicicleta, Interno, Gestão
- Remoção de funcionários

### ⚠️ CIEs (Ocorrências)
- Registro de ocorrências com número de CIE
- Tipos: Acidente, Avaria, Atraso, Falta, Problema, Outros
- Níveis de impacto: Baixo, Médio, Alto, Crítico
- Vinculação com funcionário
- Status: Aberta/Resolvida
- Filtros por tipo e busca
- Alertas visuais para CIEs críticas no dashboard

### 📜 Histórico
- Consulta por data específica
- Consulta por funcionário
- Botão "Hoje" para acesso rápido
- Visualização agrupada por data
- Estatísticas de presentes/ausentes por dia

### ⚙️ Configurações
- Limites de ausência por função
- Backup e compartilhamento
- Compactação de dados
- Limpeza de histórico antigo (>30 dias)
- Modo escuro automático

## 📱 Capturas de Tela

### Desktop
```
┌─────────────────────────────────────────────┐
│  LOGÍSTICA MASTER                           │
│  ┌─────┐  ┌────────────── Dashboard ──────┐ │
│  │Menu │  │  Total  Presentes  Atrasos    │ │
│  │     │  │  [12]      [8]       [2]      │ │
│  │     │  │  Ausentes: 2                   │ │
│  │     │  └────────────────────────────────┘ │
│  │     │  ┌────────── Tarefas ───────────┐ │
│  │     │  │  Total: 5 | Pendentes: 3     │ │
│  │     │  └────────────────────────────────┘ │
└─────────────────────────────────────────────┘
```

### Mobile
```
┌─────────────────┐
│ LOGÍSTICA MASTER│
│ ┌─┐ ┌─┐ ┌─┐ ┌─┐│
│ │P│ │T│ │C│ │E││
│ └─┘ └─┘ └─┘ └─┘│
│ 📊 Dashboard    │
│ Total: 12       │
│ Presentes: 8    │
└─────────────────┘
```

## 🚀 Como Usar

### Acesso Direto
1. Abra o arquivo `gestao_logistica.html` em qualquer navegador moderno
2. Todos os dados são salvos automaticamente no `localStorage`
3. Navegue pelas abas usando o menu lateral

### Primeiros Passos
1. **Cadastre a equipe** na aba "Equipe"
2. **Registre o ponto** na aba "Ponto"
3. **Crie tarefas** na aba "Tarefas"
4. **Registre ocorrências** na aba "CIEs"
5. **Acompanhe tudo** no Dashboard

## 💾 Instalação

### Opção 1: Download Direto
```bash
# Clone ou baixe o arquivo
wget https://exemplo.com/gestao_logistica.html

# Abra no navegador
firefox gestao_logistica.html
```

### Opção 2: Servidor Local
```bash
# Com Python
python -m http.server 8000
# Acesse: http://localhost:8000

# Com Node.js
npx http-server
# Acesse: http://localhost:8080
```

### Opção 3: PWA (Progressive Web App)
- Abra no Chrome/Edge
- Clique em "Instalar aplicativo" na barra de endereços
- Use como app nativo no desktop/celular

## 🔄 Backup e Compartilhamento

### Exportar Backup
1. Vá em **Configurações** > **Backup e Compartilhamento**
2. Clique em **Exportar Backup**
3. O arquivo será salvo como `LOGISTICA_BACKUP_YYYY-MM-DD_HH-MM.json`

### Compartilhar
1. Clique em **Compartilhar**
2. Escolha:
   - **WhatsApp**: Envia via app
   - **E-mail**: Abre cliente de email
   - **Copiar**: Copia JSON para área de transferência
   - **Download**: Salva localmente

### Importar Backup
1. Clique em **Importar**
2. Selecione o arquivo `.json` do backup
3. Confirme a restauração
4. A página recarrega automaticamente

## 📁 Estrutura de Dados

```javascript
// Exemplo de backup
{
  "db_equipe": [
    {
      "nome": "João Silva",
      "mat": "001",
      "fun": "Motorista"
    }
  ],
  "db_tarefas": [
    {
      "desc": "Entregar mercadoria",
      "resp": "João Silva",
      "prioridade": "Alta",
      "status": "Pendente",
      "dataCriacao": "2026-02-27"
    }
  ],
  "db_ponto": {
    "001": {
      "status": "Presente",
      "tempo": ""
    }
  },
  "db_limites": {
    "Motorista": 2,
    "Motociclista": 1
  },
  "db_historico": [
    {
      "data": "2026-02-26",
      "pontos": [
        {
          "nome": "João Silva",
          "status": "Presente",
          "tempo": ""
        }
      ]
    }
  ],
  "db_cies": [
    {
      "id": 123456789,
      "numero": "CIE-001",
      "tipo": "Acidente",
      "funcionario": "João Silva",
      "impacto": "Crítico",
      "descricao": "Descrição do ocorrido",
      "data": "2026-02-27",
      "hora": "14:30:00",
      "status": "Aberta"
    }
  ],
  "ultima_data": "2026-02-27",
  "versao": "1.0",
  "data_backup": "2026-02-27T14:30:00.000Z"
}
```

## 🛠 Tecnologias Utilizadas

- **HTML5** - Estrutura semântica
- **CSS3** - Estilização responsiva
- **JavaScript ES6+** - Lógica da aplicação
- **LocalStorage** - Persistência de dados
- **Font Awesome 6** - Ícones
- **Web Share API** - Compartilhamento nativo
- **PWA** - Instalável como app

## 🌐 Compatibilidade

| Navegador | Versão | Desktop | Mobile |
|-----------|--------|---------|--------|
| Chrome | 90+ | ✅ | ✅ |
| Firefox | 88+ | ✅ | ✅ |
| Edge | 90+ | ✅ | ✅ |
| Safari | 14+ | ✅ | ✅ |
| Opera | 76+ | ✅ | ✅ |

### Requisitos
- Navegador moderno com suporte a `localStorage`
- JavaScript habilitado
- Conexão com internet (apenas para ícones)

## 🔧 Solução de Problemas

### Dados não salvam
```javascript
// Verifique o espaço do localStorage
console.log('Espaço usado:', localStorage.length);
// Limpe histórico antigo nas configurações
```

### Backup não importa
1. Verifique se o arquivo é `.json`
2. Confirme que é um backup válido do sistema
3. Tente fazer download de um novo backup e importar

### Scroll no celular
- Use os botões flutuantes de navegação
- Arraste a barra de rolagem lateral
- Toque no topo da tela para voltar ao início

### Modo escuro
- O sistema segue a preferência do seu dispositivo
- Para forçar, altere as configurações do sistema

## 🤝 Contribuição

### Como contribuir
1. Faça um fork do projeto
2. Crie uma branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

### Sugestões de melhorias
- [ ] Gráficos visuais com Chart.js
- [ ] Exportação para PDF/Excel
- [ ] Integração com API externa
- [ ] Notificações push
- [ ] Login com níveis de acesso
- [ ] Fotos dos funcionários

## 📄 Licença

MIT License © 2026

Permissão é concedida, gratuitamente, a qualquer pessoa que obtenha uma cópia deste software e dos arquivos de documentação associados, para lidar com o Software sem restrições, incluindo, sem limitação, os direitos de usar, copiar, modificar, mesclar, publicar, distribuir, sublicenciar e/ou vender cópias do Software.

---

## 👨‍💻 Autor

Desenvolvido para gestão logística eficiente.

**Contato:** seu-email@exemplo.com

---

## ⭐ Agradecimentos

- Usuários que reportaram bugs e sugeriram melhorias
- Comunidade open source
- Font Awesome pelos ícones incríveis

---

**Logística Master** - Simplificando a gestão do seu dia a dia! 🚀
