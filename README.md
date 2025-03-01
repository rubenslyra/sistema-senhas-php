# Sistema de Gerenciamento de Senhas (PHP 8.4)

Um sistema completo para gerenciamento de senhas de atendimento bancário implementado em PHP 8.4, utilizando arquivos de texto para armazenamento de dados antes da integração com banco de dados.

## 🚀 Sobre o Projeto

Este projeto foi desenvolvido como um aplicativo educacional para demonstrar os fundamentos da programação em PHP 8.4, com foco em:

- Manipulação de arquivos de texto
- Programação orientada a objetos
- Gestão de configurações e constantes globais
- Tratamento de dados e operações CRUD
- Interface web simples e responsiva

O sistema simula um ambiente de gerenciamento de senhas para atendimento bancário, permitindo a geração de senhas normais, preferenciais e prioritárias, chamada de senhas nos guichês, finalização de atendimentos e visualização de estatísticas.

## 📋 Funcionalidades

- Geração de diferentes tipos de senhas (normal, prioritária, preferencial)
- Painel de chamada de senhas com suporte a múltiplos guichês
- Cancelamento e finalização de atendimentos
- Estatísticas de atendimento em tempo real
- Logs de sistema para auditoria e debugging
- Interface responsiva e amigável

## 🔧 Requisitos

- PHP 8.4 ou superior
- Servidor web (Apache, Nginx, etc.)
- Permissões de leitura/escrita para os diretórios do projeto

## 📦 Estrutura do Projeto

```
/
├── config.php             # Configurações e constantes globais
├── FileHandler.php        # Classe para manipulação de arquivos
├── TicketSystem.php       # Classe principal do sistema de senhas
├── index.php              # Interface principal do sistema
├── /data/                 # Diretório para armazenamento de dados
│   ├── users.txt          # Dados de usuários (operadores do sistema)
│   ├── tickets.txt        # Registro de senhas geradas
│   └── counters.txt       # Contadores do sistema
└── /logs/                 # Diretório para logs do sistema
    └── system.log         # Log principal do sistema
```

## 🛠️ Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/rubenslyra/sistema-senhas-php.git
   ```

2. Configure seu servidor web para apontar para o diretório do projeto

3. Certifique-se de que o PHP 8.4 está instalado e configurado corretamente

4. Verifique as permissões dos diretórios `/data` e `/logs` para permitir escrita

5. Acesse o sistema pelo navegador

## 📚 Tópicos de Aprendizado

Este projeto aborda os seguintes tópicos fundamentais de PHP 8.4:

- Tipos de retorno (union types)
- Named arguments
- Constructor property promotion
- Nullsafe operator
- Manipulação de arquivos
- Serialização e deserialização JSON
- Formatação de datas e números
- Classes e objetos
- Constantes e configurações globais
- Tratamento de requisições web
- Logging e debugging

## 🧪 Próximos Passos

- Implementação de autenticação de usuários
- Migração para banco de dados (MySQL/PostgreSQL)
- API REST para integração com outros sistemas
- Painel de chamadas em tempo real com WebSockets
- Adição de recursos de acessibilidade

## 📄 Licença

Este projeto está sob a licença MIT - veja o arquivo [LICENSE.md](LICENSE.md) para detalhes.

## ✒️ Autor

* **Rubens Lyra** - [rubenslyra](https://github.com/rubenslyra)
