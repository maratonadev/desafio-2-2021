[![](https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg)](https://cloud.ibm.com)
[![](https://img.shields.io/discord/734849242153222221?logo=discord)](https://discord.gg/yJYmTGDWKH)

# Desafio 02 | Quanam

- [1. Sobre a Quanam e a Aleph](#1-sobre-a-quanam-e-a-aleph)
  - [1.1. Introdução](#11-introdução)
  - [1.2. Premiação](#12-premiação)
- [2. Desafio de negócio](#2-desafio-de-negócio)
- [3. Objetivo](#3-objetivo)
- [4. Tecnologias aplicadas](#4-tecnologias-aplicadas)
- [5. Desenvolvimento da solução](#5-desenvolvimento-da-solução)
  - [5.1. Pré-requisitos](#51-pré-requisitos)
  - [5.2. Resumo das tarefas](#52-resumo-das-tarefas)
  - [5.3. Desenvolvimento](#53-desenvolvimento)
- [6. Submissão](#6-submissão)
- [7. Sobre a avaliação](#7-sobre-a-avaliação)

## Para te ajudar

- [Material de Apoio](#material-de-apoio)

## 1. Sobre a Quanam e a Aleph

### 1.1. Introdução

_Quanam_ é uma federação internacional de empresas cujo objetivo é a inovação e a gestão do conhecimento para o benefício dos clientes e da comunidade através da consultoria empresarial, gestão e aplicação de tecnologias de ponta em diferentes segmentos.

A Quanam mantém diversas atividades a nível internacional, possui 7 escritórios na América, mais de 600 clientes e 400 especialistas altamente especializados

A iniciativa _Aleph_ foi criada e desenvolvida pela Quanam visando um forte compromisso com a inovação e tem como objetivo promover o crescimento constante de todos os atores de um ecossistema (organizações, PMEs, empresas tradicionais, cidadãos , etc.) por meio da dinamização de suas interações e integrações. Essa dinamização é alcançada através da aplicação de metodologias e ferramentas de TI que criam espaços de oportunidades, permitindo acelerar o ritmo de desenvolvimento de determinada comunidade ou ecossistema.

### 1.2. Premiação

Em linha com o propósito de formar uma comunidade capaz de gerar soluções para o projeto, a Quanam alocará recursos para treinar e apoiar, por meio de mentoria, aqueles desenvolvedores que venceram o evento e que desejam acompanhar o projeto. Será dado como premiação pela Quanam, para as três melhores pessoas colocadas em este desafio, um "**Voucher Aleph**" para cada:

- O titular de cada Voucher Aleph receberá uma mentoria que visa transformar uma ideia em um modelo de negócio exponencial.
- A mentoria será realizada aplicando metodologias de inovação disruptiva.
- O modelo de negócio será formulado de forma a poder ser apresentado a fundos de investimento a definir em conjunto com o vencedor.
- A ideia não tem necessariamente de estar relacionada com a maratona.

Cada Voucher Aleph inclui:

- 1 workshop para criar modelos de negócios em ecossistemas ou comunidades Aleph utilizando a Metodologia Pentagrowth, uma das metodologias usadas pelo Aleph para criar modelos de negócios disruptivos baseados em uma ideia fornecida pelo participante.
- 3 meses de acompanhamento com Consultores Aleph
- Acompanhamento semanal com sessões de 1 hora para explorar juntos o potencial da ideia.

**Valor de cada Voucher: US \$ 3.000**. Os 3 participantes melhor colocados, podem optar pelo "Voucher Aleph" ou por um vale-compras no valor de US$ 500.

## 2. Desafio de negócio

Em um centro de reabilitação de saúde são instalados sensores para determinar a qualidade das suas condições ambientais. É necessário ter controle da qualidade do ar e outros parâmetros relacionados ao meio ambiente, para agir rapidamente caso sejam detectadas anomalias, que podem ser muito prejudiciais aos pacientes.

Os sensores estão instalados em vários locais como: sala de espera, quartos, banheiros, refeitório, sala de atividades, escritório, jardim.

Os níveis aceitáveis de dados medidos podem variar dependendo da localização do medidor.

Também existem pulseiras que medem a frequência cardíaca, elas são colocadas em pacientes com doenças ou riscos cardíacos. O objetivo é poder controlar e realizar intervenções precoces em pacientes que possuam alterações desses valores.

No escritório, há um servidor disponível para monitoramento dos parâmetros medidos, disponibilizando os níveis dos mesmos em tempo real.

## 3. Objetivo

Desenvolver uma solução capaz de:

- Capturar de dados da central de IoT e persistir os mesmos em algum formato padrão. (por exemplo, arquivo CSV);
- Detectar anomalias em cada uma das séries de dados. O processo deve retornar alertas, dependendo dos valores recebidos dos sensores e do ambiente em que o sensor está localizado.
- Elaborar um modelo que permita prever as condições futuras de uma habitação, com base na análise de dados anteriores. O modelo deverá ser capaz de predizer o ritmo cardíaco de pacientes da habitação que utilizam a pulseira, baseando-se nas condições do ambiente.

## 4. Tecnologias aplicadas

Para este desafio serão utilizados os seguintes serviços da IBM Cloud:

- [Watson Studio](https://cloud.ibm.com/catalog/services/watson-studio), também conhecido como Cloud Pak for Data as a Service. Esse serviço permite o uso de uma gama de ferramentas relacionadas à Ciência de Dados, inclusive execução de Jupyter Notebooks com processadores na nuvem.

- [Cloud Functions](https://cloud.ibm.com/functions), um serviço para execução de funções na nuvem, sem necessidade de um servidor (modelo conhecido como Serverless).

## 5. Desenvolvimento da solução

### 5.1. Pré-requisitos

Para realizar esse desafio você deverá cumprir os seguintes pré-requisitos:

- Ser registrado na [Maratona Behind the Code 2021](https://maratona.dev/?register=true) e confirmar seu e-mail de cadastro;
- Possuir uma [conta na IBM Cloud](https://ibm.biz/Bdf8dW), podendo ser a conta Lite ou Pay-As-You-Go (não é necessário registrar-se no evento com o mesmo e-mail utilizado para criar sua conta na IBM Cloud).

### 5.2. Resumo das Tarefas

1. Instanciar o serviços do desafio na IBM Cloud: Object Storage e Watson Studio (opcionais);
2. Criar uma API Serverless capaz de gerar alertas para os dados dos sensores IoT;
3. Coletar os dados disponíveis dos sensores IoT;
4. Criar um modelo de Machine Learning capaz de realizar predições baseadas nos dados capturados dos sensores;
5. Efetuar a submissão na [página do desafio](https://maratona.dev/challenge/2).

### 5.3. Desenvolvimento

#### Parte 1 - Alertas de sensores

Precisamos gerar alertas caso as medidas com que estamos trabalhando saiam do alcance esperado. Para isso, pedimos que você crie uma API Serverless, utilizando Cloud Functions. Assista ao vídeo abaixo para entender como fazer isso:

<div align="center">
    <a href="https://youtu.be/fiInka0Q5J8">
        <img width="375" src="../img/video.jpg" alt='video'>
    </a>
</div>

A API que você vai criar receberá os seguintes dados, no formato JSON como no exemplo abaixo:

```json
{
  "room": "bathroom-main",
  "values": {
    "co2": 400,
    "temperature": 22,
    "humidity": 70,
    "sound": 30,
    "illumination": 150
  }
}
```

E deve retornar um objeto JSON com uma lista das medidas com alertas como no exemplo abaixo:

```json
{
  "alerts": ["temperature", "humidity"]
}
```

Os alertas da lista podem aparecer em qualquer ordem.

Os alcances aceitáveis de valores estão definidos na tabela abaixo:

| Dado                        | Unidade de Medida | Ambiente                             | Alcance de valores aceitáveis    |
| --------------------------- | ----------------- | ------------------------------------ | -------------------------------- |
| CO2 (`co2`)                 | PPM               | Sala de Atividades (`activity-room`) | Até 500                          |
| "                           | "                 | Refeitório (`refectory`)             | Até 400                          |
| "                           | "                 | Quarto 1 (`room-1`)                  | Até 300                          |
| "                           | "                 | Banheiro Principal (`bathroom-main`) | Até 500                          |
| "                           | "                 | Jardim (`garden`)                    | Até 500                          |
| Temperatura (`temperature`) | °C                | Sala de Atividades (`activity-room`) | 19 - 22                          |
| "                           | "                 | Refeitório (`refectory`)             | 20 - 23                          |
| "                           | "                 | Quarto 1 (`room-1`)                  | 21 - 23                          |
| "                           | "                 | Banheiro Principal (`bathroom-main`) | 22 - 25                          |
| "                           | "                 | Jardim (`garden`)                    | 15 - 22                          |
| Humidade (`humidity`)       | %                 | Sala de Atividades (`activity-room`) | 50 - 60                          |
| "                           | "                 | Refeitório (`refectory`)             | 50 - 70                          |
| "                           | "                 | Quarto 1 (`room-1`)                  | 50 - 60                          |
| "                           | "                 | Banheiro Principal (`bathroom-main`) | 60 - 75                          |
| "                           | "                 | Jardim (`garden`)                    | 50 - 80                          |
| Som (`sound`)               | dB                | Sala de Atividades (`activity-room`) | 0 - 40                           |
| "                           | "                 | Refeitório (`refectory`)             | 20 - 35                          |
| "                           | "                 | Quarto 1 (`room-1`)                  | 10 - 30                          |
| "                           | "                 | Banheiro Principal (`bathroom-main`) | 20 - 35                          |
| "                           | "                 | Jardim (`garden`)                    | 10 - 35                          |
| Iluminação (`illumination`) | Lux               | Sala de Atividades (`activity-room`) | 300 - 750                        |
| "                           | "                 | Refeitório (`refectory`)             | 200 - 500                        |
| "                           | "                 | Quarto 1 (`room-1`)                  | 100 - 200                        |
| "                           | "                 | Banheiro Principal (`bathroom-main`) | 100 - 200                        |
| "                           | "                 | Jardim (`garden`)                    | N/A (Qualquer valor é aceitável) |

#### Parte 2 - Predição com dados de IoT

Para esse desafio, temos um _broker_ MQTT disponível online. Esse _broker_ está capturando dados de sensores IoT em loop, e publicando-os no tópico `quanam`, e você deverá capturá-los. No total, são 3200 amostras de dados diferentes, cada uma tendo os valores de co2 (`CO2`), temperatura (`TEMP`), humidade (`HUMID`), som (`SOUND`), iluminação (`ILLUM`) e ritmo cardíaco (`RYTHM`), juntamente com um número identificador da amostra (`ID`), variando de 1 até 3200. O primeiro passo que você deve completar é capturar esses dados do _broker_, para então fazer análises com eles. Abaixo estão as credenciais de acesso para o broker:

```
HOST: iot.maratona.dev
PORT: 31666
USERNAME: maratoners
PASSWORD: btc-2021
```

Nosso _broker_ utiliza o protocolo MQTT v3.1.1. Escutando pelo tópico `quanam`, você obterá os dados no seguinte formato:

```json
{
  "ILLUM": "523.98",
  "HUMID": "67.24",
  "CO2": "564.43",
  "SOUND": "36.97",
  "TEMP": "18.6",
  "RYTHM": "73.73",
  "ID": 1994
}
```

Você pode escolher o cliente MQTT que preferir para capturar os dados. Como recomendação, deixamos o [Node-RED](https://nodered.org/docs/getting-started/local), que já vem com o nó `mqtt in` por padrão, pronto para ser utilizado, ou o cliente Python [paho-mqtt](https://pypi.org/project/paho-mqtt/). Lembre-se de inserir o usuário e senha para subscrever ao tópico, caso contrário não conseguira receber os eventos.

Queremos, a partir dos dados obtidos via IoT, fazer uma predição de qual será o ritmo cardíaco de uma pessoa para saber se ela está em risco ou não. Portanto, após agrupar esses dados, sua tarefa é criar um modelo de **regressão**, capaz de predizer qual será o ritmo cardíaco de um paciente baseando-se nas medidas disponíveis. Dessa vez, você não precisará publicar o modelo no Watson Machine Learning. Para entregar as respostas do seu modelo, basta preencher a coluna **RYTHM** do [arquivo CSV](../../assets/answers.csv) de respostas e nos entregá-lo. **Não altere nenhum outro dado do arquivo, apenas os valores da coluna RYTHM**.

**Observação**: Os dados disponibilizados nesse desafio são fictícios, e não correspondem de maneira alguma à realidade.

## 6. Submissão

Tendo completado as duas etapas, o último passo é realizar a submissão. Será aceita somente uma submissão para o desafio, então teste bem antes de fazer o envio.

Para realizar a submissão, você deverá acessar a página do desafio: [https://maratona.dev/challenge/2](https://maratona.dev/challenge/2) e enviar:

- A URL da sua função no Cloud Functions
- O arquivo CSV com suas respostas
- Um arquivo `.zip`, de até 10MB, contendo o código fonte utilizado para o **modelo de regressão**. Não inclua o código utilizado para o Cloud Functions.

A página fará um teste para verificar se seus dados estão corretos.

As avaliações só começarão a ocorrer após a primeira semana do desafio. No momento da submissão, as credenciais para acesso à sua solução serão guardadas, e usadas para avaliação posteriormente. **Não exclua nenhum serviço utilizado para o desafio antes da avaliação!** Se os serviços cujas credenciais foram enviadas não estiverem disponíveis na data de avaliação, a submissão ficará com nota zero. Nesse caso, uma nova submissão será permitida.

Você poderá acompanhar o status da submissão acessando a [página do desafio](https://maratona.dev/challenge/2), logando na sua conta.

## 7. Sobre a avaliação

Uma semana após o início do desafio, nosso sistema de avaliação automática começará as avaliações. Ele irá utilizar os dados enviados para calcular uma pontuação numérica de 1 até 100, baseada nas respostas de alertas IoT e na métrica [R<sup>2</sup>](https://en.wikipedia.org/wiki/Coefficient_of_determination). O arquivo `.zip` enviado deve conter todo o código utilizado para o modelo de regressão. Caso contrário, a pontuação será zerada.

Caso o desafio seja entregue dentro do prazo de envio (até 28 de novembro), o participante receberá uma bonificação de 10% da pontuação total (10 pontos), independendo do resultado de seu desafio. A pontuação máxima possível, portanto, é 110 (100 de avaliação + 10 de bônus).

Após o prazo de envio, o participante ainda poderá realizar sua submissão até dia 12 de dezembro, mas sem receber o bônus.

**Atenção**: nos reservamos o direito de zerar a pontuação de uma submissão caso:

- O código fonte enviado não seja coerente com os resultados obtidos.
- Seja detectado plágio, de um ou mais participantes. Nesse caso, todos os participantes com a solução igual terão sua pontuação no desafio zerada.

## Material de apoio

- [Documentação do Cloud Functions](https://cloud.ibm.com/docs/openwhisk?locale=pt-BR)
- [Crie funções serverless para enviar notificações push](https://developer.ibm.com/br/patterns/serverless-functions-push-notifications/)
- [Como utilizar Cloud Functions?](https://developer.ibm.com/br/videos/como-utilizar-cloud-functions/)
- [Visualizar dados com Python](https://developer.ibm.com/br/patterns/visualize-data-with-python/)
- [Watson e a Assistência Médica](https://developer.ibm.com/br/tutorials/ind-watson/)
- [Crie e implemente um modelo de pontuação para prever problemas na frequência cardíaca](https://developer.ibm.com/br/patterns/create-and-deploy-a-scoring-model-to-predict-heartrate-failure/)

Você também pode acessar o Discord oficial da Maratona 2021 para realizar perguntas e/ou interagir com outros participantes: [Discord](https://discord.gg/yJYmTGDWKH).

## License

Copyright 2021 Maratona Behind the Code

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
