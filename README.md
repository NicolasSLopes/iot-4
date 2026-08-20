# iot-4

**Discente:** Nicolas Santana Lopes
**Docente:** Amanda Paul Dull

Esse repositório contém a atividade da matéria de IoT, utilizando um Arduino UNO, dois LEDs e um botão para controlar diferentes estados do circuito.

[![Simular no Tinkercad](https://img.shields.io/badge/Simular%20no-Tinkercad-orange?style=for-the-badge\&logo=autodesk)](https://www.tinkercad.com)

## Enunciado: Controle de LEDs com Botão

O projeto utiliza um **botão** para controlar dois LEDs conectados ao Arduino UNO. Cada vez que o botão é pressionado, o circuito muda para o próximo estado.

O funcionamento ocorre em três estados:

* **Estado 1:** o LED 1 acende e o LED 2 permanece apagado.
* **Estado 2:** o LED 1 apaga e o LED 2 acende.
* **Estado 3:** os dois LEDs permanecem apagados.

Após o terceiro estado, o próximo clique retorna ao primeiro estado, mantendo o funcionamento em ciclo.

### Ligações

* **Botão:** Pino **7**
* **LED 1:** Pino **11**
* **LED 2:** Pino **10**

O botão utiliza `INPUT_PULLUP`, enquanto os dois LEDs são configurados como saídas digitais.

## Materiais Necessários

| Qtd | Componente                 |
| :-- | :------------------------- |
| 1   | Placa Arduino UNO          |
| 1   | Cabo USB                   |
| 1   | Protoboard                 |
| 2   | LEDs                       |
| 2   | Resistores de 220 Ω        |
| 1   | Botão (Push Button)        |
| —   | Fios de Jumper Macho-Macho |

## Funcionamento do Código

O programa utiliza a variável `estado` para determinar qual ação deve ser realizada a cada clique do botão.

Quando o botão é pressionado, o programa aumenta o valor de `estado`:

* `estado = 1`: LED 1 ligado e LED 2 desligado.
* `estado = 2`: LED 1 desligado e LED 2 ligado.
* `estado = 3`: os dois LEDs desligados.

Quando o estado ultrapassa 3, ele volta para 1, reiniciando o ciclo.

A variável `ultimoEstadoBotao` é utilizada para identificar o momento exato em que o botão foi pressionado, evitando que uma única pressão seja registrada várias vezes. O `delay(200)` também ajuda a evitar múltiplas leituras causadas pelo acionamento do botão.
