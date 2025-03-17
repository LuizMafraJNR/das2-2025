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

## 2. Aula 06/03/2025

IAC - Automatizar. E é a capacidade de provisionar e dar suporte à infraestrutura de computação usando código em vez de configurações e processos manuais.

Pesquisar sobre Tofu e ArdCD(eu acho)

Escrever um teplate usando terraform ou cloud formation para IAC

Servidor com nome = DANGER (Não descartavel)

Um Plano de dados é a máquina ser discartada.

### O que é Acomplamento
Uma coisa que não consigo substituir com facilidade para outra.
Exemplo: Qualquer dispositivo que tem uma porta HDMI, ele tem alto acomplamento ou baixo? Baixo pois podemos trocar facilmente, 

AntiPatern: Basta cair o banco de dados que aplicação vai juntor, pois geralmente o banco tem um alto acomplamento com o serviço.

Best Practice: Para resolver o problema do antipatern, basta criar varias replicas e no meio colocar um Load Balancer para quando qualquer maquina que cair do banco tenha uma outra pronta. (Distribuição de carga) E se cair o LoadBalancer? Basta ter duplicação, triplicação (redundancia)

## Frase do dia: 
<b>FAÇA DESIGN DE SERVIÇO NÃO DE SERVIDORES!</b> 
<hr>

## 3. Aula 10/03/2025

Apenas um pouco da aula passada

### Global Insfrascrutcture
- AWS Regions;
    - Conjunto de um ou mais data-centeres
- Availability Zones
    - Pode haver 5 data-centers mas eu não enxergo;
    - Sempre que tiver mais em uma zona sempre vai representar disponibilidade. 
- AWS Local Zones
    - Estrutura parecida com uma AZ(mas é menor) Argentinha Buenos Aires; Para que server: rodar servidor de fortnite para tu jogar(computação, storage ou no geral serviços gerais)
- AWS Data Centers
    - 
- AWS Points of presence(PoPs)
    - Edge location e Regional Edge Cache

Carregar site angular mais rapido, o ultimo.

### Securing Access


## 4. Aula 13/03/2025
- Modelo de responsabilidade compartilhada
- Principio do privilegio minimo
- Autenticação
- Autorização
- Identity and Access Management
- 


## 5. Aula 17/03/2025

### IAM Policies and permissions

Toda nuvem tem que ter um mecanismo de permissões e grupos.
Há das polices:
- Identity-based: Attach to an IAM user group OR role 
- Resource-based: Fica no recurso

Diferença: na de identidade você coloca a police no zezinho enquanto na de recurso você tem que especificar um  usuario, mesmo que seja um "*" (todo mundo)

### S3
- Block of Storage
    - Data is stored on a device in fixed-sized blocks
- File Storage
    - Data is stored in a hierarchical structure
    - File share = Centenas de maquinas trocando de arquivos atraves desses servidores
- Object Storage
    - Data is sotred as objects based on attributes and metadata
    - Dados, apenas 

Serviço mais famoso da AWS
- Limite 5tb por objeto/arquivo




















