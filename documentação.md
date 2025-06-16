# Documentação Técnica - Sistema de Servidores Públicos

## 1. Visão Geral

Este projeto implementa um sistema em Java para gerenciar informações de servidores públicos, incluindo dados pessoais, contratuais, profissionais e financeiros. O sistema é estruturado em classes que representam as diferentes entidades e seus relacionamentos, como Servidor, Endereço, Profissão, Remuneração e Proventos.

## 2. Estrutura do Projeto

A estrutura do projeto é organizada em um diretório `src` que contém os arquivos `.java`:

```
servidores-publicos/
├── src/                        # Código fonte Java
│   └── servidores/             # Pacote contendo as classes do sistema
│       ├── Endereco.java       # Classe para representar o endereço do servidor
│       ├── Profissao.java      # Classe para representar a profissão do servidor
│       ├── Proventos.java      # Classe para representar os proventos do servidor
│       ├── Remuneracao.java    # Classe para representar a remuneração do servidor
│       ├── Servidor.java       # Classe base para representar um servidor
│       ├── ServidorAtivo.java  # Classe para representar um servidor ativo
│       └── ServidorInativo.java# Classe para representar um servidor inativo
└── Diagrama_Classes_Servidores.pdf # Diagrama de classes do sistema
```

## 3. Tecnologias Utilizadas

*   **Java**: Linguagem de programação principal.

## 4. Funcionalidades Principais e Modelos de Dados

O sistema é composto pelas seguintes classes, que representam as entidades e suas funcionalidades:

### `Servidor`

*   **Atributos**: `nome` (String), `idade` (int), `cpf` (String), `endereco` (String), `telefone` (String), `dataContratacao` (String), `vinculo` (String), `matricula` (int).
*   **Métodos**: Getters e setters para todos os atributos. Métodos para obter dados pessoais (`getDadosPessoais()`), dados contratuais (`getDadosContratuais()`) e status do servidor (`getstatusServidor()`).

### `Endereco`

*   **Atributos**: `rua` (String), `bairro` (String), `numero` (String), `CEP` (String), `cidade` (String), `estado` (String).
*   **Métodos**: Getters e setters para todos os atributos.

### `Profissao`

*   **Atributos**: `orgao` (String), `cargo` (String), `funcao` (String).
*   **Métodos**: Getters e setters para todos os atributos.

### `Remuneracao`

*   **Atributos**: `remuneracaoBase` (double), `comissao` (double), `beneficios` (double), `eventuais` (double), `horasExtras` (double), `judiciais` (double), `tetoRedutor` (double), `irrf` (double), `contribPrev` (double), `totalLiquido` (double).
*   **Métodos**: Getters e setters para todos os atributos.

### `Proventos`

*   **Atributos**: `profissao` (Profissao), `remuneracao` (Remuneracao), `ferias` (boolean).
*   **Métodos**: Getters e setters para `profissao`, `statusFerias` e `ferias`.

### `ServidorAtivo`

*   **Atributos**: `proventos` (double), `eventuais` (double), `judiciais` (double), `tetoRedutor` (double), `irrf` (double), `contribPrev` (double), `totalLiquido` (double).
*   **Métodos**: Getters e setters para os atributos de proventos e status do servidor.

### `ServidorInativo`

*   **Atributos**: `proventos` (Proventos), `dataAposentadoria` (String).
*   **Métodos**: Getters e setters para `proventos`, `dataAposentadoria` e status do servidor.

## 5. Relacionamentos entre Classes

*   Um `Servidor` `possui` um `Endereco`.
*   Um `ServidorAtivo` `possui` `Proventos`.
*   Um `ServidorInativo` `possui` `Proventos`.
*   `Proventos` `possui` uma `Profissao` e uma `Remuneracao`.

## 6. Configuração e Execução

Para configurar e executar o projeto em seu ambiente local, siga os passos abaixo:

### Pré-requisitos

*   Java Development Kit (JDK) instalado (versão 8 ou superior recomendada).

### Instalação

1.  Clone o repositório:
    ```bash
    git clone https://github.com/rafaelcrb/servidores-publicos.git
    cd servidores-publicos
    ```

### Compilação e Execução

1.  Navegue até o diretório `src`:
    ```bash
    cd src
    ```
2.  Compile os arquivos Java:
    ```bash
    javac servidores/*.java
    ```
3.  Execute a classe principal (se houver uma, caso contrário, será necessário criar uma para testar as funcionalidades):
    ```bash
    # Exemplo, se houver uma classe principal como 'Main.java' no pacote 'servidores'
    java servidores.Main
    ```

## 7. Considerações de Desenvolvimento

*   O projeto demonstra o uso de Programação Orientada a Objetos para modelar entidades complexas do mundo real.
*   A separação de responsabilidades em diferentes classes facilita a manutenção e a escalabilidade do sistema.
*   O diagrama de classes (`Diagrama_Classes_Servidores.pdf`) fornece uma representação visual clara da estrutura do sistema.
*   Este é um projeto de estrutura de dados e lógica de negócio, sem interface gráfica ou persistência de dados implementada diretamente nos arquivos fornecidos. Seria necessário integrar um banco de dados ou outro mecanismo de persistência para armazenar os dados de forma duradoura.


