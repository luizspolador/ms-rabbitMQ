Utilizado o Spring AMQP para integrar o sistema através mensageria, comunicação assíncrona, promovendo o desacoplamento através do message broker (RabbitMQ).

- producer: pagamentos
- consumers: pedidos e avaliacao

- queue: pagamentos.detalhes-pedido
- queue: pagamentos.detalhes-avaliacao

- exchange: pagamentos.ex -> do tipo fanout. Não necessário routing key. Necessário criar uma binding key. A mensagem é enviada para todas as filas que estiverem ligadas a essa exchange.

Foi utilizada a biblioteca Jackson2JsonMessageConverter para converter objetos para o formato JSON e enviá-los ou recebê-los como mensagem.  

Foi utilizada uma DQL (dead letter queues) denominada pagamentos.detalhes-avaliacao-erros e uma DLX (dead letter exchange) denominada pagamentos.dlx
