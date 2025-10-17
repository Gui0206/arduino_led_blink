Projeto Arduino: Introdução à Programação com Blink
===================================================

Este projeto documenta os passos iniciais de programação com a plataforma Arduino, cobrindo desde o acionamento do LED embutido na placa até a simulação de um circuito externo com um LED e resistor em um ambiente virtual.

Parte 1: Blink com LED Interno (Físico)
---------------------------------------

### Objetivo

O objetivo desta etapa é familiarizar-se com o ambiente de desenvolvimento (IDE) do Arduino e realizar a programação do microcontrolador para fazer o LED interno da placa (conectado ao pino 13) piscar em um intervalo de tempo definido.

### Ferramentas e Materiais

*   Placa Arduino UNO
    
*   Cabo USB
    
*   Arduino IDE (Software)
    

### Código Utilizado (Arduino IDE)

O código abaixo configura o pino do LED interno (LED\_BUILTIN) como uma saída. No loop principal, ele acende o LED, aguarda 1 segundo (1000 milissegundos), apaga o LED e aguarda mais 1 segundo, criando um efeito de pisca-pisca contínuo.


```

// Função de configuração, executada uma vez quando a placa é ligada ou resetada
void setup() {
  // Define o pino do LED interno como uma saída (OUTPUT)
  pinMode(LED_BUILTIN, OUTPUT);
}


// Função de loop, executada repetidamente após a configuração
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // Acende o LED (nível de tensão ALTO)
  delay(1000);                      // Aguarda por 1000 milissegundos (1 segundo)
  digitalWrite(LED_BUILTIN, LOW);    // Apaga o LED (nível de tensão BAIXO)
  delay(1000);                      // Aguarda por 1000 milissegundos (1 segundo)
} 
```

### Evidências e Resultados

Abaixo estão as evidências da execução do projeto: o código na IDE, a placa Arduino em funcionamento com o LED aceso e uma verificação do mesmo código no simulador Tinkercad.

![Código do sketch para piscar o LED interno no Arduino IDE.](codigo_arduino_ide.png)

**Figura 1:** Código final no Arduino IDE.

![Foto da placa Arduino UNO conectada ao computador com o LED interno 'L' aceso.](arduino.jpeg)

**Figura 2:** Placa Arduino UNO conectada e executando o código, com o LED interno (L) aceso.

![Simulação no Tinkercad mostrando o LED interno da placa virtual piscando.](tinkercad.png)

**Figura 3:** Simulação de verificação no Tinkercad, demonstrando o LED interno piscando.

Parte 2: Simulação de Blink com LED Externo (Tinkercad)
-------------------------------------------------------

### Objetivo

Nesta etapa, o projeto avança para a simulação de um circuito eletrônico básico no Tinkercad. O objetivo é montar e programar um pisca-pisca utilizando um LED externo, um resistor para proteção, uma protoboard e um Arduino UNO virtual.

### Componentes da Simulação

*   Arduino Uno
    
*   Protoboard (Matriz de Contatos)
    
*   1 LED (Amarelo)
    
*   1 Resistor de 220Ω (Vermelho, Vermelho, Marrom)
    
*   Fios de Conexão (Jumper Wires)
    

### Montagem do Circuito

O circuito foi montado da seguinte forma:

1.  O pino digital **13** do Arduino foi conectado a uma das pernas do resistor.
    
2.  A outra perna do resistor foi conectada ao terminal **anodo** (perna maior) do LED.
    
3.  O terminal **catodo** (perna menor) do LED foi conectado ao pino **GND** (Terra) do Arduino.
    

O resistor é fundamental para limitar a corrente que passa pelo LED, evitando que ele se queime.

### Código da Simulação

O código é muito semelhante ao da Parte 1, mas em vez de usar a constante LED\_BUILTIN, ele se refere diretamente ao **pino 13**, onde o circuito externo foi conectado.

```
// Função de configuração
void setup() {
  // Define o pino 13 como uma saída
  pinMode(13, OUTPUT);
}

// Função de loop
void loop() {
  digitalWrite(13, HIGH); // Envia 5V para o pino 13, acendendo o LED
  delay(1000);            // Mantém o LED aceso por 1 segundo
  digitalWrite(13, LOW);  // Corta a tensão do pino 13, apagando o LED
  delay(1000);            // Mantém o LED apagado por 1 segundo
}
```

### Resultados da Simulação

As imagens abaixo mostram a simulação em execução no Tinkercad, com o LED externo nos estados aceso e apagado.

![Simulação do circuito no Tinkercad com o LED amarelo aceso.](tinkercad_pisca_on.png)

**Figura 4:** Simulação com o LED externo no estado LIGADO (HIGH).

![Simulação do circuito no Tinkercad com o LED amarelo apagado.](tinkercad_pisca_off.png)

**Figura 5:** Simulação com o LED externo no estado DESLIGADO (LOW).

### Vídeo de Demonstração

Um vídeo demonstrando o funcionamento da simulação pode ser acessado no link a seguir:

[Link do vídeo](youtube.com/watch?v=MVImrbjRozs&feature=youtu.be)