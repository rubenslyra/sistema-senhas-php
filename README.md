# Recursos do Projeto e Plano de Desenvolvimento

## 🔍 Visão Geral do Projeto

O Sistema de Gerenciamento de Senhas é uma aplicação completa para controle de filas de atendimento bancário, desenvolvido com PHP 8.4 e utilizando arquivos de texto como armazenamento temporário de dados. O projeto serve como um estudo de caso educacional para demonstrar os recursos modernos do PHP e boas práticas de programação.

## 📑 Requisitos Funcionais

1. **Geração de Senhas**
   - Gerar senhas normais (N001, N002, etc.)
   - Gerar senhas prioritárias (P001, P002, etc.)
   - Gerar senhas preferenciais (E001, E002, etc.)
   - Imprimir comprovante com data/hora e número estimado de espera

2. **Painel de Atendimento**
   - Listar senhas aguardando atendimento
   - Chamar próxima senha (respeitando prioridades)
   - Redirecionar senhas entre guichês
   - Visualizar histórico de senhas atendidas

3. **Gerenciamento de Atendimentos**
   - Iniciar atendimento
   - Pausar atendimento (cliente ausente)
   - Finalizar atendimento
   - Cancelar senha
   - Registrar motivo do atendimento

4. **Estatísticas e Relatórios**
   - Tempo médio de espera
   - Tempo médio de atendimento
   - Total de senhas por tipo
   - Taxa de senhas não atendidas
   - Desempenho por atendente/guichê
   - Gráficos de fluxo por horário

## 📋 Etapas de Desenvolvimento

### Fase 1: Configuração e Base (Implementado)
- [x] Arquivo de configurações globais
- [x] Classe para manipulação de arquivos
- [x] Estrutura básica de diretórios
- [x] Sistema de logging

### Fase 2: Core do Sistema (Implementado)
- [x] Classe para gerenciamento de senhas
- [x] Métodos para criação, chamada e finalização de senhas
- [x] Algoritmo de priorização de atendimento
- [x] Cálculo de estatísticas básicas

### Fase 3: Interface Web (Implementado)
- [x] Layout responsivo básico
- [x] Formulários para operações principais
- [x] Exibição de estatísticas
- [x] Sistema de mensagens e alertas

### Fase 4: Recursos Avançados (A Implementar)
- [ ] Autenticação de operadores
- [ ] Painel de chamadas em tempo real
- [ ] Geração de relatórios em PDF
- [ ] Tela para monitor de TV
- [ ] Backup automático de dados

### Fase 5: Migração para Banco de Dados (Futura)
- [ ] Modelagem do banco de dados
- [ ] Criação de camada de abstração (DAO)
- [ ] Scripts de migração de dados
- [ ] Refatoração para suporte a transações

## 🛠️ Técnicas e Recursos de PHP 8.4 Aplicados

1. **Union Types**
   ```php
   public function readLines(string $filename): array|false {...}
   ```

2. **Promoted Properties**
   ```php
   public function __construct(
       private string $dataDir = DIR_DATA,
       private bool $useCompression = false
   ) {...}
   ```

3. **Named Arguments**
   ```php
   $ticket = $ticketSystem->generateTicket(
       ticketType: TICKET_TYPE_PREFERENTIAL,
       includeEstimatedTime: true
   );
   ```

4. **Nullsafe Operator**
   ```php
   $username = $user?->profile?->getFullName() ?? 'Visitante';
   ```

5. **Match Expression**
   ```php
   $className = match($ticket['status']) {
       STATUS_WAITING => 'waiting',
       STATUS_CALLED => 'called',
       STATUS_FINISHED => 'finished',
       default => 'unknown',
   };
   ```

6. **Weak Maps**
   ```php
   $ticketCache = new WeakMap();
   $ticketCache[$ticket] = $calculatedStats;
   ```

7. **First-class Callable Syntax**
   ```php
   $formatDate = date(...);
   $formatted = $formatDate(DATETIME_FORMAT);
   ```

## 📊 Estrutura de Dados

### users.txt
```json
{"id":1,"username":"admin","password_hash":"$2y$10$..","name":"Administrador","role":"admin","last_login":"2024-02-28 14:30:00"}
{"id":2,"username":"atendente1","password_hash":"$2y$10$..","name":"João Silva","role":"attendant","last_login":"2024-02-28 09:15:22"}
```

### tickets.txt
```json
{"code":"N001","type":1,"status":"finished","created_at":"2024-02-28 08:30:45","called_at":"2024-02-28 08:35:12","finished_at":"2024-02-28 08:40:33","counter_number":3}
{"code":"P001","type":2,"status":"called","created_at":"2024-02-28 08:45:22","called_at":"2024-02-28 08:47:05","finished_at":"","counter_number":1}
{"code":"E001","type":3,"status":"waiting","created_at":"2024-02-28 08:50:18","called_at":"","finished_at":"","counter_number":null}
```

### counters.txt
```json
{"1":45,"2":12,"3":8}
```

## 🎯 Metas de Aprendizado

1. **Dominar PHP 8.4**
   - Utilizar todos os novos recursos relevantes
   - Compreender melhorias de performance
   - Aplicar tipagem de forma eficiente

2. **Boas Práticas de Codificação**
   - PSR-12 para estilo de código
   - Documentação PHPDoc completa
   - Separação de responsabilidades
   - Princípios SOLID

3. **Manipulação Eficiente de Arquivos**
   - Performance em operações de I/O
   - Prevenção de race conditions
   - Técnicas de caching
   - Tratamento de erros robusto

4. **Interface Web Responsiva**
   - Layout flexível e adaptável
   - Padrões de design moderno
   - Acessibilidade básica
   - Experiência de usuário intuitiva

5. **Segurança e Validação**
   - Validação de entrada rigorosa
   - Prevenção de injeção
   - Tratamento seguro de arquivos
   - Proteção contra ataques comuns

## 🔄 Ciclo de Desenvolvimento

1. **Planejamento Iterativo**
   - Definição de pequenos incrementos funcionais
   - Priorização de features por valor educacional
   - Documentação por funcionalidade

2. **Desenvolvimento Guiado por Testes**
   - Testes manuais estruturados
   - Verificação de cada funcionalidade
   - Validação de casos de borda

3. **Refatoração Constante**
   - Melhoria de código existente
   - Eliminação de duplicações
   - Simplificação de lógicas complexas

4. **Integração e Validação**
   - Testes integrados de fluxos completos
   - Verificação de performance
   - Validação de requisitos

## 📚 Evolução de Conhecimentos

O projeto foi estruturado para evoluir o aprendizado em níveis incrementais:

### Nível 1: Fundamentos
- Sintaxe básica do PHP 8.4
- Manipulação simples de arquivos
- Conceitos básicos de OOP

### Nível 2: Construção do Core
- Classes e objetos avançados
- Design de API
- Algoritmos e estruturas de dados

### Nível 3: Interface e Experiência
- Integração front-end/back-end
- Formulários e processamento
- Validação e feedback

### Nível 4: Conceitos Avançados
- Padrões de design
- Performance e otimização
- Segurança e resiliência
