Video do arduino funcionando no youtube: https://www.youtube.com/watch?v=5_gKxlHbtg8

## Integrantes

| Nome | RM |
|------|----|
| *(André Nobrega)* | *(RM561754)* |
| *(André Gouveia)* | *(RM564219)* |
| *(Mirella Mascarenhas)* | *(RM562092)* |

# Transmissão de Mensagem com Laser e LDR

## Sobre o projeto

Este projeto utiliza um Arduino para transmitir uma mensagem por meio de pulsos de luz. A comunicação é feita usando um módulo laser como transmissor e um sensor LDR como receptor.

A mensagem digitada no Monitor Serial é convertida em sinais binários, enviados pelo laser. O LDR detecta esses pulsos de luz e o Arduino reconstrói a mensagem recebida.

## Componentes utilizados

* Arduino Uno
* Módulo Laser KY-008
* Sensor LDR
* Jumpers
* Protoboard

## Pinos utilizados

* Laser: pino digital 12
* LDR: pino analógico A0

## Funcionamento

O projeto não utiliza mais código Morse. A transmissão foi alterada para um modelo binário simples.

Cada caractere da mensagem é convertido em 8 bits. O laser acende por tempos diferentes para representar os bits:

* Pulso curto: representa o bit 0
* Pulso longo: representa o bit 1

Antes da mensagem ser enviada, o sistema transmite um pulso inicial para indicar o começo da comunicação. No final, outro pulso maior indica o término da transmissão.

## Calibração do LDR

O código realiza uma calibração automática do LDR no início da execução.

Primeiro, ele mede o valor do sensor sem o laser. Depois, mede o valor com o laser ligado. Com esses dois valores, o sistema calcula um limite para identificar quando o laser está sendo detectado.

Isso ajuda a reduzir erros causados pela luz ambiente.

## O que aparece no Monitor Serial

Durante a execução, o Monitor Serial mostra:

* valores da calibração do LDR
* mensagem enviada
* início da transmissão
* fim da transmissão
* mensagem recebida

## Problemas corrigidos

Durante o desenvolvimento, foram feitas algumas correções importantes:

* a transmissão deixou de ser feita em código Morse
* a mensagem passou a ser enviada em formato binário
* o receptor passou a reconhecer os pulsos do laser
* a mensagem recebida passou a ser reconstruída e exibida no Monitor Serial
* foi adicionada calibração automática para melhorar a leitura do LDR

## Limitações

O funcionamento depende do alinhamento entre o laser e o LDR. Se o laser não estiver apontado corretamente para o sensor, a transmissão pode não ser reconhecida.

Além disso, a luz ambiente pode interferir na leitura, por isso a calibração é importante.

## Conclusão

O projeto demonstra uma comunicação simples por luz usando Arduino. Ele mostra como uma mensagem pode ser convertida em bits, transmitida por pulsos luminosos e reconstruída no receptor usando um sensor LDR.
