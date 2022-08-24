# 📝 Documentação da API:
https://registro-de-equipamentos.leudoneto.repl.co/

# 🏷️ Documentação do projeto:

## 🚀 Instalação
> git clone https://github.com/LeudoNeto/registro-de-equipamentos.git

## 💻 Execução

> - ` 1. ` cd registro-de-equipamentos
>
> - ` 2. ` dotnet run
>
> - ` 3. ` No seu `navegador` acesse `https://localhost:7185/swagger`.

# Sobre o projeto:

## O Desafio

Você é o desenvolvedor backend de uma empresa que coleta dados de equipamentos utilizados em uma operação florestal. Dentre esses dados estão o histórico de posições e estados desses equipamentos. O estado de um equipamento é utilizado para saber o que o equipamento estava fazendo em um determinado momento, seja Operando, Parado ou em Manutenção. O estado é alterado de acordo com o uso do equipamento na operação, já a posição do equipamento é coletada através do GPS e é enviada e armazenada de tempo em tempo pela aplicação.

Seu objetivo é, de posse desses dados, desenvolver uma aplicação backend que exponha esses dados através de uma API.

### Requisitos de négocio

* **API de CRUD**: Você deve desenvolver uma API que exponha os métodos de Criar, Excluir, Editar e Ler para as seguintes entidades:
  * Equipamento.
  * Estado de equipamento.
  * Modelo de Equipamento.
  * Ganhos por hora por estado.
  * Histórico de posições de um equipamento.
  * Histórico de estados de um equipamento.

* **Estado atual do equipamento**: Endpoint na API que deve retornar o estado mais recente dos equipamentos.

* **Posição atual por equipamento**: Endpoint na API que deve retornar a posição mais recente dos equipamentos.

## Dados

### equipment
Contém todos os equipamentos da aplicação.

* **id**: Identificador único do equipamento.
* **equipment_model_id**: Chave estrangeira, utilizada para referenciar de qual modelo é esse equipamento.
* **name**: Nome do equipamento.

### equipment_state
Contém todos os estados dos equipamentos.

* **id**: Identificador único do estado de equipamento
* **name**: Nome do estado.
* **color**: Cor utilizada para representar o estado.

### equipment_model
Contém todos os modelos de equipamentos.

* **id**: Identificador único do modelo de equipamento.
* **name**: Nome do modelo de equipamento.

### equipment_model_state_hourly_earnings
Informação de qual é o valor por hora do modelo de equipamento em cada um dos estados.

* **equipment_model_id**: Chave estrangeira, utilizada para referenciar de qual modelo é esse valor.
* **equipment_state_id**: Chave estrangeira, utilizada para referenciar de qual valor é esse estado.
* **value**: Valor gerado por hora nesse estado.

### equipment_state_history
O histórico de estados por equipamento.

* **equipment_id**: Chave estrangeira, utilizada para referenciar de qual equipamento é esse estado.
* **date**: Data em que o equipamento declarou estar nesse estado.
* **equipment_state_id**: Chave estrangeira, utilizada para referenciar qual é o estado que o equipamento estava nesse momento.

### equipment_position_history
O histórico de posições dos equipamentos.

* **equipment_id**: Chave estrangeira, utilizada para referenciar de qual equipamento é essa posição.
* **date**: Data em que a posição foi registrada.
* **lat**: Latitude em WGS84.
* **lon**: Longitude em WGS84.