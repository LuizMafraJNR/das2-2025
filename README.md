# Design e arquitetura de software 2
### Luiz Sesna Mafra Junior
<br><hr>
## 1. Aula 27/02/2025

    TradeOf
    
        Fazer Escolhas;
        Cada vez que for projetar um sistema voce precisa escolher em qual irá programar.
        
        Consiste em consistência, tamanho durabilidade, espaço, latência e performance.

            Consistência: O sistema ficar disponivel e consistente.

            Durabilidade: Gravar uma informação no database e garantir que essa informação não seja perdida. O que fazer quando as query não estão dando mais conta e você não tem mais opções? --> Pense em Cache para resolver se ja tentou de tudo. O cache é mais rápido. No cache não podemos manter a informação de dados(Incosistência, Sobrecarga da memoria). As vezes você vai abrir mão da durabildiade para ter performance.

            Espaço: Terceira forma normal --> Serve para reduzir redundancia. Usa uma quantidade minima para usar o banco.


            Exemplo de TradOf: (Ganho em uma coisa e ganho em outra):
            Site da univille lento -> precisa de mais computadores para não travar quando está cheio de gente e precisa ter mais computadores. Logo realizamos um TradeOf na AWS requisitando mais uma maquina EC2 com um alarme para Auto Scaling onde iremos ganhar consistencia, experiencia de usuario e em contrapartida perdemos dinheiro.


        Maquina que estava sendo usada pela AWS crashou:
            1. Poderia ter observalidade para detectar crashes e possiveis sobrecargas de sistema.
            2. Disparar um alarme
                2.1 Criar uma nova maquina para manter a consistencia(Primeiro bate no LoadBalancer e resolve isso.) 


        Tratar os recursos como descartavel.

<br>













