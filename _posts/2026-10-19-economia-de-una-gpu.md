---
layout: post
title: "La economía de una GPU: cuánto vive y a qué precio se alquila"
date: 2026-10-19
---


Esto es un análisis que he hecho del modelo de negocio de Nebius. Lo que es importante saber es que al 99.9% de los inversores de NBIS esto les da igual: no van más allá de invertir cuando un contrato grande se anuncia, o cuando algún analista saca una métrica molona sin entrar en profundidad.

Personalmente no tengo ni idea de dónde va a ir el precio de Nebius, solo he creado este artículo para dar un poco más de luz al negocio.

Mi punto de vista es bastante negativo: el hecho de que no sean más transparentes en sus reports me da siempre muy muy mala espina. Yo he sido CEO, y cualquier cosa buena de mi negocio que pudiese decir, siempre la diría. Cuando no dices mucho es porque tienes dudas o cosas que esconder.

## En resumen

- La flota en servicio de Nebius costó $5,198M, produce $3,000M al año y cuesta $1,500M operarla.
- El alquiler de una GPU sin contrato cae un 25% al año: cada generación nueva de NVIDIA empuja el precio de la anterior hacia abajo.
- La flota solo recupera lo que costó si está contratada a precio fijo toda su vida, y aun así rinde un 6% anual (13% si la GPU dura 5 años). Con contratos de 3 años empata, con 2 o menos, pierde.
- Hoy menos de la mitad de la flota está a 5 años. El resto renueva a precio de mercado.
- Ese 6-13% del mejor caso está por debajo del 15% al que se financia hoy CoreWeave. La pregunta es a qué precio financiará Nebius sus $20-25B de capex.

## Antes de empezar

Nebius es una “neocloud”: compra GPUs (los chips que entrenan y ejecutan inteligencia artificial), las monta en centros de datos y las alquila por horas o por contrato a empresas de IA. Es el negocio de un casero: paga un edificio caro y vive del alquiler.

La diferencia con un casero es que una GPU no dura 50 años. Cada año NVIDIA saca un chip mejor y más barato por unidad de cálculo, y el alquiler de la GPU vieja baja. La pregunta de este artículo es simple: ¿da tiempo a recuperar lo que costó la GPU antes de que deje de valer la pena tenerla encendida?

Tres palabras para los que no tengan mucho background en finanzas: capex (lo que costó comprar las GPU), EBITDA (lo que queda del alquiler después de pagar la energía para que las GPUs corran y los sueldos de quienes las colocan y mantienen en el centro de datos, no descuenta ni la depreciación de los chips ni los intereses) y run-rate (el ingreso del último mes multiplicado por 12).

## 1. El dinero que genera la flota de Nebius

La flota en servicio costó $5,198M. Hoy, al ritmo de junio, ingresa $3,000M al año y cuesta $1,500M operarla. Lo que ingrese los años siguientes es lo que hay que discutir.

Tres cifras de las cuentas de junio de 2026 (Nebius 6-K, agosto 2026), tomadas a la salida del trimestre, cuando toda la capacidad conectada ya estaba trabajando:

- **Lo que costó:** $5,198M de servidores y red en servicio. Otros $7,836M ya comprados esperan a conectarse y no cuentan aquí.
- **Lo que produce:** $3,000M al año (run-rate de junio: último mes × 12).
- **Lo que cuesta operarla:** $1,500M al año (energía, colocación y sueldos del segmento, con el margen del 50% que Nebius publica).

## 2. Lo que pasa con el precio año tras año

Hay dos tipos de ingreso, y se comportan al revés.

**Lo contratado no cae.** Nebius firma contratos de 1-3 años con clientes normales y de 5 años con Microsoft y Meta, a precio fijo. En el 70% de los contratos el cliente adelanta el 50-60% del coste de los chips. Mientras dura el contrato, es renta fija.

**Lo que queda libre se alquila a precio de mercado, y ese precio cae.** La H100 on-demand costaba $6.62/hora a finales de 2023 y ronda los $2.80 hoy: un −30% anual. Los contratos a un año bajaron más, hasta $1.70 en octubre de 2025, y han rebotado a $2.35 por escasez eléctrica. Comparando generaciones en on-demand (la A100 vale un 60% de la H100. La H100, entre la mitad y tres cuartos de una B200 según el índice), cada chip nuevo recorta el precio del anterior un 20-30% al año. El modelo usa un 25%, la media entre esa comparación y el −30% medido en 2024-25, solo sobre lo no contratado.

Las fuerzas detrás no descansan: +49% de cálculo por dólar cada año (Epoch AI) y una arquitectura nueva de NVIDIA cada año. Nebius lo sabe y cobra casi el doble por contratos de 3-6 meses: es el sobreprecio por asumir el riesgo de la caída.

## 3. La cuenta: un rango, no un número

El resultado depende casi por completo de cuántos años está contratada la flota.

Capex $5,198M, costes de salida $1,500M al año, ingreso inicial $3,000M, vida de 4 años:

| Escenario | Ingresos 4 años | EBITDA 4 años | Sobre el capex | TIR anual |
| --- | --: | --: | --: | --: |
| Todo contratado, precio fijo | $12,000M | $6,000M | +15% | \~6% |
| 3 años contratados + 1 a mercado (−25%) | $11,250M | $5,250M | +1% | \~0% |
| 2 años contratados + 2 a mercado (−25%) | $9,938M | $3,938M | −24% | negativa |
| Todo a mercado, cayendo 25% al año | $8,203M | $2,203M | −58% | negativa |

La TIR es el “interés anual” que paga la inversión. La lectura es simple: el único caso en el que la flota gana dinero es el de contratos de 5 años con hiperescaladores (Microsoft, Meta), y aun así rinde un 6% anual si la GPU dura 4 años, un 13% si dura 5. En todos los demás pierde.

## 4. Cuánto está contratado hoy, y por qué es peligroso

Hoy la mayoría de la flota no tiene contratos de 5 años, y por eso no recupera lo que costó.

Nebius tiene unos $40B firmados, casi todo con Microsoft y Meta a 5 años. Pero esos contratos entran poco a poco: Meta ya está en marcha (\~$600M al año) y Microsoft terminó de entregarse en verano de 2026, así que en junio aún no facturaba a pleno ritmo. Nuestra estimación (Nebius no publica la mezcla) es que en junio menos de la mitad de los $3,000M de ingreso anual estaba a 5 años. El resto eran contratos de 1-3 años o alquiler a precio de mercado.

Con esa mezcla, la flota de hoy gana dinero cada trimestre pero no recupera lo que costó: cuando los contratos cortos vencen, renueva más barato. Está en las filas del medio de la tabla, las que pierden.

Y en el mejor caso, con toda la flota contratada a precio fijo, el retorno es un 6% anual si la GPU dura 4 años y un 13% si dura 5. El mercado hoy no presta a este sector a esos precios: CoreWeave, el neocloud más grande, se está financiando al 15%. Nebius tiene que financiar $20-25B de capex este año, y la pregunta es a qué precio. Si es parecido al de CoreWeave, ni el mejor caso cierra.

## Fuentes

1. **La flota, el ingreso y los costes.** Nebius 6-K, agosto 2026 (resultados Q2 2026, abril-junio): servidores y red en servicio $5,197.7M, otros $7,836.4M “not yet in use”; ingresos de nube IA $574.9M en el trimestre; EBITDA ajustado del segmento $286M (50%); run-rate $3.0B a cierre de junio; 70% de contratos con prepago del 50-60% del capex; \~$40B de compromisos firmados. Resumen de la [llamada de resultados](https://www.nasdaq.com/articles/nebius-group-q2-earnings-call-highlights) y de los [resultados](https://quartr.com/events/nebius-group-n-v-nbis-q2-2026_ozKEzQzr).
2. **Los contratos con hiperescaladores.** Microsoft: hasta $17.4B a 5 años, \~$7B por adelantado, facturación mensual hasta octubre 2031 (Nebius 20-F, abril 2026; [resumen](https://www.theenergymag.com/news/2026-05-04/microsoft-nebius-ai)). Meta: $3B a 5 años ya desplegados y acuerdo de hasta $27B en órdenes de 5 años con entregas desde 2027 ([Nebius 6-K, marzo 2026](https://www.sec.gov/Archives/edgar/data/1513845/000110465926027886/tm268879d1_6k.htm)).
3. **La vida contable.** Nebius 20-F, diciembre 2025: vida útil de 4 años hasta 2025, 5 desde enero 2026 ($167.6M al año menos de depreciación).
4. **El precio de mercado.** H100 de \~$8/hora en el pico de 2023 a $1-2 en 2025; índice SemiAnalysis de contratos a un año de $1.70 (octubre 2025) a $2.35 (marzo 2026). Bank of America: spot H100 $2.77 en agosto 2026 (+33% interanual), A100 plana en $1.65 ([resumen](https://shattered.io/h100-h200-b200-cloud-gpu-pricing-2026/)). Nebius subió su H100 on-demand de $3.85 a $4.50 el 1 de octubre de 2026 ([índice Uvik](https://uvik.net/blog/gpu-price-index/)). B200 on-demand \~$5.2-5.7/hora a mediados de 2026.
5. **La física.** Epoch AI, “Chip performance per dollar”: +49% al año de cálculo por dólar desde 2023.
6. **La cadencia de NVIDIA.** NVIDIA 10-K, enero 2025: nuevas soluciones de cómputo cada año y menor demanda de la generación actual cuando los clientes anticipan la siguiente.
7. **El coste del dinero.** CoreWeave: rendimiento de sus bonos a 2032 cerca del 15% el 14 de octubre de 2026; $640M de intereses en Q2 2026 ([nota](https://cryptobriefing.com/coreweave-shares-plunge-bond-yields-15/)). Nebius: deuda garantizada de $775M a SOFR+250 pb en julio 2026.
