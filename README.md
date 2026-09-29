# POO_Vladimir_Taller4
## Etapa 1. El objeto sin constructor
1. Crea la clase Paquete con cuatro atributos: codigo (String), destino (String), peso (double) y asegurado (boolean). No escribas ningún constructor. 
2. Crea la clase Envios con el método main. Crea un paquete con new Paquete() e imprime sus cuatro atributos, uno por línea.

Comprobación: la salida muestra Código: null, Destino: null, Peso: 0.0 y Asegurado: false. Anota en tus respuestas
por qué aparecen esos valores.

### ***IMAGEN***
<img width="2304" height="4096" alt="1000111857" src="https://github.com/user-attachments/assets/adb2b5ee-a73d-4ff1-b11c-6c2eac69af09" />


Aparecen los valors ***null null 0,0 y false*** porque si no le asignamos ningun valor a los atributos (dependiendo de su tipo de dato varia) nos va a arrojar esos valores especificos

## Etapa 2. Constructor con parámetros y this
1. Agrega a Paquete un constructor que reciba los cuatro datos, con parámetros que se llamen exactamente igual
que los atributos. Usa this para asignarlos.
2. Agrega el método mostrarInformacion(), que imprima los datos en una sola línea con este formato:
P-001 -> Manizales | 3.0 kg | asegurado: true
3. En main, crea p1 = new Paquete("P-001", "Manizales", 3.0, true) y llama a
mostrarInformacion().
4. Observa que la línea new Paquete() de la Etapa 1 ya no compila. Anota el mensaje de NetBeans y explica la causa en una línea. Luego elimina esa línea.

***// One or more projects were compiled with errors*** *Esto pasa porque estamos intentando poner mas de un paquete en una misma clase, eso no se puede hacer*

*Comprobación:* se imprime P-001 -> Manizales | 3.0 kg | asegurado: true. Si ves null o 0.0, revisa el uso de this en
el constructor.

### ***IMAGEN***  
<img width="4096" height="2304" alt="1000111897" src="https://github.com/user-attachments/assets/b75ba11c-b759-47a8-9cb8-cf2f20b38dd0" />
<img width="4096" height="2304" alt="1000111898" src="https://github.com/user-attachments/assets/7242888e-ee86-4532-acbb-44ac209c6fcf" />


## Etapa 3. Sobrecarga de constructores y this(...)

1. Agrega un constructor que reciba solo el código y el destino. El paquete debe quedar con peso 1.0 y sin seguro.
Este constructor no debe asignar atributos directamente: debe delegar con this(...) en el constructor de la
Etapa 2.
2. Agrega un constructor que reciba solo el código. El destino debe quedar como "Por asignar". Debe delegar con
this(...) en el constructor del punto anterior.
3. En main, crea p2 = new Paquete("P-002", "Pereira") y p3 = new Paquete("P-003"), y muestra la
información de ambos.
Comprobación: se imprimen P-002 -> Pereira | 1.0 kg | asegurado: false y P-003 -> Por asignar | 1.0 kg |
asegurado: false.

### ***IMAGEN***  
<img width="4096" height="2304" alt="1000111898" src="https://github.com/user-attachments/assets/cb495b47-363d-4e11-bb05-065c30825ecd" />

# Etapa 4. Métodos con parámetros y valor de retorno
1. Agrega el método actualizarPeso(double peso), con el parámetro llamado igual que el atributo, que cambie el
peso del paquete.
2. Agrega el método calcularCosto(), que devuelva el costo del envío: 5000 por cada kilo y, si el paquete está
asegurado, 8000 adicionales.
3. En main, actualiza el peso de p3 a 2.5. Luego calcula en una variable total la suma de los costos de p1, p2 y p3,
usando los valores devueltos, e imprímela.
Comprobación: el costo de p1 es 23000.0, el de p2 es 5000.0 y el de p3 es 12500.0, así que se imprime Total del
envío: 40500.0

### ***IMAGEN***
<img width="4096" height="2304" alt="1000111903" src="https://github.com/user-attachments/assets/dde6f43e-cec9-413e-9df7-b7f450a18999" />


# Etapa 5. Sobrecarga de métodos
1. Agrega una segunda versión, calcularCosto(double tarifaPorKilo), que use la tarifa recibida en lugar de 5000 y
conserve el recargo del seguro.
2. En main, imprime p1.calcularCosto(4000) y p2.calcularCosto(4000).
3. Antes de ejecutar, escribe en tus respuestas qué versión de calcularCosto se ejecuta en cada una de estas tres
llamadas y por qué: p1.calcularCosto(), p1.calcularCosto(4000) y p1.calcularCosto("4000").

***// El primer p1.calcularCosto() va a usar la primera version del calcularCosto hecho, p1.calcularCosto(4000) va a utilizar la segunda version porque le estamos dando un valor y p1.calcularCosto("4000") tira error porque entre comillas es un String y no puede pasar a double asi porque si***

Comprobación: se imprimen 20000.0 y 4000.0. La tercera llamada no compila, porque no existe ninguna versión
que reciba un String.

### ***IMAGEN***
<img width="4096" height="2304" alt="1000111899" src="https://github.com/user-attachments/assets/65082c7b-0f2e-4e08-bf78-5281ce2391e4" />

# 8. Parte B: aplicación autónoma, la clase Habitacion

Aplica el mismo procedimiento para modelar las habitaciones de un hotel. Esta vez debes diseñar la clase por tu
cuenta, sin una guía paso a paso. Primero dibuja el diagrama y después implementa.
Requisitos:

 Atributos: numero (int), tipo (String), precioNoche (double) y ocupada (boolean).

 Un constructor completo que reciba los cuatro datos, usando this.

 Un constructor que reciba solo el número y el tipo, con precio de 120000 por noche y sin ocupar, que delegue
con this(...).

 Método ocupar(), que marque la habitación como ocupada, y método estaDisponible(), que devuelva true si
no está ocupada.

 Método calcularEstadia(int noches), que devuelva el valor de la estadía.

 Sobrecarga calcularEstadia(int noches, double descuento), donde el descuento es un porcentaje. Debe
reutilizar la versión de un parámetro.

 Método mostrarInformacion().

 Clase Hotel con main: crea al menos tres habitaciones usando los dos constructores, ocupa una, muestra la
información de todas e imprime el valor de una estadía de 3 noches con y sin descuento.

 Diagrama de clases de Habitacion en draw.io, con sus constructores y los métodos sobrecargados, exportado
como PNG.

Comprobación: para una habitación de 120000 por noche, 3 noches cuestan 360000.0 y, con un descuento del
10%, 324000.0.

### ***UML***

<img width="232" height="252" alt="Diagrama sin título drawio" src="https://github.com/user-attachments/assets/183435fa-300e-43cf-95f3-d0496f967198" />

### ***IMAGEN***
<img width="4096" height="2304" alt="etap" src="https://github.com/user-attachments/assets/ea60c432-3dd9-49d7-bd07-a24c81e3a0c8" />

# 9. Parte C: retos y análisis
1. Analiza estas cuatro declaraciones de constructores para la clase Habitacion e indica cuáles pueden existir al
mismo tiempo en la clase y cuáles no. Justifica cada caso con el concepto de firma.

A.Habitacion(int n, String t)

B.Habitacion(int numero, String tipo)

C.Habitacion(String tipo, int numero)

D.Habitacion(int numero)


***// La A no puede estar con la B porque ambas utilizan el int y string en el mismo lugar, asi que esas dos no podrian estar juntas***

3. Agrega a Paquete el método esPesado(), que devuelva true si el peso supera los 5 kilos, y úsalo en main dentro
de un if para imprimir un aviso de manejo especial.

5. Agrega a Paquete una sobrecarga mostrarInformacion(String encabezado) que imprima el encabezado y luego
reutilice la versión sin parámetros.

7. Escribe un programa corto que demuestre el paso por valor: un método que modifique su parámetro de tipo
double y un main que muestre que la variable original no cambió.

# 10. Preguntas de comprensión

Responde con tus propias palabras. Hacen parte de los entregables.

1. ¿Qué diferencias hay entre un constructor y un método? Menciona al menos tres.
   // 1. El constructor debe tener el mismo nombre que la clase, el metodo no.
   2. El constructor no tiene ningun tipo de retorno, el metodo si.
   3. El constructor se ejecuta automaticamente, el metodo toca llamarlo
      
3. ¿Por qué new Paquete() dejó de compilar en la Etapa 2? ¿Qué harías si la empresa necesitara seguir creando
paquetes sin datos?
  ***// Porque ya no habian datos, y si la empresa necesita hario algo con void o con otras funciones para que no tire error***
4. ¿Qué ocurriría si en el constructor de Paquete escribieras peso = peso; en lugar de this.peso = peso;? ¿El
programa compilaría?
  ***// No lo haria porque estaria agarrando el mismo parametro***
5. ¿Qué es la firma de un método y por qué el tipo de retorno no sirve para distinguir dos versiones
sobrecargadas?
***// Porque en los constructores no hay ningun tipo de retorno***

6. ¿Qué ventaja tiene que los constructores abreviados de Paquete deleguen con this(...) en lugar de asignar los
atributos ellos mismos?
***// Porque asi, el codigo seria mucho mas simplificado y el codigo no se veria abrumado por muchas operaciones***
