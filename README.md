# Resolucion prueba de ingreso Facundo Kuzis


Este script tiene como objetivo determinar la existencia o no de posibilidades de arbitraje en el mercado de futuros del Rofex. Para ello, se automatizará la extracción en tiempo real de la información de precios de mercado de los contratos financieros brindada por la plataforma 'Remarkets', junto a los de sus activos subyacentes, obtenidos con 'Yahoo Finance'. 


## Arbitraje

El tipo de arbitraje que se estará buscando es el que surge a partir de las tasas implícitas calculadas al comparar los precios de los contratos a futuro, tanto los 'bid' como los 'ask', con los precios spot de los activos subyacentes que representan. El arbitraje existirá cuando los precios de los distintos instrumentos permitan 'pedir prestado' a una tasa menor a la que se puede 'colocar', para un mismo plazo. En este proyecto, se considera 'pedir prestado' a vender una acción en t = 0, recibiendo el dinero hoy, y recomprarla a futuro, fijando el costo a devolver al vencimiento. La operación contraria es la de 'colocar', donde se compra la acción en spot, 'invirtiendo' el dinero hoy, para luego venderla a futuro, recibiendo el beneficio pactado.


## Funciones
Para lograr este objetivo, se construyeron las siguientes funciones:

* get_f_prices:     Obtiene los precios bid y ask del instrumento especificado utilizando la biblioteca pyRofex.

* get_vencimiento:     Obtiene la fecha de vencimiento del instrumento especificado utilizando la biblioteca pyRofex.

* calcular_tasa_implicita: Calcula la tasa implícita para los precios de los instrumentos financieros dados.

* info_instrumentos: Crea un DataFrame con información acerca de los instrumentos.

* get_prices:  Actualiza un DataFrame de instrumentos con los precios bid y ask de los contratos, precios spot de los activos subyacentes, y tasas implícitas.

* verificar_arbitraje: Verifica si existe un arbitraje a partir de los precios de los subyacentes y los contratos.

* main:  Función principal del programa.     Obtiene la información de los instrumentos, los precios de mercado, y calcula posibles arbitrajes.
