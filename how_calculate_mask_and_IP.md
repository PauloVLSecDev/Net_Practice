aqui explicarei como funciona o cada um dos elementos do Net_Practice  


todos os bites que corespondem a 1 se referenciam ao endereco da rede e os 0 se referenciam ao endereco do host

ou seja se tiveremos uma marcara de rede como 
cat << oi | cat << ola | cat << banana | cat << ander | catt jorge

                255.255.255.255 
    [11111111] [11111111] [11111111] [1111111]
        8          8           8         8   == /32

    esta mascar de reede nao possui nenhum espaco na rede os IPs (internet protocol)
    
# Notacao CDIR

tembem podemos representar esta mascara como /32 e para realizarmos este calculo usamos o notacao CDIR (Classless inter domain Routing)
assim o /30 por exemplo se refere a quantidade de bytes que uma mascara de rede possui a conta para checarmos nisto e a notacao assim feirta desta forma 

                255.255.255.252 

pegamos o ultimo octeto e aplicamos a CDIR 

      1   252 - 128
      2   124 - 64
      3   60 - 32
      4   28 - 16
      5   12 - 8
      6   4 - 4
          0 - 2 

assim podemos afirma que a potencia de 2 a 6 e igual a 252 logo sabemos que 6 bytes de 252 sao 1 e o ultimos restantes sao zero fiucando desta forma 


                255.255.255.252 
    [11111111] [11111111] [11111111] [1111100]
        8          8           8         6   == /30
    
    
um endereco ip tem 32 bytes para calcularmos o a quantidade de enderecos ips validos fazemos 32 (numero de bites maximo) - /30 (numero de butes da rede mascara atual) = 2
deppois disso usamos o resuyltaos para elevar 2 ** (resultado 2) assim tesmo 4 sendo o endereco o primeor o e o ultimo reservados para o endereco da mascara e o de broadcast


enderecos 127.x.x.x  sao usados para rede interna e nao conseguem se cominucar com outros ips sao chamada de endereco loopback

# Broadcast

    o Broadcast e um endereco especial que nao envia dados para
    apenas outro host mas para todos os ips que a rede possui 
    o broadcast e responsavel por escutar quais ips a rede possuem
    e quais estao querendo se conectar e o broadcast e usado para 
    definir a internet que vai se conectar com todos os ips de uma rede
    ou de um roteador que conecta varias redes

# Switch

    switch funcaiona para levar dados de um rede internal usando o enderecok Mac e nao apenas o IP pois
    o switch cria uma conectacao entre os dispositivos conectados na mesma rede 

# Roteadores

    Os Roteadores fazem  o trabalho de conectar o dispositivo entre redes, o roteadores possuem mascara e ip
    e sua rota se refere ao seu ip


# IP (internet protocol)

    Quando um dispositivo e conectado a um wi-fi ele pede um endereco IP para a rede assim respeitando quais dispositivos ja esta conectador a rede
    o endereco IP tambem possui quatro octetos logo cada endereco ip equivale a 32 bytes

# DHCP (Dynamic host Configuration protocol)

    sabendo disso podedmos pensar como um dispositivo consegue se conectar a uma rede sem um IP ? 
    O ocorre que quando um dispositivo entra na rede ele ¨grita" para todos os dispositivos na rede
    para que um IP seja destinado a ele assim normalente o roteador "escuta" o dispositivo e define um ip
    dentro dos disponiveis para ele essde processo e chamado de (Dynamic host Configuration protocol)


