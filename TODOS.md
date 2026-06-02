# Guia de Configuração - 2ª Avaliação GTIC

## 1. Empresa e Cenário

Elaborar um documento de contexto da empresa fictícia contendo, no mínimo, meia página.

### Informações obrigatórias

* Nome da empresa
* Segmento de mercado
* Porte da organização (pequena, média ou grande)
* Estrutura organizacional (áreas e departamentos)
* Localizações físicas (matriz e filiais)
* Resumo da infraestrutura de TI
* Equipe de TI com cargos e responsabilidades

## 2. Estrutura de Entidades

### Quantidade mínima

* 1 entidade raiz (empresa principal)
* 2 subentidades

**Total:** 3 entidades

### Requisitos

Cada entidade deve possuir:

* Nome
* Endereço
* Dados básicos preenchidos

Além disso:

* Usuários devem estar vinculados às entidades corretas.
* Ativos devem estar associados às entidades correspondentes.
* A hierarquia deve refletir o cenário organizacional definido.

## 3. Usuários, Perfis e Grupos

### Usuários

Cadastrar:

* 8 usuários

Cada usuário deve possuir:

* Nome
* E-mail
* Entidade vinculada

### Perfis de acesso

Criar os seguintes perfis:

| Perfil                    | Permissões                            |
| ------------------------- | ------------------------------------- |
| Administrador de TI       | Acesso total ao sistema               |
| Técnico de Suporte        | Gestão de chamados e ativos           |
| Usuário Final (Requester) | Abertura e acompanhamento de chamados |

### Grupos

Criar grupos de usuários, por exemplo:

* Suporte N1
* Suporte N2
* Gestão

Distribuir corretamente os usuários entre:

* Perfis
* Grupos
* Entidades

## 4. Catálogo de Serviços

### Categorias

Criar:

* 3 categorias de serviços

Cada categoria deve conter:

* Nome
* Descrição

### Itens de serviço

Cadastrar:

* 15 itens de serviço

Cada item deve possuir:

* Nome
* Descrição
* Tipo:

  * Incidente
  * Requisição

### Formulários

Criar:

* 2 formulários personalizados

Os formulários devem estar vinculados a itens do catálogo.

## 5. Gestão de Ativos (CMDB)

### Quantidade mínima de ativos

| Tipo                            | Quantidade |
| ------------------------------- | ---------- |
| Computadores (desktop/notebook) | 6          |
| Impressoras ou periféricos      | 2          |
| Equipamentos de rede            | 2          |
| Servidor (físico ou virtual)    | 1          |

**Total mínimo:** 15 ativos

### Informações obrigatórias

Cada ativo deve possuir:

* Tipo
* Nome
* Número de série ou patrimônio
* Localização
* Usuário responsável
* Status

### Software e licenciamento

Cadastrar softwares contendo:

* Quantidade de licenças
* Data de validade das licenças

### Relacionamentos

* Vincular pelo menos 3 ativos a chamados existentes.

## 6. SLA e OLA

### SLAs

| Prioridade | Tempo de Resposta | Tempo de Resolução |
| ---------- | ----------------- | ------------------ |
| Crítico    | 30 minutos        | 4 horas            |
| Alta       | 1 hora            | 8 horas            |
| Normal     | 4 horas           | 24 horas           |

### Configurações adicionais

* Configurar calendário de atendimento.
* Associar o calendário aos SLAs.
* Criar 1 regra de escalonamento.
* Configurar notificação por e-mail para violações de SLA.
* Associar os SLAs aos itens do catálogo de serviços.

## 7. Gestão de Chamados

### Quantidade mínima

Cadastrar:

* 15 chamados

Distribuição mínima:

* 6 incidentes
* 4 requisições de serviço

### Estados obrigatórios

Os chamados devem contemplar os estados:

* Novo
* Em Atendimento
* Pendente
* Resolvido
* Fechado

### Relacionamentos

Todos os chamados devem estar vinculados a:

* Um item do catálogo de serviços
* Um ativo

### Requisitos adicionais

Criar:

* 1 chamado com escalonamento (troca de técnico ou grupo)
* 1 Problema relacionado a incidentes recorrentes

> **Observação:** a rubrica menciona 10 chamados em alguns trechos, porém o requisito mais restritivo exige 15. Foi adotado o valor maior.

## 8. Base de Conhecimento

### Artigos

Publicar:

* 4 artigos

Cada artigo deve possuir:

* Título
* Conteúdo descritivo
* Palavras-chave

### Organização

Criar:

* 2 categorias de conhecimento

### Relacionamentos

* Pelo menos 1 artigo deve estar vinculado a um chamado resolvido.

### Visibilidade

Definir para cada artigo:

* Público
* Restrito a técnicos

## 9. Relatório Técnico

O relatório deve conter:

### Identificação da equipe

* Nome dos integrantes
* Matrícula dos integrantes

### Descrição do projeto

* Empresa fictícia
* Cenário utilizado

### Execução

* Dificuldades encontradas
* Soluções adotadas

### Conclusão

* Aprendizados obtidos
* Considerações finais sobre o projeto

## 10. Entrega Final

Enviar ao professor:

* Link do ambiente GLPI funcional
* Login de acesso
* Senha de acesso
* Relatório técnico em anexo

## Resumo dos Entregáveis

| Item                               | Quantidade |
| ---------------------------------- | ---------- |
| Entidades                          | 3          |
| Usuários                           | 8          |
| Perfis                             | 3          |
| Categorias de Serviço              | 3          |
| Itens de Serviço                   | 15         |
| Formulários Personalizados         | 2          |
| Ativos                             | 15         |
| SLAs                               | 3          |
| Regras de Escalonamento            | 1          |
| Chamados                           | 15         |
| Problemas                          | 1          |
| Artigos da Base de Conhecimento    | 4          |
| Categorias da Base de Conhecimento | 2          |
