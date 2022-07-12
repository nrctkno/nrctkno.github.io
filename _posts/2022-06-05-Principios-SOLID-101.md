---
layout: post
title: Principios SOLID 101
categories: [Diseño de sistemas]
---

El propósito de este artículo es brindar un resumen conciso sobre los tan afamados principios SOLID. Es común que se los mencione durante entrevistas de trabajo y charlas sobre buenas prácticas de implementación de código. Sin embargo, también es común que olvidemos el significado y objeto de cada uno de estos principios.

<!--more-->

SOLID es, valga la redundancia, un conjunto de principios de diseño que nos alientan a crear software más mantenible, fácil de entender y flexible. De esta forma, mientras nuestras aplicaciones crecen en tamaño, podemos reducir su complejidad, ahorrándonos dolores de cabeza. Nos permiten mantener una alta cohesión (cooperación entre clases) y un bajo acoplamiento (dependencia). Los principios son:

### Single responsibility - Responsabilidad única

Nos indica que una clase sólo debería tener una única responsabilidad. Más aún, debería tener una única razón para cambiar. Beneficios:
- Testing: los test cases para la clase tendrán muchísimos menos casos que testear.
- Menor acoplamiento: al tener menos funcionalidad, tendrá menos dependencias.
- Organización: es más fácil encontrar algo en clases pequeñas y bien organizadas que en clases monolíticas grandes.

### Open/Closed - Abierto para extenderse / cerrado para modificarse

Recomienda que extendamos una clase en lugar de modificar el código de la original, lo cual podría ocasionar potenciales errores. La excepción a esto, desde luego, es cuando efectivamente debemos corregir un error en una clase. Entonces la idea es que si debo agregar nuevas características a una entidad que está probada y funciona correctamente, mejor creo una subclase, e implemento en la misma las nuevas funcionalidades.

### Liskov Substitution - Sustitución de Liskov

Las clases derivadas deben poder sustituirse por su clase base. Es decir que las  subclases o implementaciones de interfaces no deberían ocultar o quitar funcionalidades definidas “más arriba” (como hacer privado un método que antes era público o arrojar una excepción), ya que se rompe con la generalidad definida por las superclases/interfaces.

### Interface Segregation - Segregación de interfaz

Simplemente indica que las interfaces grandes deben dividirse en otras más pequeñas, ya que haciendo esto nos podemos asegurar que las clases que las implementen sólo necesiten preocuparse por los métodos que son de su interés. Por ejemplo, una interfaz AgenteInmobiliario que describe los métodos tasar(), vender() y firmarBoleto() podría claramente separarse en tres interfaces: Tasador:tasar(), Vendedor:vender() y Notario:firmarBoleto().

### Dependency Inversion - Inversión de dependencias

Consiste en desacoplar módulos de software. De esta forma, en vez de tener módulos de alto nivel dependiendo de otros de bajo nivel, ambos pueden depender de abstracciones. A grandes rasgos, se logra utilizando interfaces en lugar de clases explícitas al momento de definir cómo se compone mi clase objetivo. De esta forma puedo cambiar los tipos de componentes sin necesidad de modificar la clase objetivo.