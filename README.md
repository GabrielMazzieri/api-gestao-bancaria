API de Gestão Bancária com Suporte a Integração IoT

Esta API é uma solução de backend desenvolvida em Java 21 e Spring Boot 3.5.5, focada na gestão de contas financeiras e operações bancárias. O sistema foi projetado com uma arquitetura preparada para o ecossistema IoT, permitindo a validação de segurança via protocolo MQTT.  
🛠️ Tecnologias Utilizadas

    Java 21: Versão estável com recursos modernos.  

    Spring Boot 3: Framework base para a construção da API.  

    Spring Data JPA: Gestão de persistência de dados.  

    Spring Security & JWT: Autenticação e proteção de endpoints.  

    Protocolo MQTT: Preparado para integração com dispositivos de hardware externos via spring-mqttx.  

    Lombok: Redução de código boilerplate.  

    Swagger/OpenAPI: Documentação automatizada dos endpoints.  

🏗️ Arquitetura e Regras de Negócio

O projeto aplica padrões de design para garantir a robustez das operações financeiras:

    Herança de Contas: Implementação de Contas Correntes e Contas Poupança através de herança de entidades (JPA Inheritance).

    Fluxo Financeiro: Lógica para depósitos, saques e transferências com tratamento rigoroso de saldo e exceções customizadas (ex: SaldoInsuficienteException).

    Segurança: Controle de acesso baseado em perfis (Clientes e Gerentes) autenticados via tokens JWT.  

📡 Módulo de Validação IoT (Simulado)

Uma característica inovadora desta API é o serviço AutenticacaoIoTService. Embora o hardware físico não seja obrigatório para o funcionamento da API, o sistema está arquiteturalmente pronto para interagir com sensores externos:

    Escuta de Tópicos: A API monitora o tópico MQTT banco/validacao/biometria.

    Processamento de Sinais: O BiometriaMqttListener processa payloads JSON simulando a resposta de um sensor biométrico.

    Segurança Extensível: Esta camada demonstra a capacidade do sistema em condicionar transações críticas a validações físicas externas.

🚀 Como Configurar e Rodar
Pré-requisitos

    Java JDK 21

    Maven 3.x

    Broker MQTT (Opcional, para testes do módulo de integração)

Instalação

    Clone o repositório.

    Configure o banco de dados em src/main/resources/application.properties.

    Compile o projeto: mvn clean install.

    Inicie a aplicação: mvn spring-boot:run.

Desenvolvido por Gabriel Mazzieri.
