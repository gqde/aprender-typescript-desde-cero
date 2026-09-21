 #  TypeScript — De Cero a Master

Este repositorio fue creado con un objetivo muy claro:

> **Convertir a cualquier desarrollador comprometido en un profesional capaz de dominar TypeScript desde sus fundamentos hasta sus áreas más avanzadas de ingeniería.**

Aquí no encontrarás un curso superficial enfocado únicamente en aprender sintaxis básica, declarar algunas interfaces o escribir unas cuantas funciones genéricas.

La meta de este roadmap es mucho más profunda.

Este `README.md` contiene una ruta estructurada de:

```text
50 módulos
×
100 temas por módulo
=
5,000 temas de TypeScript
```

acompañados por:

```text
2,000 preguntas de evaluación
50 exámenes prácticos
50 proyectos
retos de programación
type challenges
laboratorios
ejercicios de arquitectura
análisis del compilador
y un proyecto final Master
```

El objetivo es llevarte progresivamente desde:

```ts
const message: string = "Hello TypeScript";
```

hasta ser capaz de comprender, diseñar y mantener sistemas de tipos avanzados como:

```ts
type DeepReadonly<T> =
    T extends (...args: any[]) => unknown
        ? T
        : T extends readonly (infer U)[]
            ? readonly DeepReadonly<U>[]
            : T extends object
                ? {
                    readonly [K in keyof T]:
                        DeepReadonly<T[K]>
                  }
                : T;
```

Pero dominar TypeScript no significa simplemente aprender a escribir tipos cada vez más complicados.

Un desarrollador realmente avanzado debe saber:

* cuándo utilizar inferencia;
* cuándo declarar tipos explícitamente;
* cuándo utilizar `interface`;
* cuándo utilizar `type`;
* cuándo utilizar generics;
* cuándo una union es mejor que una jerarquía de clases;
* cuándo utilizar `unknown`;
* por qué evitar `any`;
* cómo diseñar APIs type-safe;
* cómo representar estados imposibles;
* cómo crear abstracciones reutilizables;
* cómo controlar la inferencia del compilador;
* cómo diseñar librerías;
* cómo trabajar con declaration files;
* cómo analizar problemas de rendimiento;
* y, especialmente, **cuándo mantener una solución simple**.

---

# 🎯 Objetivo del repositorio

Este repositorio está diseñado para desarrolladores que quieran dejar de utilizar TypeScript únicamente como:

```text
JavaScript + anotaciones de tipos
```

y comenzar a comprenderlo como lo que realmente es:

```text
un sistema de tipos extremadamente poderoso
+
un compilador
+
una plataforma de análisis estático
+
una infraestructura para construir herramientas
+
una capa de seguridad para grandes codebases
```

A lo largo de la ruta aprenderás desde:

```text
string
number
boolean
arrays
objects
functions
interfaces
```

hasta:

```text
Generic Constraints
Mapped Types
Conditional Types
infer
Template Literal Types
Recursive Types
Variadic Tuples
Branded Types
Type-State
Type-Level Algorithms
Type-Safe DSLs
Declaration Files
Module Resolution
Project References
Compiler Architecture
AST
Language Service
```

---

# 🧠 La filosofía de esta ruta

Este roadmap sigue una idea fundamental:

> **No memorices TypeScript. Aprende a razonar con TypeScript.**

Memorizar que existe:

```ts
Partial<T>
```

no significa dominar TypeScript.

Debes comprender cómo podría construirse:

```ts
type MyPartial<T> = {
    [K in keyof T]?: T[K];
};
```

Memorizar:

```ts
ReturnType<T>
```

tampoco es suficiente.

Debes llegar a comprender:

```ts
type MyReturnType<T> =
    T extends (...args: any[]) => infer R
        ? R
        : never;
```

Y todavía más importante:

debes entender **por qué funciona**.

La meta no es copiar tipos avanzados de Stack Overflow, documentación o repositorios externos.

La meta es que puedas construirlos tú mismo.

---

# 🏗️ Cómo está organizada la ruta

Los 50 módulos están organizados de manera progresiva.

No debes comenzar directamente con:

```text
infer
conditional types
recursive types
type-level parsers
```

sin comprender previamente:

```text
assignability
inference
unions
narrowing
generics
keyof
indexed access
mapped types
```

Por eso la ruta avanza por niveles.

## Nivel 1 — Fundamentos

Aprenderás cómo funciona TypeScript, su compilador, configuración, inferencia y sistema básico de tipos.

## Nivel 2 — Sistema de tipos

Profundizarás en objetos, arrays, tuples, unions, intersections, aliases e interfaces.

## Nivel 3 — Funciones y Narrowing

Dominarás funciones type-safe, overloads, control flow analysis, guards y assertions.

## Nivel 4 — Clases y Generics

Trabajarás con programación orientada a objetos, generics, constraints y relaciones entre tipos.

## Nivel 5 — Type Manipulation

Entrarás en:

```text
Mapped Types
Conditional Types
infer
Template Literal Types
Utility Types
```

## Nivel 6 — Type-Level Programming

Comenzarás a construir algoritmos utilizando el propio sistema de tipos.

## Nivel 7 — Arquitectura de librerías

Aprenderás module resolution, declarations, augmentation y diseño de APIs públicas.

## Nivel 8 — Ecosistema avanzado

Trabajarás con decorators, generators, JSX typing, JavaScript interoperability y grandes proyectos.

## Nivel 9 — Ingeniería de tipos

Construirás:

```text
type-state systems
builders
DSLs
parsers
type-level algorithms
advanced generic APIs
```

## Nivel 10 — Master Engineering

Estudiarás:

```text
compiler performance
AST
Compiler API
Language Service
static analysis
large-scale architecture
```

y finalizarás construyendo un proyecto TypeScript Master.

---

# 🧪 No basta con leer

Este repositorio no está diseñado para ser leído como un libro y después olvidado.

Cada módulo contiene:

```text
100 temas
40 preguntas
1 examen práctico
1 proyecto
criterios de dominio
```

La metodología recomendada es:

```text
Aprender
↓
Experimentar
↓
Romper código
↓
Leer errores
↓
Corregir
↓
Implementar
↓
Explicar
↓
Evaluarte
↓
Construir
```

Si solamente lees los temas, no dominarás TypeScript.

Debes escribir código.

Mucho código.

---

# ⚠️ Regla fundamental

Durante esta ruta intenta evitar utilizar:

```ts
any
```

como solución automática.

También evita solucionar cualquier error escribiendo:

```ts
value as Something
```

sin comprender primero por qué TypeScript está rechazando tu código.

El compilador no es tu enemigo.

Los errores del compilador forman parte del aprendizaje.

Cuando TypeScript muestre algo como:

```text
Type 'X' is not assignable to type 'Y'
```

no intentes únicamente hacer desaparecer el error.

Pregunta:

```text
¿Por qué X no puede asignarse a Y?

¿Qué relación está intentando comprobar TypeScript?

¿Qué información perdió el compilador?

¿Mi modelo de tipos representa realmente el dominio?

¿Estoy intentando convencer al compilador de algo que no puedo demostrar?
```

Ese tipo de preguntas es lo que comienza a desarrollar verdadero dominio del lenguaje.

---

# 🔥 Aprende a romper TypeScript

Una de las mejores formas de dominar el lenguaje es experimentar.

Crea código que falle.

Prueba cosas como:

```ts
type A = string & number;
```

o:

```ts
type Example<T> =
    T extends string
        ? "string"
        : "other";
```

Luego prueba:

```ts
type Result =
    Example<string | number>;
```

Antes de mirar el resultado, intenta predecir qué hará TypeScript.

Haz lo mismo con:

```text
unions
intersections
generics
conditional types
infer
mapped types
tuples
recursive types
```

Tu objetivo debe llegar a ser:

> **predecir lo que hará el compilador antes de preguntárselo al compilador.**

---

# 🧩 TypeScript no sustituye la validación runtime

Una de las ideas más importantes de toda esta ruta es comprender que:

```text
TypeScript protege compile time.
```

No significa que datos provenientes de:

```text
APIs
usuarios
archivos
JSON
bases de datos
formularios
mensajes externos
```

sean automáticamente seguros.

Por eso aprenderás a utilizar:

```ts
unknown
```

como frontera de confianza y después convertir datos externos en estructuras confiables mediante validación.

El objetivo será aprender la diferencia entre:

```text
"TypeScript dice que esto es un User"
```

y:

```text
"he comprobado que este dato realmente cumple el contrato User"
```

---

# 🏆 ¿Qué significa dominar TypeScript?

Dominar TypeScript no significa conocer todas las palabras reservadas.

Tampoco significa resolver solamente Type Challenges extremadamente complejos.

Al finalizar esta ruta deberías ser capaz de:

```text
leer TypeScript avanzado

escribir TypeScript avanzado

entender errores complejos

diseñar APIs type-safe

crear generics reutilizables

modelar dominios

representar estados correctamente

eliminar estados imposibles

trabajar con unknown

usar never estratégicamente

crear type guards

crear utility types

trabajar con mapped types

trabajar con conditional types

utilizar infer

crear recursive types

manipular tuples

crear branded types

construir builders type-safe

crear pequeñas DSLs

escribir declaration files

diseñar librerías

trabajar con Project References

analizar rendimiento del compilador

entender un AST

crear herramientas de análisis

y mantener codebases TypeScript grandes
```

Pero existe una habilidad todavía más importante:

```text
saber cuándo NO utilizar
un tipo extremadamente complejo.
```

---

# 💡 TypeScript avanzado no significa TypeScript innecesariamente complejo

El objetivo de este repositorio no es producir código como:

```ts
type MegaUltraGeneric<
    T,
    U extends keyof T,
    X extends {
        [K in U]:
            T[K] extends infer R
                ? R
                : never
    }
> = ...
```

solamente porque sea posible.

Una solución como:

```ts
interface User {
    id: string;
    name: string;
}
```

puede ser mucho mejor.

La ingeniería profesional consiste en encontrar el equilibrio entre:

```text
seguridad
inferencia
legibilidad
mantenibilidad
rendimiento del compilador
experiencia del desarrollador
```

---

# 📈 Progresión esperada

Al principio probablemente pensarás:

```text
"TypeScript es JavaScript con tipos."
```

Después:

```text
"TypeScript tiene generics."
```

Luego:

```text
"El sistema de tipos puede transformar otros tipos."
```

Más adelante:

```text
"Puedo programar lógica dentro del sistema de tipos."
```

Y finalmente:

```text
"Debo decidir conscientemente
qué lógica pertenece al type system
y qué lógica pertenece al runtime."
```

Ese último punto representa un nivel mucho más maduro de ingeniería TypeScript.

---

# 👨‍💻 Para quién está diseñado este roadmap

Esta ruta está pensada para:

```text
estudiantes

desarrolladores autodidactas

frontend developers

backend developers

full stack developers

library authors

engineers que trabajan con JavaScript

developers que ya utilizan TypeScript
pero quieren entenderlo profundamente

developers preparándose para
codebases de gran escala
```

No necesitas ser experto antes de comenzar.

La ruta empieza desde los fundamentos.

Lo que sí necesitas es:

```text
disciplina

curiosidad

práctica

paciencia

y disposición para investigar errores
```

---

# 🚫 Este no es un roadmap de frameworks

Este repositorio está dedicado exclusivamente a:

# **TypeScript**

No intenta enseñar al mismo tiempo:

```text
React
Node.js
Next.js
NestJS
Angular
Docker
Kubernetes
Databases
Cloud
```

Cada una de esas tecnologías merece su propia ruta profunda.

Aquí el objetivo es construir una base tan sólida de TypeScript que posteriormente puedas utilizarla en cualquier ecosistema.

---

# 🧭 Cómo utilizar este repositorio

La recomendación principal es seguir los módulos en orden:

```text
Módulo 1
↓
Módulo 2
↓
Módulo 3
↓
...
↓
Módulo 50
```

No avances solamente porque terminaste de leer.

Avanza cuando puedas:

```text
explicar el tema

escribirlo desde cero

detectar errores

corregirlos

resolver el quiz

completar el examen

construir el proyecto
```

Si no puedes explicar un concepto sin copiar una definición, todavía puedes profundizar más.

---

# 📊 Regla de aprobación

Como referencia, puedes considerar un módulo dominado cuando logres al menos:

```text
85 % del quiz correcto
+
examen práctico completado
+
proyecto funcional
+
capacidad de explicar las decisiones
```

Si fallas un tema, no significa que debas abandonar la ruta.

Significa que encontraste exactamente qué necesitas reforzar.

---

# 🧠 Aprende como ingeniero

No preguntes solamente:

```text
¿Cómo hago esto?
```

Pregúntate también:

```text
¿Por qué funciona?

¿Por qué TypeScript infirió este tipo?

¿Qué ocurriría si cambio esta variable?

¿Qué relación existe entre estos tipos?

¿Dónde ocurre narrowing?

¿Qué está comprobando extends?

¿Por qué aparece never?

¿Por qué se distribuyó esta union?

¿Qué información está capturando infer?

¿Cuál es el coste de esta abstracción?

¿Existe una solución más sencilla?
```

Estas preguntas transforman conocimiento superficial en conocimiento transferible.

---

# 🏁 El objetivo final

Cuando completes este roadmap, la meta no es poder decir:

> “Terminé 50 módulos de TypeScript.”

La meta es poder abrir una codebase TypeScript compleja y pensar:

```text
Entiendo cómo está modelado este dominio.

Entiendo cómo funciona esta inferencia.

Entiendo por qué este generic existe.

Entiendo cómo se relacionan estos tipos.

Entiendo por qué esta union es discriminada.

Entiendo cómo este conditional type transforma T.

Entiendo por qué infer obtiene este valor.

Entiendo cómo se genera esta declaration.

Entiendo cómo se resuelve este módulo.

Entiendo por qué esta API no permite este estado.

Entiendo cómo simplificar este diseño.
```

Ese es el verdadero objetivo.

# **No solamente utilizar TypeScript.**

# **Entender TypeScript.**

# **Diseñar con TypeScript.**

# **Pensar en TypeScript.**

# **Y dominar TypeScript como herramienta de ingeniería.**

---

## 🚀 Comienza con el Módulo 1

No intentes aprender los 5,000 temas al mismo tiempo.

Empieza con uno.

Domínalo.

Después continúa con el siguiente.

```text
1 tema
→
1 concepto dominado
→
1 módulo
→
10 módulos
→
50 módulos
→
TypeScript Mastery
```

El compilador será uno de tus principales profesores durante esta ruta.

Lee sus errores.

Rétalo.

Experimenta.

Construye.

Y continúa hasta que TypeScript deje de parecer una colección de reglas y comience a convertirse en una herramienta que puedes razonar con precisión.

# 📌 Requisitos previos

Este roadmap **no está diseñado para enseñar JavaScript desde cero**.

Antes de comenzar, se espera que el desarrollador ya tenga una base sólida de JavaScript moderno.

Como mínimo deberías sentirte cómodo trabajando con:

```text
variables: let y const

tipos y valores de JavaScript

operadores

condicionales

loops

functions

arrow functions

scope

closures

arrays

objects

destructuring

spread y rest

map

filter

reduce

callbacks

classes

prototypes

this

ES Modules

import / export

Promises

async / await

manejo de errores

event loop

JSON

ES2015+
```

También deberías poder leer y escribir código JavaScript como este sin dificultad:

```js
const users = [
  { id: 1, name: "Ana", active: true },
  { id: 2, name: "John", active: false },
];

const activeUsers = users
  .filter(user => user.active)
  .map(({ id, name }) => ({
    id,
    name,
  }));

async function getUser(id) {
  const response = await fetch(`/users/${id}`);

  if (!response.ok) {
    throw new Error("Unable to load user");
  }

  return response.json();
}
```

La pregunta principal de esta ruta no será:

> **¿Cómo funciona JavaScript?**

Sino:

> **¿Cómo puede TypeScript modelar, analizar y hacer más seguro este código JavaScript?**

---

## ¿Por qué JavaScript es un requisito?

Porque TypeScript sigue utilizando la semántica de JavaScript.

Por ejemplo:

```ts
const user = {
  name: "John",
};

user.name;
```

TypeScript puede analizar que 


# PARTE I — FUNDAMENTOS PROFESIONALES DE TYPESCRIPT

# MÓDULO 1 — Introducción profesional a TypeScript

### Qué aprenderás

Comprenderás qué es TypeScript, qué problemas resuelve, cómo se relaciona con JavaScript, cómo funciona su compilación, qué significa el tipado estático y cómo pensar correctamente sobre TypeScript desde el principio.

### Por qué debes aprenderlo

Antes de escribir sistemas de tipos complejos necesitas comprender que TypeScript es principalmente un **analizador estático de tipos para JavaScript** y que los tipos normalmente desaparecen durante la emisión de JavaScript.

### Al finalizar podrás

Explicar el funcionamiento general de TypeScript, crear programas básicos, interpretar errores del compilador y distinguir claramente entre tiempo de compilación y tiempo de ejecución.

### 100 temas

**1–10:** 1. Qué es TypeScript; 2. Origen de TypeScript; 3. Objetivos del lenguaje; 4. TypeScript vs JavaScript; 5. Superset de JavaScript; 6. Tipado estático; 7. Tipado gradual; 8. Type checking; 9. Compilación; 10. Transpilación.

**11–20:** 11. Tiempo de compilación; 12. Tiempo de ejecución; 13. Erasure de tipos; 14. JavaScript generado; 15. `tsc`; 16. TypeScript Compiler; 17. Archivos `.ts`; 18. Archivos `.tsx`; 19. Archivos `.d.ts`; 20. Archivos `.js`.

**21–30:** 21. Sistema estructural de tipos; 22. Inferencia; 23. Anotaciones; 24. Type safety; 25. Soundness pragmática; 26. Compatibilidad con JavaScript; 27. Progressive adoption; 28. TypeScript en proyectos existentes; 29. TypeScript en proyectos nuevos; 30. Language Service.

**31–40:** 31. Autocompletado; 32. IntelliSense; 33. Hover information; 34. Go to Definition; 35. Find References; 36. Rename Symbol; 37. Diagnostics; 38. Refactoring; 39. Editor integration; 40. Source maps.

**41–50:** 41. Errores sintácticos; 42. Errores semánticos; 43. Errores de tipos; 44. Warnings conceptuales; 45. Código válido; 46. Código emitible; 47. Código type-safe; 48. Runtime errors; 49. Compile-time errors; 50. Limitaciones del type system.

**51–60:** 51. Structural typing; 52. Duck typing y TS; 53. Nominal typing como contraste; 54. Variables y tipos; 55. Expresiones y tipos; 56. Funciones y tipos; 57. Objetos y tipos; 58. Clases y tipos; 59. Módulos y tipos; 60. Librerías y tipos.

**61–70:** 61. Declaraciones de tipos; 62. DefinitelyTyped; 63. `@types`; 64. Ecosistema npm; 65. Semantic versioning de TS; 66. Compatibilidad entre versiones; 67. Release notes; 68. Handbook; 69. TSConfig Reference; 70. Playground.

**71–80:** 71. TypeScript Playground; 72. Inspecting emitted JS; 73. Inspecting inferred types; 74. Compiler diagnostics; 75. Type errors como feedback; 76. Diseñar antes de implementar; 77. Modelado de dominio; 78. Illegal states; 79. Static guarantees; 80. Runtime validation.

**81–90:** 81. Diferencia entre tipos y validación; 82. Datos externos; 83. Trust boundaries; 84. Type assertions y riesgos; 85. `any` y pérdida de seguridad; 86. `unknown` como alternativa; 87. Strict mode; 88. Filosofía de `strict`; 89. Type-driven development; 90. API type-first.

**91–100:** 91. Evolución de TypeScript; 92. Backward compatibility; 93. Breaking changes; 94. Código idiomático; 95. Legibilidad de tipos; 96. Complejidad accidental; 97. Principio de tipos simples; 98. TypeScript profesional; 99. Estrategia de aprendizaje; 100. Mentalidad para dominar el lenguaje.

### Quiz — 40 preguntas

1. ¿Qué problema principal resuelve TypeScript? 2. ¿TypeScript se ejecuta directamente en el navegador? 3. ¿Qué significa tipado estático? 4. ¿Qué significa tipado gradual? 5. ¿Qué hace `tsc`? 6. ¿Qué es type erasure? 7. ¿Qué diferencia existe entre compile time y runtime? 8. ¿Qué contiene un `.ts`? 9. ¿Qué contiene un `.d.ts`? 10. ¿Qué significa structural typing?

2. ¿TypeScript reemplaza JavaScript? 12. ¿Los tipos existen normalmente en runtime? 13. ¿Qué es inferencia de tipos? 14. ¿Qué es una anotación? 15. ¿Qué proporciona Language Service? 16. ¿Qué es IntelliSense? 17. ¿Qué representa type safety? 18. ¿Qué es un runtime error? 19. ¿Qué es un type error? 20. ¿Qué significa progressive adoption?

3. ¿Qué es DefinitelyTyped? 22. ¿Para qué sirve `@types`? 23. ¿Qué es TypeScript Playground? 24. ¿Qué significa type-driven development? 25. ¿Qué es una trust boundary? 26. ¿Los tipos validan automáticamente JSON externo? 27. ¿Por qué `any` reduce seguridad? 28. ¿Qué ventaja presenta `unknown`? 29. ¿Para qué sirve `strict`? 30. ¿Qué es una type assertion?

4. ¿TypeScript garantiza ausencia total de errores? 32. ¿Cuál es la diferencia entre typing y validation? 33. ¿Qué significa API type-first? 34. ¿Qué es soundness? 35. ¿Por qué TypeScript prioriza compatibilidad con JS? 36. ¿Qué es un diagnóstico del compilador? 37. ¿Qué significa código idiomático? 38. ¿Qué papel tiene el editor? 39. ¿Por qué revisar JavaScript emitido? 40. ¿Qué debes dominar antes de metaprogramación de tipos?

### Examen práctico

Construye un programa `student-profile.ts` que modele un estudiante con nombre, edad, materias, promedio y estado activo. Introduce deliberadamente cinco errores de tipos, analiza los diagnósticos y corrígelos sin utilizar `any`.

### Proyecto del módulo

Construye una pequeña aplicación CLI denominada **TS Fundamentals Lab** con cinco archivos TypeScript que demuestren inferencia, anotaciones, objetos, funciones y errores detectados durante compilación.

### Criterio de dominio

Debes poder explicar sin memorizar **qué ocurre desde que escribes un `.ts` hasta que el runtime ejecuta JavaScript**, y completar el quiz con mínimo **34/40**.

---

# MÓDULO 2 — Toolchain, compilador y flujo de trabajo TypeScript

### Qué aprenderás

Aprenderás a controlar `tsc`, compilar archivos, observar JavaScript emitido, usar watch mode, interpretar diagnósticos y construir un flujo de desarrollo profesional.

### Por qué

Un experto en TypeScript debe comprender no solamente el lenguaje sino también cómo el compilador transforma y analiza el proyecto.

### Al finalizar podrás

Crear, compilar, diagnosticar y organizar proyectos TypeScript sin depender de configuraciones copiadas sin comprenderlas.

### 100 temas

**1–10:** 1. Instalación de TypeScript; 2. TypeScript local; 3. TypeScript global; 4. Versión del compilador; 5. Comando `tsc`; 6. Compilar un archivo; 7. Compilar varios archivos; 8. Directorio de salida; 9. Código emitido; 10. Errores de compilación.

**11–20:** 11. `tsc --version`; 12. `tsc --help`; 13. `tsc --init`; 14. `tsc --project`; 15. `tsc --watch`; 16. Watch mode; 17. Pretty diagnostics; 18. Incremental workflow; 19. Exit codes; 20. Compiler pipeline.

**21–30:** 21. Parsing; 22. AST conceptual; 23. Binding; 24. Type checking; 25. Emitting; 26. Diagnostics phases; 27. Syntactic diagnostics; 28. Semantic diagnostics; 29. Declaration diagnostics; 30. Emit diagnostics.

**31–40:** 31. `target`; 32. ECMAScript targets; 33. Downleveling; 34. ESNext; 35. ES2022; 36. ES2020; 37. Feature transformation; 38. Native runtime features; 39. Polyfills vs transpilation; 40. TypeScript no es polyfill.

**41–50:** 41. `outDir`; 42. `rootDir`; 43. `noEmit`; 44. `noEmitOnError`; 45. `removeComments`; 46. `sourceMap`; 47. `inlineSourceMap`; 48. `inlineSources`; 49. Declaration emit; 50. `declaration`.

**51–60:** 51. `.map` files; 52. Debugging con source maps; 53. `.d.ts` emitidos; 54. `declarationMap`; 55. Preservación de estructura; 56. Entrada vs salida; 57. Build artifacts; 58. Directorio `dist`; 59. Directorio `src`; 60. Limpieza de builds.

**61–70:** 61. Editor TypeScript version; 62. Workspace TypeScript; 63. Language server; 64. Editor diagnostics; 65. Quick Fix; 66. Code actions; 67. Auto imports; 68. Rename refactoring; 69. Extract function; 70. Extract constant.

**71–80:** 71. Type acquisition conceptual; 72. Compiler API introducción; 73. AST visualization; 74. Incremental compilation; 75. `.tsbuildinfo`; 76. Build caching; 77. Project root; 78. File discovery; 79. Explicit inputs; 80. Config-based inputs.

**81–90:** 81. `--listFiles`; 82. `--listEmittedFiles`; 83. `--showConfig`; 84. `--traceResolution`; 85. `--extendedDiagnostics`; 86. `--diagnostics`; 87. Compiler performance; 88. Memory diagnostics; 89. Resolución de problemas; 90. Reproducciones mínimas.

**91–100:** 91. Playground compiler options; 92. Comparing outputs; 93. Nightly TypeScript; 94. Stable TypeScript; 95. Version pinning; 96. Upgrade strategy; 97. Release testing; 98. Compiler regressions; 99. Toolchain reproducible; 100. Flujo profesional completo.

### Quiz — 40 preguntas

1. ¿Qué hace `tsc --init`? 2. ¿Para qué sirve `--watch`? 3. ¿Qué controla `target`? 4. ¿Qué es downleveling? 5. ¿Qué hace `outDir`? 6. ¿Qué hace `rootDir`? 7. ¿Qué hace `noEmit`? 8. ¿Qué diferencia hay con `noEmitOnError`? 9. ¿Qué genera `sourceMap`? 10. ¿Qué genera `declaration`?

2. ¿Qué es parsing? 12. ¿Qué representa un AST? 13. ¿Qué ocurre durante binding? 14. ¿Qué ocurre durante type checking? 15. ¿Qué significa emit? 16. ¿Qué es un diagnóstico semántico? 17. ¿Qué es `.tsbuildinfo`? 18. ¿Para qué sirve `--showConfig`? 19. ¿Qué hace `--traceResolution`? 20. ¿Para qué sirve `--listFiles`?

3. ¿Un transpiler agrega polyfills? 22. ¿Por qué no necesariamente? 23. ¿Para qué sirve declarationMap? 24. ¿Qué diferencia existe entre `src` y `dist`? 25. ¿Qué es workspace TypeScript? 26. ¿Por qué fijar versión? 27. ¿Qué es un Quick Fix? 28. ¿Qué es auto-import? 29. ¿Qué mide `--diagnostics`? 30. ¿Qué es una reproducción mínima?

4. ¿Qué significa incremental compilation? 32. ¿Cómo ayuda watch mode? 33. ¿Qué ventaja aporta `noEmit`? 34. ¿Qué significa build reproducible? 35. ¿Cuándo usar `ESNext`? 36. ¿Por qué inspeccionar JS emitido? 37. ¿Qué es TypeScript Nightly? 38. ¿Por qué probar upgrades? 39. ¿Qué función tiene Language Service? 40. Describe el pipeline conceptual del compilador.

### Examen práctico

Crea un proyecto con `src/`, `dist/`, sourcemaps y declaration emit. Compílalo mediante CLI usando al menos diez opciones diferentes y explica cada archivo producido.

### Proyecto

Construye **Compiler Laboratory**, donde una misma aplicación sea compilada hacia tres targets ECMAScript distintos y documenta las diferencias del JavaScript emitido.

### Dominio

Debes ser capaz de diagnosticar un proyecto utilizando únicamente `tsc`, sin depender inicialmente de herramientas externas.

---

# MÓDULO 3 — `tsconfig.json` desde cero

La existencia de `tsconfig.json` define la raíz de un proyecto TypeScript y permite controlar archivos y opciones del compilador. ([TypeScript][2])

### Qué aprenderás

A configurar proyectos TypeScript conscientemente.

### Por qué

Muchas dificultades profesionales de TypeScript provienen de configuraciones incorrectas, no del código.

### Al finalizar podrás

Construir configuraciones apropiadas para distintos proyectos y explicar cada decisión.

### 100 temas

**1–10:** 1. Propósito de `tsconfig.json`; 2. Raíz del proyecto; 3. JSON configuration; 4. `compilerOptions`; 5. `files`; 6. `include`; 7. `exclude`; 8. Globs; 9. Herencia de configuración; 10. `extends`.

**11–20:** 11. `target`; 12. `module`; 13. `lib`; 14. Bibliotecas estándar; 15. DOM typings; 16. ECMAScript typings; 17. `rootDir`; 18. `outDir`; 19. `baseUrl`; 20. Paths conceptuales.

**21–30:** 21. `strict`; 22. Strict family; 23. `noImplicitAny`; 24. `strictNullChecks`; 25. `strictFunctionTypes`; 26. `strictBindCallApply`; 27. `strictPropertyInitialization`; 28. `useUnknownInCatchVariables`; 29. `alwaysStrict`; 30. Strict migrations.

**31–40:** 31. `noUnusedLocals`; 32. `noUnusedParameters`; 33. `noImplicitReturns`; 34. `noFallthroughCasesInSwitch`; 35. `noUncheckedIndexedAccess`; 36. `noImplicitOverride`; 37. `noPropertyAccessFromIndexSignature`; 38. `allowUnreachableCode`; 39. `allowUnusedLabels`; 40. Quality flags.

**41–50:** 41. `esModuleInterop`; 42. `allowSyntheticDefaultImports`; 43. Interoperabilidad conceptual; 44. `moduleResolution`; 45. Runtime-aware resolution; 46. Package resolution; 47. Extension resolution; 48. Module format; 49. Node-style resolution; 50. Bundler-style resolution.

**51–60:** 51. `resolveJsonModule`; 52. JSON imports; 53. `isolatedModules`; 54. Single-file transpilation; 55. `verbatimModuleSyntax`; 56. Type-only imports; 57. Type-only exports; 58. Emit preservation; 59. Module detection; 60. `moduleDetection`.

**61–70:** 61. `skipLibCheck`; 62. Ventajas y riesgos; 63. `types`; 64. `typeRoots`; 65. Ambient types; 66. Global types; 67. Default inclusion; 68. Type package control; 69. Library conflicts; 70. Dependency typings.

**71–80:** 71. `declaration`; 72. `declarationMap`; 73. `emitDeclarationOnly`; 74. `sourceMap`; 75. `inlineSourceMap`; 76. `inlineSources`; 77. `removeComments`; 78. `importHelpers`; 79. `downlevelIteration`; 80. Emit configuration.

**81–90:** 81. `incremental`; 82. `composite`; 83. `tsBuildInfoFile`; 84. Project build mode; 85. Config inheritance; 86. Base config; 87. Development config; 88. Production config; 89. Testing config conceptual; 90. Shared configs.

**91–100:** 91. `showConfig`; 92. Debugging config; 93. Conflicting flags; 94. Defaults; 95. Version-dependent defaults; 96. Minimal tsconfig; 97. Strict tsconfig; 98. Library tsconfig; 99. Monorepo-ready config; 100. Auditoría de configuración.

### Quiz — 40 preguntas

1. ¿Qué representa `tsconfig.json`? 2. ¿Qué diferencia hay entre `files` e `include`? 3. ¿Qué hace `exclude`? 4. ¿Qué hace `extends`? 5. ¿Qué controla `target`? 6. ¿Qué controla `module`? 7. ¿Qué controla `lib`? 8. ¿Qué activa `strict`? 9. ¿Qué hace `noImplicitAny`? 10. ¿Qué cambia `strictNullChecks`?

2. ¿Qué hace `noUncheckedIndexedAccess`? 12. ¿Qué hace `noImplicitOverride`? 13. ¿Qué hace `isolatedModules`? 14. ¿Qué problema aborda `esModuleInterop`? 15. ¿Qué es module resolution? 16. ¿Qué hace `types`? 17. ¿Qué hace `typeRoots`? 18. ¿Qué significa declaration emit? 19. ¿Qué hace `emitDeclarationOnly`? 20. ¿Qué hace `incremental`?

3. ¿Qué significa `composite`? 22. ¿Qué contiene `.tsbuildinfo`? 23. ¿Qué hace `skipLibCheck`? 24. ¿Qué riesgos tiene? 25. ¿Qué es `verbatimModuleSyntax`? 26. ¿Por qué existen type-only imports? 27. ¿Qué es `moduleDetection`? 28. ¿Para qué sirve `resolveJsonModule`? 29. ¿Qué diferencia hay entre source maps e inline source maps? 30. ¿Qué hace `declarationMap`?

4. ¿Cómo diseñarías un tsconfig estricto? 32. ¿Por qué heredar configuraciones? 33. ¿Cuándo separar dev/prod? 34. ¿Qué significa configuración reproducible? 35. ¿Cómo inspeccionas la configuración final? 36. ¿Por qué los defaults importan? 37. ¿Puede cambiar el comportamiento entre versiones? 38. ¿Qué opción mejora la seguridad de índices? 39. ¿Qué opción verifica retornos? 40. ¿Qué configuración usarías como punto de partida profesional?

### Examen práctico

Diseña tres configuraciones heredadas: `tsconfig.base.json`, `tsconfig.dev.json` y `tsconfig.build.json`, justificando al menos 20 opciones.

### Proyecto

Construye **TS Config Matrix**, un repositorio que demuestre cómo diferentes configuraciones afectan inferencia, diagnósticos y JavaScript emitido.

### Dominio

Debes poder escribir un `tsconfig.json` estricto desde cero y justificar cada opción importante.

---

# MÓDULO 4 — Tipos primitivos e inferencia

### Qué aprenderás

A dominar el modelo básico de valores y cómo TypeScript infiere sus tipos.

### Por qué

Todo el sistema avanzado depende de entender correctamente los tipos fundamentales.

### Al finalizar podrás

Modelar valores primitivos evitando anotaciones redundantes.

### 100 temas

**1–10:** 1. `string`; 2. `number`; 3. `boolean`; 4. `bigint`; 5. `symbol`; 6. `null`; 7. `undefined`; 8. Primitivos; 9. Valores vs tipos; 10. Primitive wrappers.

**11–20:** 11. `String` vs `string`; 12. `Number` vs `number`; 13. `Boolean` vs `boolean`; 14. Boxed values; 15. Inferencia de strings; 16. Inferencia numérica; 17. Inferencia booleana; 18. Variable initialization; 19. Assignment checking; 20. Reassignment.

**21–30:** 21. Annotation syntax; 22. Type inference; 23. Contextual typing; 24. Type widening; 25. Literal widening; 26. `const` inference; 27. `let` inference; 28. Return inference; 29. Parameter annotations; 30. Property inference.

**31–40:** 31. Arithmetic typing; 32. Comparison expressions; 33. Boolean expressions; 34. String concatenation; 35. Template strings; 36. Numeric separators; 37. Hexadecimal numbers; 38. Binary numbers; 39. Octal numbers; 40. BigInt literals.

**41–50:** 41. Symbols únicos conceptualmente; 42. `typeof`; 43. JavaScript `typeof`; 44. TypeScript `typeof` posterior; 45. Undefined variables; 46. Optionality conceptual; 47. Nullable values; 48. Strict null checking; 49. Nullish values; 50. Nullish coalescing.

**51–60:** 51. Optional chaining; 52. Non-null assertion intro; 53. Truthiness; 54. Falsy values; 55. Numeric edge cases; 56. `NaN`; 57. `Infinity`; 58. Floating point; 59. Number safety; 60. BigInt limitations.

**61–70:** 61. Immutable primitive values; 62. Variable mutability; 63. Const binding; 64. Type compatibility; 65. Assignability; 66. Widened types; 67. Fresh literal types; 68. Context sensitivity; 69. Function context; 70. Object context.

**71–80:** 71. Union emergence; 72. Best common type intro; 73. Inference from expressions; 74. Inference from callbacks; 75. Generic inference preview; 76. Explicit vs inferred; 77. Annotation overuse; 78. Annotation underuse; 79. Public API annotations; 80. Local inference.

**81–90:** 81. `const` best practices; 82. Primitive conversion; 83. Type coercion awareness; 84. `Number()` typing; 85. `String()` typing; 86. `Boolean()` typing; 87. Parse functions; 88. Runtime parsing; 89. Static assumptions; 90. Validation boundaries.

**91–100:** 91. Type debugging; 92. Hover inspection; 93. `satisfies` preview; 94. Type assertions preview; 95. Errors de asignación; 96. Diagnostic messages; 97. Read errors structurally; 98. Minimal annotations; 99. Idiomatic inference; 100. Primitive modeling mastery.

### Quiz — 40 preguntas

1. ¿Qué diferencia existe entre `string` y `String`? 2. ¿Qué infiere `let x = "A"`? 3. ¿Qué infiere normalmente `const x = "A"`? 4. ¿Qué es widening? 5. ¿Qué es contextual typing? 6. ¿Qué representa `bigint`? 7. ¿Qué representa `symbol`? 8. ¿Qué diferencia hay entre `null` y `undefined`? 9. ¿Qué cambia `strictNullChecks`? 10. ¿Qué devuelve `typeof` en JS?

2. ¿Qué es una anotación? 12. ¿Cuándo puede omitirse? 13. ¿Qué es assignability? 14. ¿Qué es inferencia de retorno? 15. ¿Por qué evitar wrappers? 16. ¿Qué significa primitive immutability? 17. ¿Qué hace `??`? 18. ¿Qué hace `?.`? 19. ¿Qué es truthiness? 20. ¿Qué valores son falsy?

3. ¿Qué es `NaN`? 22. ¿Qué riesgo tiene floating point? 23. ¿Cuándo sirve bigint? 24. ¿Se mezcla directamente bigint con number? 25. ¿Qué significa local inference? 26. ¿Por qué anotar APIs públicas? 27. ¿Qué es runtime parsing? 28. ¿Los tipos validan conversiones externas? 29. ¿Qué es type coercion? 30. ¿Por qué preferir inferencia cuando es clara?

4. ¿Cómo inspeccionas un tipo inferido? 32. ¿Qué es literal widening? 33. ¿Qué diferencia existe entre binding y valor? 34. ¿`const` vuelve inmutable a un objeto completo? 35. ¿Por qué no? 36. ¿Qué es best common type? 37. ¿Qué produce `String(123)`? 38. ¿Qué produce `Boolean(0)`? 39. ¿Cuándo una anotación añade claridad? 40. ¿Cuándo resulta redundante?

### Examen

Implementa una calculadora financiera estrictamente tipada que trabaje con monedas, porcentajes y valores opcionales sin `any` ni assertions.

### Proyecto

Construye **Primitive Type Explorer**, con ejemplos ejecutables de todos los tipos primitivos, inferencia y widening.

### Dominio

34/40 + examen sin errores de compilación bajo `strict`.

---

# MÓDULO 5 — Literal Types, `as const` y `satisfies`

### Qué aprenderás

A representar valores exactos dentro del sistema de tipos.

### Por qué

Los literal types son fundamentales para unions discriminadas, APIs seguras y programación avanzada de tipos.

### Al finalizar podrás

Crear modelos mucho más precisos que simples `string` o `number`.

### 100 temas

**1–10:** 1. String literal types; 2. Numeric literal types; 3. Boolean literals; 4. Exact values; 5. Literal inference; 6. Widening; 7. Non-widening literals; 8. `const`; 9. `let`; 10. Literal annotations.

**11–20:** 11. Literal unions; 12. Status values; 13. Direction values; 14. HTTP methods como literals; 15. Command names; 16. Role names; 17. State modeling; 18. Magic strings; 19. Eliminación de magic strings; 20. Autocomplete seguro.

**21–30:** 21. `as const`; 22. Const assertions; 23. Readonly properties; 24. Readonly tuples; 25. Deep literal preservation; 26. Object literals; 27. Array literals; 28. Tuple inference; 29. Exact configuration objects; 30. Constant maps.

**31–40:** 31. Derivar unions de arrays; 32. `typeof array[number]`; 33. Derivar unions de objetos; 34. `keyof typeof`; 35. Value unions; 36. Lookup objects; 37. Enum-like objects; 38. Alternatives to enums; 39. Static constants; 40. Type derivation.

**41–50:** 41. `satisfies`; 42. Validation without widening; 43. `satisfies` vs annotation; 44. `satisfies` vs assertion; 45. Exact property checking; 46. Configuration typing; 47. Record validation; 48. Preserving inference; 49. Excess properties; 50. Safe configuration.

**51–60:** 51. Literal function parameters; 52. Literal returns; 53. Generic literal capture; 54. Const type parameters preview; 55. Narrow APIs; 56. Exhaustiveness foundations; 57. Discriminants; 58. Tagged objects; 59. State machine foundation; 60. Event names.

**61–70:** 61. Literal concatenation concept; 62. Template literal preview; 63. String domains; 64. Value spaces; 65. Closed sets; 66. Open strings; 67. Extensible unions; 68. String & `{}` patterns; 69. Completion behavior; 70. Domain constraints.

**71–80:** 71. Readonly consequence; 72. Mutation errors; 73. Clone before mutation; 74. Const assertions and APIs; 75. JSON-like config; 76. Object value extraction; 77. Object key extraction; 78. Bidirectional maps; 79. Single source of truth; 80. Avoid duplicated unions.

**81–90:** 81. Literal preservation in functions; 82. Generic inference; 83. Destructuring effects; 84. Contextual widening; 85. Function returns; 86. Array methods; 87. Tuple methods; 88. Spread effects; 89. Object spread; 90. Type inspection.

**91–100:** 91. Assertions risks; 92. `as const` misuse; 93. `satisfies` misuse; 94. Overly narrow types; 95. Overly broad types; 96. Domain modeling; 97. API contracts; 98. Static configuration validation; 99. Literal-first design; 100. Precision vs flexibility.

### Quiz — 40 preguntas

1. ¿Qué representa `"admin"` como tipo? 2. ¿Qué es una literal union? 3. ¿Qué hace `as const`? 4. ¿Cómo afecta objetos? 5. ¿Cómo afecta arrays? 6. ¿Qué diferencia existe entre `const` y `as const`? 7. ¿Qué hace `satisfies`? 8. ¿Widening desaparece con `satisfies`? 9. ¿Qué diferencia hay entre assertion y `satisfies`? 10. ¿Qué significa exact value type?

2. ¿Cómo crearías un tipo `"GET" | "POST"`? 12. ¿Cómo derivarías una union desde un array constante? 13. ¿Para qué sirve `typeof A[number]`? 14. ¿Qué hace `keyof typeof`? 15. ¿Cómo construirías un objeto enum-like? 16. ¿Qué es un closed set? 17. ¿Qué es un discriminant? 18. ¿Por qué evitar magic strings? 19. ¿Cómo mejora autocomplete? 20. ¿Qué es single source of truth?

3. ¿Qué ocurre con propiedades bajo `as const`? 22. ¿Pueden modificarse directamente? 23. ¿Qué ventaja tiene `satisfies` para configuración? 24. ¿Qué son excess properties? 25. ¿Por qué mantener inferencia? 26. ¿Cuándo un tipo es demasiado estrecho? 27. ¿Cuándo es demasiado amplio? 28. ¿Cómo representarías estados? 29. ¿Cómo representarías roles? 30. ¿Cómo representarías comandos?

4. ¿Cómo deriva TS literals dentro de tuples? 32. ¿Qué ocurre con spread? 33. ¿Qué significa literal preservation? 34. ¿Cómo relacionar valores y tipos? 35. ¿Por qué derivar tipos de constantes? 36. ¿Cuándo preferir union a string? 37. ¿Por qué no usar assertion para ocultar errores? 38. ¿Qué significa domain modeling? 39. ¿Qué ventaja tiene literal-first design? 40. Diseña conceptualmente una API basada en literals.

### Examen

Crea un router tipado con métodos `"GET" | "POST" | "PUT" | "DELETE"`, rutas constantes y configuraciones verificadas mediante `satisfies`.

### Proyecto

Construye **Configuration Type System**, donde todas las opciones válidas se deriven automáticamente de objetos constantes.

### Dominio

Debes poder derivar tipos desde valores sin duplicar manualmente información.

---

# MÓDULO 6 — `any`, `unknown`, `never`, `void`, `null` y `undefined`

### 100 temas

**Qué aprenderás:** dominarás los tipos especiales que controlan seguridad, ausencia de valores y estados imposibles.
**Por qué:** usarlos incorrectamente destruye buena parte de las garantías de TypeScript.
**Al finalizar:** podrás decidir con precisión cuándo corresponde cada uno.

**1–10:** 1. `any`; 2. Escape hatch; 3. Propagación de `any`; 4. Unsafety; 5. Implicit any; 6. Explicit any; 7. Migration scenarios; 8. Any contamination; 9. Detecting any; 10. Replacing any.

**11–20:** 11. `unknown`; 12. Unknown values; 13. Safe top type; 14. Narrow before use; 15. Unknown assignments; 16. Unknown parameters; 17. Unknown returns; 18. External data; 19. Catch variables; 20. JSON boundaries.

**21–30:** 21. `any` vs `unknown`; 22. Assignability to any; 23. Assignability from any; 24. Assignability to unknown; 25. Operations on unknown; 26. Narrowing unknown; 27. Assertions; 28. Guards; 29. Validation; 30. Boundary APIs.

**31–40:** 31. `never`; 32. Bottom type; 33. Impossible values; 34. Functions never returning; 35. Throw functions; 36. Infinite loops; 37. Exhaustiveness; 38. Unreachable branches; 39. Never unions; 40. Never intersections.

**41–50:** 41. `void`; 42. Function returns; 43. Ignored returns; 44. Callback void; 45. `undefined` vs void; 46. Assignability nuances; 47. Event handlers; 48. Side-effect functions; 49. Void variables; 50. API semantics.

**51–60:** 51. `undefined`; 52. Missing values; 53. Optional properties; 54. Optional parameters; 55. Explicit undefined; 56. `null`; 57. Explicit absence; 58. Nullable unions; 59. Null checking; 60. Optional chaining.

**61–70:** 61. Nullish coalescing; 62. Non-null assertion; 63. Definite assignment assertion; 64. Risks de `!`; 65. Control flow narrowing; 66. Guarding null; 67. Truthiness pitfalls; 68. Empty strings; 69. Zero values; 70. Boolean narrowing.

**71–80:** 71. `never` in conditional types; 72. Filtering unions; 73. Exhaustive switches; 74. `assertNever`; 75. Impossible state modeling; 76. Result models; 77. Error models; 78. Function contracts; 79. No-return APIs; 80. Bottom semantics.

**81–90:** 81. Top types; 82. `unknown` as top; 83. `{}` differences; 84. `object` differences; 85. `Object` differences; 86. Safe migration; 87. Type boundaries; 88. Validation boundaries; 89. Trust boundaries; 90. Defensive typing.

**91–100:** 91. `noImplicitAny`; 92. `useUnknownInCatchVariables`; 93. Strict null checks; 94. Linter interaction; 95. API hygiene; 96. Avoiding assertions; 97. Never as proof; 98. Void semantics; 99. Unknown-first design; 100. Special type mastery.

### Quiz

1. ¿Qué permite `any`? 2. ¿Por qué es peligroso? 3. ¿Qué es implicit any? 4. ¿Por qué `unknown` es más seguro? 5. ¿Puedes llamar métodos directamente sobre unknown? 6. ¿Cómo lo utilizas? 7. ¿Qué representa `never`? 8. ¿Qué representa `void`? 9. ¿`void` y undefined son idénticos? 10. ¿Qué cambia strictNullChecks?

2. ¿Qué es nullable union? 12. ¿Qué hace `?.`? 13. ¿Qué hace `??`? 14. ¿Qué hace `!` después de una expresión? 15. ¿Qué riesgo conlleva? 16. ¿Qué es definite assignment assertion? 17. ¿Qué significa bottom type? 18. ¿Qué significa top type? 19. ¿Por qué unknown actúa como top type? 20. ¿Cómo participa never en exhaustiveness?

3. ¿Qué es `assertNever`? 22. ¿Qué ocurre con `T | never`? 23. ¿Cómo modelas una función que siempre lanza? 24. ¿Cómo modelas un loop infinito? 25. ¿Qué tipo usarías para JSON sin validar? 26. ¿Por qué? 27. ¿Qué usarías al migrar JS temporalmente? 28. ¿Qué problema causa any contamination? 29. ¿Qué flag evita implicit any? 30. ¿Qué flag afecta catch?

4. ¿Qué diferencia existe entre missing y null? 32. ¿Cuándo usar undefined? 33. ¿Cuándo usar null? 34. ¿Qué es trust boundary? 35. ¿Por qué validar entradas externas? 36. ¿Los tipos existen en runtime? 37. ¿Qué es defensive typing? 38. ¿Por qué minimizar assertions? 39. ¿Qué tipo representa estado imposible? 40. Diseña una función exhaustiva conceptualmente.

### Examen

Implementa un parser de entradas `unknown` que valide cuatro estructuras posibles sin `any`, y utiliza `never` para garantizar exhaustividad.

### Proyecto

**Safe Boundary Library**: utilidades para convertir valores desconocidos en modelos confiables mediante guards y assertions.

### Dominio

Ningún `any` salvo justificación explícita; uso correcto de `unknown` y `never`.

---

# MÓDULO 7 — Object Types

### 100 temas

**Qué aprenderás:** modelar objetos completos. **Por qué:** la mayoría de datos de aplicaciones reales son estructuras. **Resultado:** crearás contratos estructurales precisos.

**1–10:** 1. Object literals; 2. Property types; 3. Method types; 4. Required properties; 5. Optional properties; 6. `readonly`; 7. Nested objects; 8. Anonymous object types; 9. Named object types; 10. Structural compatibility.

**11–20:** 11. Excess property checking; 12. Fresh objects; 13. Variable assignment; 14. Property access; 15. Bracket access; 16. Dynamic access; 17. Index signatures intro; 18. String indexes; 19. Number indexes; 20. Symbol indexes.

**21–30:** 21. Readonly semantics; 22. Shallow readonly; 23. Nested mutation; 24. Optional vs undefined; 25. Exact optional behavior; 26. `exactOptionalPropertyTypes`; 27. Object intersections; 28. Object unions; 29. Common properties; 30. Object narrowing.

**31–40:** 31. Method syntax; 32. Function properties; 33. `this` contextual type; 34. Getters conceptual; 35. Setters conceptual; 36. Object spread; 37. Object rest; 38. Destructuring; 39. Typed destructuring; 40. Parameter destructuring.

**41–50:** 41. Return objects; 42. Factory functions; 43. Configuration objects; 44. Options pattern; 45. Deep models; 46. Recursive objects preview; 47. Dictionaries; 48. Records; 49. Lookup tables; 50. Heterogeneous objects.

**51–60:** 51. Property key types; 52. `PropertyKey`; 53. Numeric keys; 54. Runtime coercion; 55. Computed properties; 56. Symbols as keys; 57. Unique symbol preview; 58. Key constraints; 59. Property iteration; 60. Typed lookup.

**61–70:** 61. Object assignability; 62. Width subtyping concept; 63. Missing properties; 64. Additional properties; 65. Optional compatibility; 66. Readonly compatibility; 67. Structural contracts; 68. Nominal contrast; 69. Data transfer objects; 70. Domain entities.

**71–80:** 71. Immutable models; 72. Mutable models; 73. Input/output models; 74. Partial update modeling; 75. Object composition; 76. Composition vs inheritance; 77. Flattening models; 78. Nested IDs; 79. Metadata models; 80. Generic containers preview.

**81–90:** 81. Object type aliases; 82. Interfaces preview; 83. Inline vs reusable; 84. Documentation; 85. Naming conventions; 86. API surface; 87. Object precision; 88. Over-modeling; 89. Under-modeling; 90. Type readability.

**91–100:** 91. Excess property debugging; 92. Optional bugs; 93. Readonly misuse; 94. Unsafe index access; 95. `noUncheckedIndexedAccess`; 96. Validation boundaries; 97. Object type design; 98. Domain invariants; 99. Refactoring object types; 100. Professional modeling.

### Quiz

1. ¿Qué es structural compatibility? 2. ¿Qué significa required property? 3. ¿Qué significa optional? 4. ¿Qué hace readonly? 5. ¿Es deep readonly? 6. ¿Qué es excess property checking? 7. ¿Cuándo ocurre? 8. ¿Qué es index signature? 9. ¿Qué diferencia hay entre dot y bracket access? 10. ¿Qué es object spread?

2. ¿Qué es object rest? 12. ¿Cómo se tipa destructuring? 13. ¿Optional significa exactamente `T | undefined` en todos los contextos? 14. ¿Qué controla exactOptionalPropertyTypes? 15. ¿Qué representa PropertyKey? 16. ¿Qué claves permite JS? 17. ¿Qué es computed property? 18. ¿Qué es lookup table? 19. ¿Qué es dictionary? 20. ¿Qué diferencia hay con Record?

3. ¿Qué significa width subtyping? 22. ¿Qué es factory function? 23. ¿Qué es options pattern? 24. ¿Qué representa DTO? 25. ¿Qué es una domain entity? 26. ¿Cuándo usar readonly? 27. ¿Qué problema evita noUncheckedIndexedAccess? 28. ¿Qué es unsafe lookup? 29. ¿Por qué separar input/output? 30. ¿Qué significa composición?

4. ¿Qué problema presenta over-modeling? 32. ¿Y under-modeling? 33. ¿Qué propiedades comparten objetos en una union? 34. ¿Por qué narrowing? 35. ¿Qué ocurre al intersectar objetos? 36. ¿Cómo modelar metadata? 37. ¿Cuándo extraer un tipo nombrado? 38. ¿Qué ventaja aporta legibilidad? 39. ¿Qué es domain invariant? 40. Diseña un modelo de usuario complejo.

### Examen

Modela un sistema de comercio con `Customer`, `Address`, `Order`, `OrderItem`, `Product`, configuraciones opcionales y propiedades readonly.

### Proyecto

**Domain Modeling Laboratory** con al menos 15 estructuras relacionadas y cero `any`.

### Dominio

Ser capaz de convertir requisitos narrativos en contratos estructurales correctos.

---

# MÓDULO 8 — Arrays, readonly arrays y tuples

### 100 temas

**1–10:** 1. `T[]`; 2. `Array<T>`; 3. Array inference; 4. Element types; 5. Mixed arrays; 6. Union arrays; 7. Nested arrays; 8. Multidimensional arrays; 9. Empty array inference; 10. Contextual arrays.

**11–20:** 11. `ReadonlyArray<T>`; 12. `readonly T[]`; 13. Mutation prevention; 14. `push`; 15. `pop`; 16. `splice`; 17. Non-mutating methods; 18. Array copying; 19. Spread arrays; 20. Immutable workflows.

**21–30:** 21. Tuples; 22. Fixed positions; 23. Fixed types; 24. Tuple access; 25. Tuple destructuring; 26. Optional tuple elements; 27. Rest elements; 28. Labeled tuples; 29. Readonly tuples; 30. Tuple assignability.

**31–40:** 31. Tuple inference; 32. `as const`; 33. Variadic tuples intro; 34. Tuple concatenation; 35. Function arguments as tuples; 36. Parameter lists; 37. Return tuples; 38. Multiple values; 39. Tuple vs object; 40. Semantic labels.

**41–50:** 41. `map`; 42. Callback inference; 43. `filter`; 44. Predicate behavior; 45. `reduce`; 46. Accumulator typing; 47. `find`; 48. `findIndex`; 49. `some`; 50. `every`.

**51–60:** 51. `flat`; 52. `flatMap`; 53. `slice`; 54. `concat`; 55. `sort`; 56. Mutability of sort; 57. `reverse`; 58. Mutation concerns; 59. Iteration; 60. `for...of`.

**61–70:** 61. Indexed access; 62. Possible undefined; 63. `noUncheckedIndexedAccess`; 64. Bounds awareness; 65. Array unions; 66. Union of arrays; 67. Element union; 68. Type extraction; 69. `T[number]`; 70. Tuple element extraction.

**71–80:** 71. Head type concept; 72. Tail type concept; 73. Recursive tuple preview; 74. Tuple length literals; 75. Empty tuple; 76. Non-empty arrays; 77. `[T, ...T[]]`; 78. Pair modeling; 79. Triple modeling; 80. Coordinate modeling.

**81–90:** 81. Readonly covariance considerations; 82. Mutable variance concerns; 83. Passing arrays; 84. Defensive copies; 85. API inputs; 86. API outputs; 87. Immutable APIs; 88. Array-like interfaces; 89. Iterable intro; 90. Iterator relation.

**91–100:** 91. Large collection types; 92. Data transformations; 93. Pipelines; 94. Type preservation; 95. Type widening; 96. `satisfies` arrays; 97. Constant datasets; 98. Collection modeling; 99. Performance vs typing; 100. Array/tuple mastery.

### Quiz

1. Diferencia entre `T[]` y `Array<T>`. 2. ¿Qué es ReadonlyArray? 3. ¿Se puede usar push? 4. ¿Qué es tuple? 5. ¿En qué difiere de array? 6. ¿Qué es labeled tuple? 7. ¿Qué es optional tuple element? 8. ¿Qué es rest tuple element? 9. ¿Qué hace `as const` sobre arrays? 10. ¿Cómo extraes el elemento de `T[]`?

2. ¿Qué significa `T[number]`? 12. ¿Qué hace map? 13. ¿Cómo infiere callbacks? 14. ¿Qué hace filter? 15. ¿Qué es predicate? 16. ¿Qué dificultad tiene reduce? 17. ¿Qué hace noUncheckedIndexedAccess? 18. ¿Por qué array[index] puede ser undefined? 19. ¿Qué es non-empty array? 20. ¿Cómo lo modelarías?

3. ¿Qué métodos mutan? 22. ¿Sort muta? 23. ¿Reverse muta? 24. ¿Qué significa immutable workflow? 25. ¿Qué es defensive copy? 26. ¿Cuándo preferir tuple? 27. ¿Cuándo preferir object? 28. ¿Cómo modelas coordenadas? 29. ¿Cómo modelas función con rest tuple? 30. ¿Qué es tuple length literal?

4. ¿Qué es variadic tuple? 32. ¿Qué significa head/tail? 33. ¿Qué es union array? 34. ¿Qué es array of union? 35. ¿Son siempre equivalentes? 36. ¿Qué es contextual array inference? 37. ¿Qué ocurre con arrays vacíos? 38. ¿Cómo preservas literals? 39. ¿Por qué usar readonly como entrada? 40. Diseña un pipeline tipado de colección.

### Examen

Implementa un módulo de estadísticas que acepte readonly arrays y utilice tuples para resultados múltiples.

### Proyecto

**Typed Collection Toolkit**.

### Dominio

Dominar arrays mutables, inmutables y tuples sin assertions innecesarias.

---

# MÓDULO 9 — Type Aliases e Interfaces

### 100 temas

**1–10:** 1. Type aliases; 2. Interface declarations; 3. Object contracts; 4. Primitive aliases; 5. Union aliases; 6. Tuple aliases; 7. Function aliases; 8. Generic aliases intro; 9. Naming; 10. Reusability.

**11–20:** 11. Interface properties; 12. Optional properties; 13. Readonly properties; 14. Methods; 15. Function properties; 16. Index signatures; 17. Interface extension; 18. Multiple extension; 19. Recursive interfaces; 20. Self references.

**21–30:** 21. Type intersections; 22. Type composition; 23. Interface inheritance; 24. Alias composition; 25. Alias recursion; 26. Interface recursion; 27. Structural typing; 28. Declaration merging; 29. Open interfaces; 30. Closed aliases concept.

**31–40:** 31. Interface reopening; 32. Global augmentation preview; 33. Module augmentation preview; 34. Library declarations; 35. API extension; 36. Accidental merging; 37. Naming collisions; 38. Extensibility; 39. Library author considerations; 40. Application considerations.

**41–50:** 41. `extends` compatibility; 42. Conflicting properties; 43. Intersection conflicts; 44. `never` properties; 45. Override-like declarations; 46. Optional conflicts; 47. Readonly differences; 48. Method variance nuance; 49. Function-property variance; 50. Structural design.

**51–60:** 51. Interfaces for classes; 52. `implements`; 53. Instance contracts; 54. Static side distinction; 55. Constructor interfaces intro; 56. Callable interfaces; 57. Hybrid interfaces; 58. Generic interfaces; 59. Multiple type parameters; 60. Constraints preview.

**61–70:** 61. API DTO aliases; 62. Domain interfaces; 63. Public contracts; 64. Internal implementation; 65. Type naming conventions; 66. Prefix anti-patterns; 67. Semantic naming; 68. Exported types; 69. Internal types; 70. Documentation.

**71–80:** 71. IntelliSense display; 72. Error readability; 73. Alias expansion; 74. Interface display; 75. Complex intersections; 76. Refactoring; 77. Public stability; 78. Declaration emit; 79. Library API ergonomics; 80. Consumer experience.

**81–90:** 81. Interface vs alias decision; 82. Unions require aliases; 83. Mapped types and aliases; 84. Conditional aliases; 85. Interface strengths; 86. Alias strengths; 87. No universal winner; 88. Team conventions; 89. Consistency; 90. Codebase evolution.

**91–100:** 91. Composition patterns; 92. Small interfaces; 93. Segregation; 94. Monolithic interfaces; 95. Intersection overuse; 96. Inheritance overuse; 97. Domain modeling; 98. Library modeling; 99. Refactoring strategies; 100. Mastery comparison.

### Quiz

1. ¿Qué es type alias? 2. ¿Qué es interface? 3. ¿Ambos pueden modelar objetos? 4. ¿Un interface modela directamente union? 5. ¿Un alias puede? 6. ¿Qué es declaration merging? 7. ¿Qué estructura lo soporta? 8. ¿Qué significa interface abierta? 9. ¿Qué hace extends? 10. ¿Qué hace intersection?

2. ¿Qué diferencia hay entre inheritance e intersection? 12. ¿Qué pasa con propiedades incompatibles? 13. ¿Qué es callable interface? 14. ¿Qué es generic interface? 15. ¿Puede una clase implements un interface? 16. ¿Qué lado verifica? 17. ¿Qué es static side? 18. ¿Qué es recursive interface? 19. ¿Puede un alias ser recursivo? 20. ¿Cuándo usar alias obligatoriamente?

3. ¿Qué ventaja tienen interfaces para augmentation? 22. ¿Qué riesgo tiene merging accidental? 23. ¿Por qué importan nombres? 24. ¿Qué es public contract? 25. ¿Qué es internal type? 26. ¿Qué afecta declaration emit? 27. ¿Qué es interface segregation? 28. ¿Por qué evitar interfaces gigantes? 29. ¿Cuándo composición? 30. ¿Cuándo herencia?

4. ¿Existe siempre una opción superior? 32. ¿Por qué no? 33. ¿Qué son team conventions? 34. ¿Cómo afecta error readability? 35. ¿Qué es alias expansion? 36. ¿Puede alias representar tuple? 37. ¿Puede alias representar primitive? 38. ¿Qué usarías para union? 39. ¿Qué usarías para API extensible? 40. Justifica una decisión interface/type.

### Examen

Diseña 20 contratos de un sistema empresarial usando deliberadamente interfaces o aliases y justifica cada elección.

### Proyecto

**Contract Design System**.

### Dominio

Debes escoger entre `interface` y `type` por razones técnicas, no por dogma.

---

# MÓDULO 10 — Union e Intersection Types

### 100 temas

**1–10:** 1. Union syntax; 2. Value sets; 3. Assignability; 4. Shared operations; 5. Union properties; 6. Union methods; 7. Narrowing requirement; 8. String unions; 9. Numeric unions; 10. Object unions.

**11–20:** 11. Nullable unions; 12. Undefined unions; 13. Function unions; 14. Array unions; 15. Tuple unions; 16. Literal unions; 17. Broad unions; 18. Nested unions; 19. Flattening unions; 20. Duplicate elimination.

**21–30:** 21. Intersection syntax; 22. Combining contracts; 23. Object intersections; 24. Primitive intersections; 25. Impossible intersections; 26. `never`; 27. Property conflicts; 28. Compatible properties; 29. Function intersections; 30. Callable overload-like behavior.

**31–40:** 31. Distribution concept; 32. Union algebra; 33. Intersection algebra; 34. Set-theoretic intuition; 35. Top/bottom relationships; 36. `unknown` intersections; 37. `unknown` unions; 38. `never` unions; 39. `never` intersections; 40. `any` complications.

**41–50:** 41. Discriminated unions intro; 42. Tags; 43. States; 44. Events; 45. Results; 46. Success/failure models; 47. Loading states; 48. Commands; 49. Messages; 50. AST nodes.

**51–60:** 51. Common field access; 52. Narrowed access; 53. Exhaustive switch; 54. Control flow; 55. `in`; 56. `typeof`; 57. `instanceof`; 58. User guards preview; 59. Equality narrowing; 60. Truthiness narrowing.

**61–70:** 61. Intersection composition; 62. Mix-and-match features; 63. Base model intersections; 64. Metadata intersections; 65. Audit fields; 66. Identifier mixins; 67. Timestamp models; 68. Avoiding inheritance; 69. Structural composition; 70. Composition risks.

**71–80:** 71. Union explosion; 72. Complex error messages; 73. Normalize models; 74. Refactoring unions; 75. Naming unions; 76. Nested discriminants; 77. Hierarchical states; 78. State transitions; 79. Illegal state prevention; 80. Domain representation.

**81–90:** 81. Exclusive-or conceptual; 82. Mutually exclusive properties; 83. `never` fields; 84. XOR patterns; 85. At-least-one patterns preview; 86. Exactly-one patterns preview; 87. Optional union pitfalls; 88. Excess properties; 89. Structural overlap; 90. Ambiguous members.

**91–100:** 91. API response unions; 92. Error unions; 93. Event unions; 94. Reducer actions; 95. Parser results; 96. Validation results; 97. Command handlers; 98. Domain events; 99. Scalable union design; 100. Union/intersection mastery.

### Quiz

1. ¿Qué significa `A | B`? 2. ¿Qué operaciones puedes hacer antes de narrowing? 3. ¿Qué significa `A & B`? 4. ¿Qué ocurre con propiedades incompatibles? 5. ¿Qué relación tiene never? 6. ¿Qué es literal union? 7. ¿Qué es object union? 8. ¿Qué es discriminant? 9. ¿Qué es discriminated union? 10. ¿Qué es exhaustive switch?

2. ¿Qué representa union como conjunto? 12. ¿Y intersection? 13. ¿Qué ocurre con `T | never`? 14. ¿Qué ocurre con `T & unknown`? 15. ¿Qué ocurre con `T | unknown`? 16. ¿Por qué any complica razonamiento? 17. ¿Qué es structural overlap? 18. ¿Qué es ambiguous member? 19. ¿Qué significa illegal state? 20. ¿Cómo evitarlo?

3. ¿Qué es XOR? 22. ¿Cómo puede never ayudar? 23. ¿Qué es state union? 24. ¿Qué es event union? 25. ¿Qué es result union? 26. ¿Qué ventaja tiene frente a booleans independientes? 27. ¿Qué es union explosion? 28. ¿Cómo reducirla? 29. ¿Qué significa flattening unions? 30. ¿TS elimina duplicados conceptualmente?

4. ¿Qué narrowing admite union? 32. ¿Qué hace `in`? 33. ¿Qué hace typeof? 34. ¿Qué hace instanceof? 35. ¿Qué es equality narrowing? 36. ¿Por qué modelar responses como unions? 37. ¿Cómo representar errores? 38. ¿Qué es scalable union design? 39. ¿Cuándo preferir intersection? 40. Diseña un workflow con estados.

### Examen

Construye una máquina de estados para pedidos usando unions discriminadas y exhaustiveness.

### Proyecto

**Order State Engine**.

### Dominio

Ningún estado inválido debe poder representarse mediante los tipos.

---

# PARTE II — FUNCIONES, NARROWING Y CONTRATOS

# MÓDULO 11 — Funciones Type-Safe

### 100 temas

**1–10:** 1. Function declarations; 2. Function expressions; 3. Arrow functions; 4. Parameter annotations; 5. Return annotations; 6. Return inference; 7. `void`; 8. `never`; 9. Optional parameters; 10. Default parameters.

**11–20:** 11. Rest parameters; 12. Rest tuples; 13. Destructured parameters; 14. Object parameters; 15. Tuple parameters; 16. Callback parameters; 17. Contextual typing; 18. Higher-order functions; 19. Function values; 20. Function variables.

**21–30:** 21. Function type expressions; 22. Named aliases; 23. Callable interfaces; 24. Call signatures; 25. Construct signatures; 26. Hybrid callables; 27. Properties on functions; 28. Generic functions intro; 29. Callback return types; 30. Side-effect callbacks.

**31–40:** 31. Optional callback parameters; 32. Parameter variance intro; 33. Strict function types; 34. Function assignability; 35. Fewer parameters; 36. Extra parameters; 37. Return assignability; 38. Void callbacks; 39. Method differences; 40. Soundness tradeoffs.

**41–50:** 41. `this` parameters; 42. Explicit `this`; 43. Arrow `this`; 44. Contextual this; 45. `this: void`; 46. Callback this; 47. Method extraction; 48. Lost this; 49. Bind conceptual; 50. Call/apply conceptual.

**51–60:** 51. Overloads intro; 52. Overload signatures; 53. Implementation signature; 54. Signature visibility; 55. Overload ordering; 56. Union alternative; 57. Generic alternative; 58. Overload implementation; 59. Return correlations; 60. API ergonomics.

**61–70:** 61. Function parameter objects; 62. Options objects; 63. Named parameters pattern; 64. Long argument lists; 65. Defaults; 66. Optional options; 67. Readonly inputs; 68. Immutable function design; 69. Pure functions; 70. Impure functions.

**71–80:** 71. Function composition; 72. Pipe concept; 73. Currying concept; 74. Partial application; 75. Closures typing; 76. Factory functions; 77. Function factories; 78. Predicate functions; 79. Assertion functions preview; 80. Guards preview.

**81–90:** 81. Async function types; 82. `Promise<T>`; 83. Async return inference; 84. Promise callbacks; 85. Error typing limitations; 86. Generator preview; 87. Iterator return types; 88. Callable objects; 89. Constructors; 90. Abstract constructors preview.

**91–100:** 91. Public API signatures; 92. Implementation hiding; 93. Signature readability; 94. Parameter naming; 95. Generic naming; 96. Error messages; 97. Function refactoring; 98. Minimizing overloads; 99. Type-driven function design; 100. Function mastery.

### Quiz

1. ¿Cómo anotas un parámetro? 2. ¿Cómo anotas retorno? 3. ¿Cuándo inferir retorno? 4. ¿Qué es optional parameter? 5. ¿Qué es default parameter? 6. ¿Qué es rest parameter? 7. ¿Qué es function type expression? 8. ¿Qué es call signature? 9. ¿Qué es construct signature? 10. ¿Qué es higher-order function?

2. ¿Qué es contextual typing? 12. ¿Qué es function assignability? 13. ¿Qué implica strictFunctionTypes? 14. ¿Qué representa void callback? 15. ¿Qué es explicit this parameter? 16. ¿Existe en runtime? 17. ¿Qué problema soluciona `this: void`? 18. ¿Qué es overload? 19. ¿Qué es implementation signature? 20. ¿Es visible externamente?

3. ¿Cuándo union puede sustituir overloads? 22. ¿Cuándo generic? 23. ¿Qué es options object? 24. ¿Por qué evitar muchos parámetros? 25. ¿Qué significa pure function? 26. ¿Qué significa closure? 27. ¿Qué es factory function? 28. ¿Qué es predicate? 29. ¿Cómo se tipa async function? 30. ¿Qué devuelve realmente?

4. ¿Qué es Promise<T>? 32. ¿Qué son callable objects? 33. ¿Qué es constructor type? 34. ¿Por qué tipar APIs públicas? 35. ¿Qué es return correlation? 36. ¿Qué problema generan overloads excesivos? 37. ¿Qué significa immutable input? 38. ¿Qué es partial application? 39. ¿Qué es currying? 40. Diseña una función type-safe extensible.

### Examen

Crea una biblioteca de funciones de colecciones con callbacks, rest tuples, overloads y funciones de orden superior.

### Proyecto

**Typed Functional Toolkit**.

### Dominio

Diseñar funciones públicas sin `any` y con inferencia útil para el consumidor.

---

# MÓDULO 12 — Sobrecargas, callable types y firmas avanzadas

### 100 temas

**1–10:** 1. Overload signatures; 2. Implementation signatures; 3. Signature compatibility; 4. Overload resolution; 5. Ordering; 6. Specific signatures; 7. General signatures; 8. Return overloads; 9. Parameter overloads; 10. Arity overloads.

**11–20:** 11. Union vs overload; 12. Generic vs overload; 13. Conditional return preview; 14. Literal overloads; 15. Correlated arguments; 16. Correlated returns; 17. Overload errors; 18. Implementation narrowing; 19. Unknown implementation params; 20. Safe dispatch.

**21–30:** 21. Call signatures; 22. Properties on callable values; 23. Function-object pattern; 24. Callable interface; 25. Callable type alias; 26. Generic call signature; 27. Overloaded interface; 28. Multiple call signatures; 29. Documentation; 30. IntelliSense overload display.

**31–40:** 31. Construct signatures; 32. `new` signatures; 33. Instance extraction; 34. Constructor parameters; 35. Abstract construct signatures; 36. Class factories; 37. Dependency creation; 38. Generic constructors; 39. Static members; 40. Instance members.

**41–50:** 41. Hybrid callable/constructable; 42. Function namespace patterns; 43. Static properties on functions; 44. Fluent functions; 45. Chainable callable APIs; 46. State carried by function; 47. Type intersections for callables; 48. Object-callable composition; 49. Library patterns; 50. API ergonomics.

**51–60:** 51. Variadic functions; 52. Tuple arguments; 53. Labeled tuple parameters; 54. Optional rest tuples; 55. Generic rest tuples; 56. Preserving arguments; 57. Wrapper functions; 58. Forwarding functions; 59. `Parameters<T>` preview; 60. `ReturnType<T>` preview.

**61–70:** 61. Decorator-style wrappers conceptual; 62. Logging wrappers; 63. Memoization typing; 64. Timing wrappers; 65. Retry wrappers; 66. Callback wrapping; 67. Preserve `this`; 68. Preserve return; 69. Preserve overloads limitations; 70. Generic inference challenges.

**71–80:** 71. Bivariance concept; 72. Contravariance intro; 73. Covariance intro; 74. Parameter safety; 75. Method exception nuance; 76. Callback APIs; 77. Event handlers; 78. Listener signatures; 79. Handler maps; 80. Typed event emitters.

**81–90:** 81. API overload scalability; 82. Combinatorial explosion; 83. Generic compression; 84. Conditional types preview; 85. Tuple mapping preview; 86. API readability; 87. Error readability; 88. Consumer inference; 89. Implementation complexity; 90. Maintenance cost.

**91–100:** 91. Designing overload sets; 92. Testing overloads; 93. Negative type tests; 94. Expected errors; 95. Public API evolution; 96. Backwards compatibility; 97. Signature deprecation; 98. Migration paths; 99. Advanced callable design; 100. Mastery.

### Quiz

1. ¿Qué es overload signature? 2. ¿Qué es implementation signature? 3. ¿Qué ve el consumidor? 4. ¿Cómo se resuelve overload? 5. ¿Por qué importa orden? 6. ¿Cuándo usar union? 7. ¿Cuándo generic? 8. ¿Qué son correlated arguments? 9. ¿Qué son correlated returns? 10. ¿Por qué unknown puede ser útil internamente?

2. ¿Qué es call signature? 12. ¿Puede una función tener propiedades? 13. ¿Qué es construct signature? 14. ¿Qué diferencia hay entre static e instance side? 15. ¿Qué es generic constructor? 16. ¿Qué es abstract construct signature? 17. ¿Qué es hybrid callable? 18. ¿Cómo representas rest arguments? 19. ¿Qué aporta tuple? 20. ¿Qué es argument forwarding?

3. ¿Qué debe preservar un wrapper? 22. ¿Qué problema hay con this? 23. ¿Qué es covariance? 24. ¿Qué es contravariance? 25. ¿Qué es bivariance? 26. ¿Qué flag influye? 27. ¿Por qué event handlers requieren cuidado? 28. ¿Qué es handler map? 29. ¿Qué es typed emitter? 30. ¿Qué es overload explosion?

4. ¿Cómo reducir overloads? 32. ¿Qué es API evolution? 33. ¿Cómo deprecar una firma? 34. ¿Qué son negative type tests? 35. ¿Por qué probar errores esperados? 36. ¿Qué es API ergonomics? 37. ¿Qué es consumer inference? 38. ¿Cuándo overload empeora mantenimiento? 39. ¿Cómo modelar factory constructor? 40. Diseña una API callable.

### Examen

Construye un API de consulta que pueda invocarse como función y posea métodos y propiedades, usando call signatures y overloads.

### Proyecto

**Callable Query API**.

### Dominio

Crear APIs invocables complejas manteniendo buenas inferencias.

---

# MÓDULO 13 — Narrowing y Control Flow Analysis

### 100 temas

**1–10:** 1. Narrowing; 2. Broad types; 3. Refined types; 4. Control flow analysis; 5. Reachability; 6. Assignment analysis; 7. Branch analysis; 8. Return analysis; 9. Re-merge; 10. Declared vs observed type.

**11–20:** 11. `typeof`; 12. String narrowing; 13. Number narrowing; 14. Boolean narrowing; 15. Bigint narrowing; 16. Symbol narrowing; 17. Undefined narrowing; 18. Object caveats; 19. Function detection; 20. Null quirk.

**21–30:** 21. Truthiness narrowing; 22. Falsy values; 23. Empty string problem; 24. Zero problem; 25. Null checks; 26. Boolean conversion; 27. Double negation; 28. Explicit checks; 29. Defensive branches; 30. Narrowing precision.

**31–40:** 31. Equality narrowing; 32. `===`; 33. `!==`; 34. Loose equality nuances; 35. Null equality pattern; 36. Comparing union members; 37. Shared compatible types; 38. Literal comparisons; 39. Switch narrowing; 40. Case branches.

**41–50:** 41. `in` operator; 42. Property presence; 43. Optional property caveat; 44. Structural overlap; 45. `instanceof`; 46. Constructor prototypes; 47. Built-in classes; 48. Custom classes; 49. Cross-realm caveats concept; 50. Class narrowing.

**51–60:** 51. Assignment narrowing; 52. Variable reassignments; 53. Declared union; 54. Observed member; 55. Callback boundaries; 56. Mutation concerns; 57. Closure analysis; 58. Aliased conditions; 59. Boolean aliases; 60. CFA improvements.

**61–70:** 61. Discriminated unions; 62. Discriminant property; 63. Literal tags; 64. Switch exhaustiveness; 65. State objects; 66. Event objects; 67. Result objects; 68. AST nodes; 69. Messages; 70. Commands.

**71–80:** 71. Predicate preview; 72. Assertion functions preview; 73. Guard composition; 74. Array filter narrowing; 75. Find narrowing; 76. Every narrowing; 77. Narrowing generics limitations; 78. Indexed access; 79. Object property narrowing; 80. Nested property narrowing.

**81–90:** 81. Destructuring narrowing; 82. Correlated destructuring; 83. Parameter narrowing; 84. Return early pattern; 85. Guard clauses; 86. Exhaustive failure; 87. Impossible branches; 88. Never detection; 89. Dead code; 90. Refactoring control flow.

**91–100:** 91. Narrowing lost by mutation; 92. Narrowing across functions; 93. Aliasing hazards; 94. Runtime checks; 95. Static interpretation; 96. Guard design; 97. Debugging narrowing; 98. Inspect inferred branches; 99. Domain state refinement; 100. CFA mastery.

### Quiz

1. ¿Qué es narrowing? 2. ¿Qué es CFA? 3. ¿Qué hace typeof? 4. ¿Por qué `typeof null` es especial? 5. ¿Qué es truthiness narrowing? 6. ¿Qué riesgo tiene empty string? 7. ¿Qué riesgo tiene 0? 8. ¿Qué es equality narrowing? 9. ¿Qué hace `in`? 10. ¿Qué hace instanceof?

2. ¿Qué es assignment narrowing? 12. ¿Qué diferencia hay entre declared y observed type? 13. ¿Qué es discriminant? 14. ¿Qué es switch narrowing? 15. ¿Qué significa reachability? 16. ¿Cómo influye return temprano? 17. ¿Qué es guard clause? 18. ¿Qué representa never al final? 19. ¿Qué es structural overlap? 20. ¿Por qué optional property complica `in`?

3. ¿Puede una mutación invalidar narrowing? 22. ¿Por qué callbacks complican análisis? 23. ¿Qué es aliased condition? 24. ¿Qué es literal comparison? 25. ¿Cómo filtrar unions? 26. ¿Qué es nested narrowing? 27. ¿Cómo narrowing mejora seguridad? 28. ¿Los checks ocurren runtime? 29. ¿TypeScript interpreta esos checks? 30. ¿Qué diferencia existe?

4. ¿Cómo modelar estado con discriminated union? 32. ¿Qué es exhaustive failure? 33. ¿Por qué no usar assertions para saltarlo? 34. ¿Qué significa impossible branch? 35. ¿Qué es dead code? 36. ¿Cómo inspeccionar tipo dentro de branch? 37. ¿Qué es property narrowing? 38. ¿Qué es parameter narrowing? 39. ¿Qué significa refinement? 40. Diseña un flujo con cinco estados.

### Examen

Implementa un procesador de diez variantes de mensajes que no utilice assertions y sea exhaustivo.

### Proyecto

**Control Flow Analyzer Playground**.

### Dominio

Ser capaz de anticipar qué tipo inferirá TS en cada rama.

---

# MÓDULO 14 — Type Guards y Assertion Functions

### 100 temas

**1–10:** 1. User-defined guards; 2. Type predicates; 3. `value is T`; 4. Guard parameters; 5. Boolean implementation; 6. Runtime checks; 7. Safe predicates; 8. Unsound predicates; 9. Guard contracts; 10. Guard naming.

**11–20:** 11. Primitive guards; 12. Object guards; 13. Array guards; 14. Tuple guards; 15. Property guards; 16. Nested object guards; 17. Class guards; 18. Literal guards; 19. Union guards; 20. Generic guards.

**21–30:** 21. `Array.isArray`; 22. `typeof`; 23. `instanceof`; 24. `in`; 25. Equality; 26. Null guards; 27. Undefined guards; 28. Non-null guards; 29. Falsy guards; 30. Branded guard preview.

**31–40:** 31. Assertion functions; 32. `asserts condition`; 33. `asserts value is T`; 34. Throwing failures; 35. Runtime invariants; 36. Development assertions; 37. API preconditions; 38. Postconditions concept; 39. Internal invariants; 40. Exhaustiveness assertions.

**41–50:** 41. Guard composition; 42. AND guards; 43. OR guards; 44. Negated guards; 45. Higher-order guards; 46. Array-of guards; 47. Record guards; 48. Optional guard; 49. Nullable guard; 50. Union guard combinators.

**51–60:** 51. Generic predicates; 52. Generic limitations; 53. Schema-like guards; 54. Recursive guards; 55. Circular values caveat; 56. Deep validation; 57. Shallow validation; 58. Error reporting; 59. Boolean vs result; 60. Validation API design.

**61–70:** 61. Guard in `filter`; 62. Guard in `find`; 63. Guard in conditionals; 64. Guard in switches; 65. Guard as callback; 66. Predicate inference considerations; 67. Reusable guards; 68. Guard libraries conceptual; 69. External input; 70. JSON validation.

**71–80:** 71. API responses; 72. LocalStorage-like input; 73. Environment values concept; 74. Message parsing; 75. Event parsing; 76. File data conceptual; 77. Trust boundaries; 78. Untrusted input; 79. Defensive decoding; 80. Parse, don't cast.

**81–90:** 81. Assertions vs guards; 82. Assertions vs type assertions; 83. Runtime guarantees; 84. Static lies; 85. `as` hazards; 86. Guard hazards; 87. Incomplete validation; 88. Property existence vs property type; 89. Prototype concerns; 90. Error diagnostics.

**91–100:** 91. Guard test cases; 92. Negative tests; 93. Edge cases; 94. Mutation after guard; 95. Validation caching; 96. Performance considerations; 97. API ergonomics; 98. Sound guard design; 99. Boundary architecture; 100. Guard mastery.

### Quiz

1. ¿Qué es type predicate? 2. ¿Qué significa `x is T`? 3. ¿El compilador verifica completamente que el guard sea verdadero? 4. ¿Qué riesgo implica? 5. ¿Qué es assertion function? 6. ¿Qué significa asserts condition? 7. ¿Qué significa asserts x is T? 8. ¿Debe lanzar si falla? 9. ¿Qué diferencia hay con `as T`? 10. ¿Cuál ofrece runtime checking?

2. ¿Qué es guard composition? 12. ¿Cómo validar array? 13. ¿Cómo validar objeto? 14. ¿Por qué comprobar propiedad no basta? 15. ¿Qué es recursive guard? 16. ¿Qué es deep validation? 17. ¿Qué es shallow validation? 18. ¿Qué significa parse, don't cast? 19. ¿Qué es trust boundary? 20. ¿Qué tipo debe recibir un parser externo?

3. ¿Por qué unknown? 22. ¿Cómo filtrar array mediante guard? 23. ¿Cómo usar guard en find? 24. ¿Qué es higher-order guard? 25. ¿Qué es nullable guard? 26. ¿Qué es array-of guard? 27. ¿Qué problema tiene circular data? 28. ¿Qué es runtime invariant? 29. ¿Qué es precondition? 30. ¿Qué es exhaustive assertion?

4. ¿Cómo probar guards? 32. ¿Qué son negative cases? 33. ¿Por qué mutation puede invalidar garantías? 34. ¿Qué diferencia hay entre predicate y validator con errores? 35. ¿Cuándo usar boolean? 36. ¿Cuándo devolver resultado detallado? 37. ¿Qué es unsound guard? 38. ¿Cómo evitarlo? 39. ¿Por qué assertions deben minimizarse? 40. Diseña un decoder para usuario.

### Examen

Construye un validador manual de un objeto `Order` profundamente anidado recibido como `unknown`.

### Proyecto

**Runtime Type Guards Toolkit**.

### Dominio

Convertir datos desconocidos en tipos seguros sin `any` ni casts ciegos.

---

# MÓDULO 15 — Enums, Symbols y constantes tipadas

### 100 temas

**1–10:** 1. Enum syntax; 2. Numeric enums; 3. String enums; 4. Heterogeneous enums; 5. Auto numbering; 6. Explicit values; 7. Computed members; 8. Constant members; 9. Runtime enum object; 10. Enum member types.

**11–20:** 11. Numeric reverse mapping; 12. String enum behavior; 13. `const enum`; 14. Inlining concept; 15. Compilation implications; 16. Library concerns; 17. Isolated modules concerns; 18. Ambient enums; 19. Declaration enums; 20. Enum compatibility.

**21–30:** 21. Union enums; 22. Member literals; 23. Narrowing enums; 24. Switch enums; 25. Exhaustiveness; 26. Bit flags concept; 27. Powers of two; 28. Flag combinations; 29. Readability; 30. Risks of numeric values.

**31–40:** 31. Object-as-enum; 32. `as const`; 33. `keyof typeof`; 34. Value unions; 35. String unions; 36. Enum alternatives; 37. Runtime availability; 38. Tree-shaking considerations concept; 39. Serialization; 40. Interoperability.

**41–50:** 41. `symbol`; 42. Symbol creation; 43. Symbol keys; 44. Unique symbol; 45. `unique symbol`; 46. Const requirement; 47. Symbol identity; 48. Computed keys; 49. Interface symbol properties; 50. Hidden-ish metadata.

**51–60:** 51. Well-known symbols; 52. `Symbol.iterator`; 53. Symbol-based protocols; 54. Runtime identity; 55. Type-level uniqueness; 56. Nominal-like branding; 57. Token patterns; 58. Dependency tokens concept; 59. Unique keys; 60. Collision avoidance.

**61–70:** 61. Constants; 62. Frozen domains; 63. Literal maps; 64. Configuration maps; 65. Status maps; 66. Error codes; 67. Command types; 68. Event names; 69. API constants; 70. Deriving types.

**71–80:** 71. Enum serialization; 72. Numeric stability; 73. Public APIs; 74. Versioning enum members; 75. Renaming concerns; 76. Adding members; 77. Exhaustiveness impact; 78. Unknown future values; 79. Open-ended domains; 80. Closed domains.

**81–90:** 81. Enum vs union decision; 82. Enum vs constant object; 83. Runtime requirement; 84. Type-only requirement; 85. Library API ergonomics; 86. Declaration output; 87. JS consumer experience; 88. TS consumer experience; 89. Compatibility; 90. Team standards.

**91–100:** 91. Enum antipatterns; 92. Mixed enums; 93. Arbitrary numbers; 94. Const enum tradeoffs; 95. String serialization; 96. Symbols limitations; 97. Debuggability; 98. Domain design; 99. Alternatives comparison; 100. Decision mastery.

### Quiz

1. ¿Qué es numeric enum? 2. ¿Qué es string enum? 3. ¿Qué es reverse mapping? 4. ¿Ocurre con string enums? 5. ¿Qué es const enum? 6. ¿Qué implica inlining? 7. ¿Qué riesgos puede tener en librerías? 8. ¿Qué es ambient enum? 9. ¿Qué es union enum? 10. ¿Cómo narrowing enum?

2. ¿Qué alternativa existe con as const? 12. ¿Cómo derivar keys? 13. ¿Cómo derivar values? 14. ¿Cuándo preferir string union? 15. ¿Cuándo runtime object es útil? 16. ¿Qué es symbol? 17. ¿Qué garantiza unique symbol? 18. ¿Cómo se usa como property key? 19. ¿Qué es Symbol.iterator? 20. ¿Por qué evita colisiones?

3. ¿Puede unique symbol ayudar a branding? 22. ¿Qué es closed domain? 23. ¿Qué es open domain? 24. ¿Qué ocurre al añadir enum member? 25. ¿Cómo afecta exhaustive switch? 26. ¿Qué problema genera numeric serialization? 27. ¿Qué es bit flag? 28. ¿Por qué powers of two? 29. ¿Qué es constant map? 30. ¿Cómo evitar duplicar union?

4. ¿Qué significa JS consumer experience? 32. ¿Qué significa declaration output? 33. ¿Por qué const enum puede complicar isolated modules? 34. ¿Qué es heterogeneous enum? 35. ¿Por qué suele evitarse? 36. ¿Qué es computed member? 37. ¿Qué es symbol identity? 38. ¿Qué diferencia tiene respecto a string key? 39. ¿Qué opción elegirías para estados serializados? 40. Justifica.

### Examen

Implementa el mismo dominio tres veces: enum, string union y object-as-enum. Compara ergonomía, runtime y serialización.

### Proyecto

**Domain Constants Laboratory**.

### Dominio

Poder justificar cuándo usar enum y cuándo no.

---

# PARTE III — CLASES Y ORIENTACIÓN A OBJETOS EN TYPESCRIPT

# MÓDULO 16 — Clases TypeScript

### 100 temas

**1–10:** 1. Class declarations; 2. Instances; 3. Constructors; 4. Fields; 5. Methods; 6. Initialization; 7. `this`; 8. Instance type; 9. Constructor value; 10. Static side.

**11–20:** 11. Field annotations; 12. Field inference; 13. Definite initialization; 14. Strict property initialization; 15. Constructor assignment; 16. Optional fields; 17. Readonly fields; 18. Initializers; 19. Parameter properties; 20. Constructor parameters.

**21–30:** 21. `public`; 22. `private`; 23. `protected`; 24. Default public; 25. TS private; 26. JS `#private`; 27. Runtime privacy; 28. Compile-time privacy; 29. Protected access; 30. Encapsulation.

**31–40:** 31. Getters; 32. Setters; 33. Accessor typing; 34. Read-only accessor; 35. Getter inference; 36. Setter parameter; 37. Accessor visibility; 38. Backing fields; 39. Validation; 40. Computed state.

**41–50:** 41. Static fields; 42. Static methods; 43. Static blocks concept; 44. Static this; 45. Constructor properties; 46. Factory statics; 47. Counters; 48. Registries; 49. Static vs instance; 50. Static limitations.

**51–60:** 51. Class expressions; 52. Anonymous classes; 53. Named expressions; 54. Class types; 55. Constructor types; 56. InstanceType preview; 57. `typeof Class`; 58. Static-side typing; 59. Passing constructors; 60. Factory functions.

**61–70:** 61. `implements`; 62. Interface contracts; 63. Multiple interfaces; 64. Implements doesn't alter class; 65. Optional interface members; 66. Method signatures; 67. Public surface; 68. Private members and compatibility; 69. Protected compatibility; 70. Structural class typing.

**71–80:** 71. `this` types; 72. Polymorphic this; 73. Fluent APIs; 74. Chainable methods; 75. Returning this; 76. This-based guards; 77. `this is T`; 78. State refinement; 79. Subclass fluent behavior; 80. Builder foundations.

**81–90:** 81. Class initialization order; 82. Field order; 83. Constructor execution; 84. Derived class considerations; 85. Runtime emitted fields; 86. `useDefineForClassFields`; 87. ECMAScript class semantics; 88. Downlevel class emit; 89. Target interactions; 90. Runtime behavior.

**91–100:** 91. Class vs object; 92. Class vs factory; 93. Data vs behavior; 94. Encapsulation boundaries; 95. Domain entities; 96. Value objects; 97. Service objects; 98. Testing classes; 99. Refactoring classes; 100. Class mastery.

### Quiz

1. ¿Qué es instance side? 2. ¿Qué es static side? 3. ¿Cómo obtienes el constructor type? 4. ¿Qué hace strictPropertyInitialization? 5. ¿Qué es parameter property? 6. ¿Qué significa public? 7. ¿Qué significa protected? 8. ¿Qué significa private? 9. ¿TS private existe en runtime? 10. ¿Qué diferencia tiene `#private`?

2. ¿Qué es getter? 12. ¿Qué es setter? 13. ¿Qué es static method? 14. ¿Qué es class expression? 15. ¿Qué hace implements? 16. ¿Cambia la clase? 17. ¿Puede implementar varios interfaces? 18. ¿Qué es structural class typing? 19. ¿Qué es polymorphic this? 20. ¿Para qué sirve?

3. ¿Qué es fluent API? 22. ¿Qué significa `this is T`? 23. ¿Qué es constructor type? 24. ¿Cómo pasas una clase como valor? 25. ¿Qué diferencia hay entre clase y instancia? 26. ¿Qué es field initializer? 27. ¿Qué significa definite initialization? 28. ¿Qué hace `!` en field? 29. ¿Qué riesgo tiene? 30. ¿Qué es useDefineForClassFields?

4. ¿Por qué importa runtime semantics? 32. ¿Cuándo usar factory en lugar de clase? 33. ¿Qué es domain entity? 34. ¿Qué es value object? 35. ¿Qué es backing field? 36. ¿Qué significa encapsulación? 37. ¿Pueden readonly fields mutarse en constructor? 38. ¿Qué significa optional field? 39. ¿Qué diferencia tiene de undefined? 40. Diseña una clase segura.

### Examen

Construye un sistema bancario orientado a objetos con encapsulación, readonly, private fields, getters y contracts.

### Proyecto

**Typed Banking Domain**.

### Dominio

Dominar lados estático/instancia y semántica runtime.

---

# MÓDULO 17 — Herencia, abstracción y polimorfismo

### 100 temas

**1–10:** 1. `extends`; 2. Base class; 3. Derived class; 4. `super`; 5. Constructor chaining; 6. Method inheritance; 7. Field inheritance; 8. Property visibility; 9. Protected members; 10. Private members.

**11–20:** 11. Method overriding; 12. Override compatibility; 13. `override`; 14. `noImplicitOverride`; 15. Parameter compatibility; 16. Return compatibility; 17. Covariant-like returns; 18. Unsafe overrides; 19. Runtime dispatch; 20. Dynamic polymorphism.

**21–30:** 21. Abstract classes; 22. `abstract`; 23. Abstract methods; 24. Abstract fields; 25. Abstract accessors; 26. Concrete implementations; 27. Instantiation prohibition; 28. Abstract constructors; 29. Shared implementation; 30. Template method pattern.

**31–40:** 31. Interfaces vs abstract classes; 32. State sharing; 33. Behavior sharing; 34. Multiple interfaces; 35. Single class inheritance; 36. Composition alternative; 37. Deep hierarchies; 38. Fragile base class; 39. Liskov concept; 40. Substitutability.

**41–50:** 41. Polymorphism; 42. Base references; 43. Derived instances; 44. Method dispatch; 45. Structural polymorphism; 46. Nominal constraints via private; 47. Protected compatibility; 48. Generic base classes; 49. Generic derived classes; 50. Specialization.

**51–60:** 51. `this` polymorphism; 52. Fluent inheritance; 53. Self types; 54. Factory methods; 55. Abstract factory contracts; 56. Constructor constraints; 57. Class registries; 58. Plugin patterns concept; 59. Extensible architectures; 60. Closed hierarchies.

**61–70:** 61. Discriminated unions vs subclasses; 62. Algebraic modeling; 63. Visitor concept; 64. Pattern matching alternatives; 65. Switch over tags; 66. Virtual dispatch; 67. Data-oriented design; 68. Behavior-oriented design; 69. Tradeoffs; 70. Refactoring strategies.

**71–80:** 71. Mixins preview; 72. Multiple behavior composition; 73. Mixin constructors; 74. Intersection output; 75. Trait-like patterns; 76. Decorator alternative conceptual; 77. Delegation; 78. Composition; 79. Aggregation; 80. Dependency relationships.

**81–90:** 81. Protected constructors; 82. Private constructors; 83. Singleton typing concept; 84. Controlled creation; 85. Static factories; 86. Abstract static limitation discussion; 87. Static contracts workaround; 88. Constructor interfaces; 89. Generic factories; 90. Class tokens.

**91–100:** 91. Inheritance smells; 92. Base class coupling; 93. Override surprises; 94. Initialization ordering; 95. Constructor virtual-call hazard; 96. Favor composition principle; 97. When inheritance fits; 98. Domain hierarchy design; 99. API hierarchy design; 100. OOP mastery.

### Quiz

1. ¿Qué hace extends? 2. ¿Para qué sirve super? 3. ¿Qué es override? 4. ¿Qué hace noImplicitOverride? 5. ¿Qué es runtime dispatch? 6. ¿Qué es abstract class? 7. ¿Puede instanciarse? 8. ¿Qué es abstract method? 9. ¿Por qué usar interface en vez de abstract? 10. ¿Cuándo abstract aporta valor?

2. ¿Qué es polymorphism? 12. ¿Qué significa substitutability? 13. ¿Qué es fragile base class? 14. ¿Por qué evitar jerarquías profundas? 15. ¿Qué es composition? 16. ¿Qué es delegation? 17. ¿Qué es aggregation? 18. ¿Qué es structural polymorphism? 19. ¿Qué efecto tienen private fields en compatibility? 20. ¿Qué es generic base class?

3. ¿Qué es specialization? 22. ¿Qué es template method? 23. ¿Qué es fluent inheritance? 24. ¿Qué es self type? 25. ¿Cuándo discriminated union puede reemplazar subclasses? 26. ¿Qué es virtual dispatch? 27. ¿Qué es data-oriented modeling? 28. ¿Qué es behavior-oriented modeling? 29. ¿Qué es mixin? 30. ¿Por qué TS necesita constructor pattern para mixins?

4. ¿Qué es protected constructor? 32. ¿Qué es private constructor? 33. ¿Qué es controlled creation? 34. ¿Qué es static factory? 35. ¿Qué peligro tiene llamar métodos sobrescribibles durante construcción? 36. ¿Qué significa favor composition? 37. ¿Cuándo sí usar herencia? 38. ¿Qué es closed hierarchy? 39. ¿Cómo diseñar plugins con contratos? 40. Diseña una jerarquía extensible.

### Examen

Crea una jerarquía de sistemas de pago y después refactorízala mediante composición. Compara ambos diseños.

### Proyecto

**Payment Polymorphism Laboratory**.

### Dominio

Reconocer cuándo usar herencia, interface, union o composición.

---

# MÓDULO 18 — Generics desde cero

Los genéricos permiten construir componentes que funcionan sobre múltiples tipos conservando la información específica del tipo utilizado. ([TypeScript][3])

### 100 temas

**1–10:** 1. Generic motivation; 2. Type parameters; 3. `<T>` syntax; 4. Identity function; 5. Generic inference; 6. Explicit type arguments; 7. Reusability; 8. Type preservation; 9. Any comparison; 10. Unknown comparison.

**11–20:** 11. Multiple type parameters; 12. `<T,U>`; 13. Naming conventions; 14. Input-output relationships; 15. Generic arrays; 16. Generic tuples; 17. Generic objects; 18. Generic callbacks; 19. Generic returns; 20. Generic predicates.

**21–30:** 21. Generic type aliases; 22. Generic interfaces; 23. Generic classes; 24. Generic call signatures; 25. Parameter placement; 26. Interface-level generic; 27. Method-level generic; 28. Class-level generic; 29. Static limitation; 30. Instance side.

**31–40:** 31. Generic defaults intro; 32. Optional type arguments; 33. Default parameters; 34. Inference priorities; 35. Contextual generic inference; 36. Return-based inference limitations; 37. Callback inference; 38. Bidirectional inference concept; 39. Literal preservation; 40. Widening.

**41–50:** 41. Generic container; 42. `Box<T>`; 43. `Result<T>`; 44. `Pair<A,B>`; 45. `Response<T>`; 46. `Tree<T>` preview; 47. `Repository<T>` conceptual; 48. `Comparator<T>`; 49. `Predicate<T>`; 50. `Mapper<A,B>`.

**51–60:** 51. Generic functions on arrays; 52. First element; 53. Last element; 54. Map-like transform; 55. Filter helper; 56. Grouping concept; 57. Indexing issue; 58. Constraints need; 59. Property access limitations; 60. Safe generic operations.

**61–70:** 61. Relationship modeling; 62. Same-type parameters; 63. Different-type parameters; 64. Producer/consumer concept; 65. Generic callbacks; 66. Higher-order generics; 67. Function wrappers; 68. Generic factories; 69. Constructor generics; 70. Generic builders preview.

**71–80:** 71. Generic API design; 72. Inference-first APIs; 73. Explicit generics only when needed; 74. Excess type parameters; 75. Unused parameters; 76. Single-use parameters; 77. Relating values; 78. Avoid unnecessary generics; 79. Error readability; 80. Consumer ergonomics.

**81–90:** 81. Generic async functions; 82. `Promise<T>`; 83. Generic iterables preview; 84. Generic generators preview; 85. Generic class methods; 86. Generic static methods; 87. Generic interfaces composition; 88. Nested generics; 89. Generic unions; 90. Generic intersections.

**91–100:** 91. Generic recursion preview; 92. Generic narrowing concerns; 93. Generic constraints preview; 94. `keyof` preview; 95. Conditional types preview; 96. Generic debugging; 97. Inspect instantiated types; 98. Design exercises; 99. Generic refactoring; 100. Generic fundamentals mastery.

### Quiz

1. ¿Qué problema resuelve generic? 2. ¿Qué es type parameter? 3. ¿Qué representa T? 4. ¿Qué es type argument? 5. ¿Qué es generic inference? 6. ¿Por qué generic es mejor que any? 7. ¿Cómo conserva información? 8. ¿Puedes tener varios parámetros? 9. ¿Qué es generic alias? 10. ¿Qué es generic interface?

2. ¿Qué es generic class? 12. ¿Puede static member usar T de clase? 13. ¿Por qué? 14. ¿Qué es method-level generic? 15. ¿Qué es class-level generic? 16. ¿Qué es generic default? 17. ¿Qué significa inference-first API? 18. ¿Cuándo especificar type argument? 19. ¿Qué es Box<T>? 20. ¿Qué es Result<T>?

3. ¿Qué significa same-type relationship? 22. ¿Qué significa input-output relationship? 23. ¿Qué es generic callback? 24. ¿Qué es generic factory? 25. ¿Qué significa nested generic? 26. ¿Qué problema tiene exceso de parameters? 27. ¿Por qué evitar unused T? 28. ¿Cuándo generic es innecesario? 29. ¿Qué significa literal preservation? 30. ¿Cómo widening afecta generic?

4. ¿Qué es producer? 32. ¿Qué es consumer? 33. ¿Cómo tipar Promise genérica? 34. ¿Qué es generic intersection? 35. ¿Qué es generic union? 36. ¿Cómo debugging de generic? 37. ¿Qué significa instantiated type? 38. ¿Qué es contextual generic inference? 39. ¿Qué limitaciones tiene property access sobre T? 40. ¿Por qué necesitamos constraints?

### Examen

Implementa `Collection<T>` con operaciones map, filter, find, first, last y reduce sin `any`.

### Proyecto

**Generic Data Structures Core**.

### Dominio

Diseñar APIs donde el usuario rara vez tenga que escribir manualmente los argumentos genéricos.

---

# MÓDULO 19 — Generic Constraints, defaults y relaciones entre parámetros

### 100 temas

**1–10:** 1. `T extends U`; 2. Constraints; 3. Capability requirements; 4. `{ length:number }`; 5. Structural constraints; 6. Object constraints; 7. Property constraints; 8. Function constraints; 9. Constructor constraints; 10. Union constraints.

**11–20:** 11. `keyof` constraints intro; 12. `<K extends keyof T>`; 13. Safe property access; 14. Generic getter; 15. Generic setter; 16. Related parameters; 17. Constraint inference; 18. Constraint errors; 19. Minimal constraints; 20. Over-constraining.

**21–30:** 21. Default type parameters; 22. `<T = unknown>`; 23. Defaults after required params; 24. Optional generic arguments; 25. Derived defaults; 26. Constraint + default; 27. API backwards compatibility; 28. Generic evolution; 29. Default ergonomics; 30. Sensible defaults.

**31–40:** 31. Multiple constraints via intersections; 32. `T extends A & B`; 33. Has-ID patterns; 34. Timestamp patterns; 35. Comparable patterns; 36. Serializable-like patterns; 37. Callable constraints; 38. Constructable constraints; 39. Abstract constructors; 40. Instance relation.

**41–50:** 41. Factory generics; 42. `new (...args)=>T`; 43. ConstructorParameters preview; 44. InstanceType preview; 45. Constructor inference; 46. Generic dependency factories; 47. Registry patterns; 48. Class tokens; 49. Subclass constraints; 50. Base class constraints.

**51–60:** 51. Key/value relationships; 52. Object key generic; 53. Object value generic; 54. Indexed access preview; 55. Update property; 56. Pick properties; 57. Merge objects; 58. Correlating keys and values; 59. Preserving key-specific value; 60. Avoiding union loss.

**61–70:** 61. Constraint vs intersection parameter; 62. Constraint vs annotation; 63. Generic narrowing limitations; 64. Conditional workaround preview; 65. Inference from constraint; 66. Inference candidates; 67. NoInfer concept later; 68. Inference control; 69. Literal capture; 70. Const generics concept.

**71–80:** 71. Higher-order constrained generics; 72. Generic callbacks; 73. Collection constraints; 74. Readonly collection constraints; 75. Tuple constraints; 76. Variadic tuple constraints; 77. Promise-like constraints; 78. Function parameter constraints; 79. Return constraints; 80. Recursive constraints preview.

**81–90:** 81. F-bounded polymorphism concept; 82. Self constraints; 83. Fluent builder relations; 84. State generic relations; 85. Phantom parameters concept; 86. Branding generics preview; 87. Generic variance; 88. Covariance; 89. Contravariance; 90. Invariance concept.

**91–100:** 91. Constraint API smell; 92. Too-broad constraints; 93. Too-narrow constraints; 94. `{}` caveat; 95. `object` caveat; 96. Record constraints; 97. Unknown records; 98. Consumer error quality; 99. Constraint refactoring; 100. Constraint mastery.

### Quiz

1. ¿Qué significa `T extends U`? 2. ¿Es herencia necesariamente? 3. ¿Qué es structural constraint? 4. ¿Cómo exigir `.length`? 5. ¿Qué significa `K extends keyof T`? 6. ¿Qué garantiza? 7. ¿Qué es generic default? 8. ¿Cómo combinar constraint y default? 9. ¿Qué es over-constraining? 10. ¿Por qué es malo?

2. ¿Cómo exigir dos contratos? 12. ¿Qué es constructor constraint? 13. ¿Qué representa `new (...args)=>T`? 14. ¿Cómo relacionar key con value? 15. ¿Qué problema aparece si pierdes correlación? 16. ¿Qué es inference candidate? 17. ¿Qué significa literal capture? 18. ¿Qué es tuple constraint? 19. ¿Qué es readonly collection constraint? 20. ¿Qué significa F-bounded conceptualmente?

3. ¿Qué es self constraint? 22. ¿Qué es phantom parameter? 23. ¿Qué es covariance? 24. ¿Qué es contravariance? 25. ¿Qué es invariance? 26. ¿Qué diferencia existe entre constraint e intersection? 27. ¿Qué riesgo tiene `{}`? 28. ¿Qué significa object? 29. ¿Qué es Record constraint? 30. ¿Cómo mejorar error quality?

4. ¿Qué es generic factory? 32. ¿Qué es class token? 33. ¿Qué es base-class constraint? 34. ¿Cómo evolucionar generic API? 35. ¿Para qué sirven defaults? 36. ¿Qué es sensible default? 37. ¿Por qué minimal constraint? 38. ¿Cómo usar keyof con generic? 39. ¿Cómo implementar getter seguro? 40. ¿Cómo implementar setter seguro?

### Examen

Crea un repositorio genérico donde entidades deban poseer ID, timestamps y distintas claves actualizables de forma segura.

### Proyecto

**Generic Repository Type Engine** — solo abstracciones TypeScript, sin base de datos.

### Dominio

Relacionar parámetros genéricos manteniendo inferencia específica.

---

# MÓDULO 20 — `keyof`, `typeof` e Indexed Access Types

### 100 temas

**1–10:** 1. `keyof`; 2. Object keys; 3. Key unions; 4. String keys; 5. Number keys; 6. Symbol keys; 7. Index signatures; 8. `keyof` dictionaries; 9. `keyof any`; 10. PropertyKey relationship.

**11–20:** 11. `typeof` type operator; 12. Value-to-type bridge; 13. Variables; 14. Functions; 15. Objects; 16. Arrays; 17. Classes; 18. `typeof Class`; 19. Constructor side; 20. Constant object derivation.

**21–30:** 21. Indexed access `T[K]`; 22. Literal key access; 23. Union key access; 24. `T[keyof T]`; 25. Value unions; 26. Nested indexed access; 27. Array element extraction; 28. `T[number]`; 29. Tuple element extraction; 30. Readonly arrays.

**31–40:** 31. Generic indexed access; 32. `<K extends keyof T>`; 33. Safe getters; 34. Safe setters; 35. Correlated values; 36. Property pickers; 37. Projection functions; 38. Pluck patterns; 39. Dynamic keys; 40. Key arrays.

**41–50:** 41. `keyof typeof`; 42. Constant maps; 43. Enum-like maps; 44. Derive key unions; 45. Derive value unions; 46. Single source of truth; 47. Configuration keys; 48. Event maps; 49. Route maps; 50. Command maps.

**51–60:** 51. Function `typeof`; 52. ReturnType preparation; 53. Parameters preparation; 54. Constructor `typeof`; 55. InstanceType preparation; 56. Static members; 57. Class instance extraction; 58. Generic function typeof; 59. Overloaded typeof caveats; 60. Declaration references.

**61–70:** 61. Nested path types intro; 62. `T[A][B]`; 63. Optional nested properties; 64. Undefined propagation; 65. NonNullable preview; 66. Indexed union types; 67. Distribution misconceptions; 68. Intersections and keys; 69. Union keyof behavior; 70. Shared keys understanding.

**71–80:** 71. `keyof` unions nuances; 72. Key extraction helper; 73. Value extraction helper; 74. Key filtering preview; 75. Value-based keys preview; 76. Mapped types bridge; 77. Conditional types bridge; 78. Template types bridge; 79. Generic utilities; 80. Type-level transformations.

**81–90:** 81. `typeof` limitations; 82. Expression restrictions; 83. Value availability; 84. Import type queries preview; 85. Runtime vs type namespace; 86. Name collisions; 87. Dual namespace classes; 88. Enums duality; 89. Type-only values; 90. Value-only entities.

**91–100:** 91. Debugging keyof; 92. Numeric index surprises; 93. String index implications; 94. Symbol keys; 95. Safe dynamic property access; 96. Avoiding string indexing; 97. Derive, don't duplicate; 98. Type relations; 99. Utility foundations; 100. Operator mastery.

### Quiz

1. ¿Qué produce keyof? 2. ¿Qué produce typeof en type position? 3. ¿Es igual que runtime typeof? 4. ¿Qué hace T[K]? 5. ¿Qué significa T[keyof T]? 6. ¿Cómo obtienes element type de array? 7. ¿Qué significa T[number]? 8. ¿Qué es keyof typeof? 9. ¿Por qué es útil? 10. ¿Cómo crear getter seguro?

2. ¿Por qué K extends keyof T? 12. ¿Qué retorna T[K]? 13. ¿Qué ocurre si K es union? 14. ¿Cómo derivar keys desde objeto constante? 15. ¿Cómo derivar values? 16. ¿Qué es single source of truth? 17. ¿Qué produce typeof Class? 18. ¿Es instancia? 19. ¿Cómo obtendrías instancia posteriormente? 20. ¿Qué significa dual namespace?

3. ¿Cómo funcionan symbol keys? 22. ¿Qué es PropertyKey? 23. ¿Qué hace string index signature a keyof? 24. ¿Cómo afectan unions? 25. ¿Qué son shared keys? 26. ¿Qué es nested indexed access? 27. ¿Cómo afecta undefined? 28. ¿Qué es key filtering? 29. ¿Qué tema permite implementarlo? 30. ¿Qué son mapped types?

4. ¿Por qué derive, don't duplicate? 32. ¿Qué problema evita? 33. ¿Qué diferencia hay entre value space y type space? 34. ¿Puede interface usarse como runtime value? 35. ¿Puede class? 36. ¿Puede enum? 37. ¿Qué es dynamic property access? 38. ¿Cómo hacerlo seguro? 39. ¿Por qué no usar string arbitrario? 40. Diseña un `getProperty`.

### Examen

Construye un motor genérico de lectura/actualización de propiedades profundamente tipadas mediante `keyof`, `typeof` e indexed access.

### Proyecto

**Typed Object Introspection Toolkit**.

### Dominio

Derivar tipos a partir de estructuras existentes evitando duplicación.

---

# PARTE IV — METAPROGRAMACIÓN DE TIPOS

# MÓDULO 21 — Mapped Types

### 100 temas

**1–10:** 1. Mapped type syntax; 2. `[K in keyof T]`; 3. Key iteration; 4. Property transformation; 5. Value preservation; 6. Generic mapped types; 7. Property modifiers; 8. `readonly`; 9. Optional; 10. Mapped output.

**11–20:** 11. Add readonly; 12. Remove readonly; 13. `+readonly`; 14. `-readonly`; 15. Add optional; 16. Remove optional; 17. `+?`; 18. `-?`; 19. Modifier composition; 20. Required transformations.

**21–30:** 21. Implement `Partial`; 22. Implement `Required`; 23. Implement `Readonly`; 24. Implement Record-like; 25. Identity mapped type; 26. Clone type; 27. Mutable type; 28. Nullable properties; 29. Promise properties; 30. Boolean flags.

**31–40:** 31. Key remapping; 32. `as` clause; 33. Rename keys; 34. Prefix keys; 35. Suffix keys; 36. Template literals integration; 37. Getter generation; 38. Setter generation; 39. Event generation; 40. API transformation.

**41–50:** 41. Filter keys with never; 42. Remove properties; 43. Keep properties; 44. Value-based filtering; 45. Key-based filtering; 46. Function-property extraction; 47. Data-property extraction; 48. Readonly key concepts; 49. Optional key concepts; 50. Required key concepts.

**51–60:** 51. Mapping unions of keys; 52. Literal unions; 53. Record generation; 54. Permission maps; 55. Feature flags; 56. Event handler maps; 57. Validator maps; 58. Formatter maps; 59. Serializer maps; 60. Resolver maps.

**61–70:** 61. Nested mapped types; 62. Deep readonly intro; 63. Deep partial intro; 64. Recursive mapped types; 65. Arrays considerations; 66. Functions considerations; 67. Tuples considerations; 68. Built-ins considerations; 69. Base cases; 70. Recursion complexity.

**71–80:** 71. Mapped types over tuples; 72. Tuple preservation; 73. Array-like mapping; 74. Numeric keys; 75. Key remapping effects; 76. Symbol keys; 77. Property metadata; 78. Optional semantics; 79. Exact optional settings; 80. Index signature interactions.

**81–90:** 81. Homomorphic mapped types; 82. Modifier preservation; 83. Non-homomorphic maps; 84. Key unions; 85. Type display; 86. Simplification helpers; 87. Intersection normalization; 88. Public utility types; 89. Error readability; 90. Performance considerations.

**91–100:** 91. Mapping domain models; 92. DTO transformation; 93. Form-state transformation; 94. Error-state transformation; 95. API transformations; 96. Schema metadata; 97. Compile-time generation; 98. Utility design; 99. Reusability; 100. Mapped type mastery.

### Quiz

1. ¿Qué es mapped type? 2. ¿Qué significa `[K in keyof T]`? 3. ¿Cómo añades readonly? 4. ¿Cómo lo eliminas? 5. ¿Cómo añades optional? 6. ¿Cómo lo eliminas? 7. ¿Cómo implementarías Partial? 8. ¿Required? 9. ¿Readonly? 10. ¿Qué es key remapping?

2. ¿Qué hace `as` dentro de mapped type? 12. ¿Cómo eliminar una key? 13. ¿Por qué never? 14. ¿Qué es getter generation? 15. ¿Qué papel tienen template literals? 16. ¿Qué es recursive mapped type? 17. ¿Qué necesita una recursión? 18. ¿Qué son base cases? 19. ¿Por qué arrays requieren tratamiento? 20. ¿Y functions?

3. ¿Qué es homomorphic mapped type? 22. ¿Qué preserva? 23. ¿Qué es non-homomorphic? 24. ¿Cómo mapear tuple? 25. ¿Qué ocurre con modifiers? 26. ¿Cómo extraer function properties? 27. ¿Cómo extraer data properties? 28. ¿Qué es feature flag map? 29. ¿Qué es validator map? 30. ¿Qué es resolver map?

4. ¿Qué es DTO transformation? 32. ¿Cómo generar form state? 33. ¿Cómo generar errors? 34. ¿Qué problema tiene recursion complexity? 35. ¿Cómo mejorar readability? 36. ¿Qué es simplification helper? 37. ¿Qué efecto tiene exact optional? 38. ¿Qué son symbol keys? 39. ¿Cómo mapped types reducen duplicación? 40. Diseña un utility propio.

### Examen

Implementa desde cero diez utility types basados en mapped types sin usar sus equivalentes nativos.

### Proyecto

**Mapped Utility Library**.

### Dominio

Transformar estructuras arbitrarias utilizando únicamente relaciones entre claves y valores.

---

# MÓDULO 22 — Conditional Types

### 100 temas

**1–10:** 1. Conditional syntax; 2. `T extends U ? X : Y`; 3. True branch; 4. False branch; 5. Assignability test; 6. Generic conditionals; 7. Non-generic conditionals; 8. Type-level branching; 9. Compile-time selection; 10. Relationship testing.

**11–20:** 11. Primitive conditions; 12. Object conditions; 13. Function conditions; 14. Array conditions; 15. Tuple conditions; 16. Promise conditions; 17. Nullable conditions; 18. Key conditions; 19. Constraint interaction; 20. Nested conditionals.

**21–30:** 21. Distributive conditionals; 22. Naked type parameter; 23. Union distribution; 24. Member-wise evaluation; 25. Filtering unions; 26. `never` elimination; 27. Extract pattern; 28. Exclude pattern; 29. NonNullable pattern; 30. Type filtering.

**31–40:** 31. Prevent distribution; 32. `[T] extends [U]`; 33. Tuple wrapper; 34. Whole-union test; 35. Distribution control; 36. Surprising distribution; 37. Boolean-like results; 38. IsNever challenge; 39. IsAny challenge concept; 40. IsUnknown concept.

**41–50:** 41. Conditional object transformation; 42. Conditional property type; 43. Function return mapping; 44. Array element mapping; 45. Promise unwrapping; 46. Recursive unwrapping; 47. Flatten type; 48. Element type; 49. Nullable removal; 50. Conditional wrappers.

**51–60:** 51. Nested branches; 52. Decision trees; 53. Type classification; 54. Primitive classifier; 55. Collection classifier; 56. Function classifier; 57. Fallback behavior; 58. `never` fallback; 59. `unknown` fallback; 60. Error types concept.

**61–70:** 61. Constraints vs conditionals; 62. Move constraint inside; 63. More flexible utilities; 64. Conditional member access; 65. Safe indexing; 66. Key validation; 67. Function signature testing; 68. Constructor signature testing; 69. Structural pattern matching; 70. Type pattern matching.

**71–80:** 71. Conditional + mapped; 72. Filter keys; 73. Transform selected values; 74. Conditional + template literals; 75. Conditional + tuples; 76. Conditional + recursion; 77. Deep utility foundations; 78. Parser foundations; 79. Type arithmetic concepts; 80. Advanced transformations.

**81–90:** 81. Performance costs; 82. Instantiation depth; 83. Recursive complexity; 84. Union explosion; 85. Simplification; 86. Helper decomposition; 87. Tail recursion concepts; 88. Compiler limits; 89. Error readability; 90. Type design pragmatism.

**91–100:** 91. API response conditional; 92. Generic function returns; 93. Conditional configuration; 94. Capability detection; 95. Feature typing; 96. Utility composition; 97. Testing type conditionals; 98. Negative cases; 99. Debugging distribution; 100. Conditional mastery.

### Quiz

1. ¿Qué forma tiene conditional type? 2. ¿Qué prueba extends? 3. ¿Qué es true branch? 4. ¿Qué es false branch? 5. ¿Qué es distributive conditional? 6. ¿Cuándo ocurre? 7. ¿Qué significa naked type parameter? 8. ¿Cómo desactivar distribución? 9. ¿Qué papel tiene never? 10. ¿Cómo implementar Exclude?

2. ¿Cómo implementar Extract? 12. ¿Cómo implementar NonNullable? 13. ¿Qué es whole-union test? 14. ¿Qué es nested conditional? 15. ¿Qué es type classifier? 16. ¿Cómo extraerías element type? 17. ¿Cómo unwrap Promise conceptualmente? 18. ¿Qué diferencia hay entre constraint y conditional? 19. ¿Por qué mover constraint dentro? 20. ¿Qué significa structural pattern matching?

3. ¿Cómo combinar conditional con mapped? 22. ¿Cómo filtrar keys? 23. ¿Cómo combinar con recursion? 24. ¿Qué es union explosion? 25. ¿Qué es instantiation depth? 26. ¿Por qué preocupa performance? 27. ¿Cómo simplificar utilities? 28. ¿Qué significa helper decomposition? 29. ¿Qué es fallback type? 30. ¿Cuándo usar never?

4. ¿Cuándo usar unknown? 32. ¿Qué significa capability detection? 33. ¿Cómo testear conditional utilities? 34. ¿Qué son negative cases? 35. ¿Cómo detectar distribución accidental? 36. ¿Qué ocurre con `never` distributivamente? 37. ¿Por qué IsNever es peculiar? 38. ¿Qué es type-level branch? 39. ¿Qué utilidad real tiene? 40. Diseña un conditional utility.

### Examen

Implementa `Flatten`, `UnwrapPromise`, `OnlyFunctions`, `OnlyStrings`, `ExcludeNullish`, `ElementType` y cuatro utilities adicionales.

### Proyecto

**Conditional Type Toolkit**.

### Dominio

Predecir exactamente cuándo ocurre distribución.

---

# MÓDULO 23 — `infer` y extracción avanzada de tipos

### 100 temas

**1–10:** 1. `infer`; 2. Conditional context; 3. Pattern variables; 4. Extracting return types; 5. Extracting parameters; 6. Array elements; 7. Promise values; 8. Constructor instances; 9. Constructor parameters; 10. Tuple parts.

**11–20:** 11. `infer R`; 12. Multiple infer variables; 13. Repeated inference; 14. Covariant inference; 15. Contravariant inference concept; 16. Union inference; 17. Intersection tendencies concept; 18. Constraint on infer; 19. Nested infer; 20. Scoped inference variables.

**21–30:** 21. ReturnType implementation; 22. Parameters implementation; 23. ConstructorParameters implementation; 24. InstanceType implementation; 25. Awaited-like implementation; 26. First element; 27. Last element; 28. Tail tuple; 29. Head tuple; 30. Init tuple.

**31–40:** 31. Function patterns; 32. Async function patterns; 33. Generic function caveats; 34. Overloaded function caveats; 35. Last overload behavior; 36. Callable extraction; 37. Constructor extraction; 38. Method extraction; 39. Callback extraction; 40. Event payload extraction.

**41–50:** 41. Promise extraction; 42. Nested promises; 43. Recursive awaited; 44. Thenable concepts; 45. Array extraction; 46. Readonly array extraction; 47. Tuple extraction; 48. Variadic tuples; 49. Prefix inference; 50. Suffix inference.

**51–60:** 51. String pattern inference; 52. Template literal infer; 53. Prefix extraction; 54. Suffix extraction; 55. Segment extraction; 56. Route parameters preview; 57. Event-name parsing; 58. Key-name parsing; 59. Delimited strings; 60. Recursive string parsing.

**61–70:** 61. Object pattern inference; 62. Property extraction; 63. Generic container extraction; 64. `Box<infer T>`; 65. `Result<infer T>`; 66. Nested generic extraction; 67. Multiple generic arguments; 68. Wrapper detection; 69. Data extraction; 70. Error extraction.

**71–80:** 71. Infer constraints; 72. `infer S extends string`; 73. Narrow inference; 74. Better recursion; 75. Literal preservation; 76. Type normalization; 77. Distribution interactions; 78. Non-distribution wrappers; 79. Union extraction; 80. Recursive extraction.

**81–90:** 81. Type parser foundations; 82. Function pipeline types; 83. Currying types; 84. Composition inference; 85. Builder extraction; 86. State extraction; 87. Schema-like inference; 88. Metadata extraction; 89. API response extraction; 90. Generic library utilities.

**91–100:** 91. Infer debugging; 92. Helper aliases; 93. Readability; 94. Excess recursion; 95. Compiler performance; 96. Ambiguous inference; 97. Fallback choices; 98. Type tests; 99. Real-world utility design; 100. Infer mastery.

### Quiz

1. ¿Dónde puede usarse infer? 2. ¿Qué hace? 3. ¿Cómo extraes return type? 4. ¿Cómo extraes parameters? 5. ¿Cómo extraes array element? 6. ¿Cómo extraes promise value? 7. ¿Cómo extraes tuple head? 8. ¿Cómo tail? 9. ¿Qué es variadic tuple inference? 10. ¿Qué es prefix inference?

2. ¿Qué es suffix inference? 12. ¿Puede haber varios infer? 13. ¿Cuál es su scope? 14. ¿Cómo implementar ReturnType? 15. ¿Cómo implementar Parameters? 16. ¿Qué particularidad tienen overloads? 17. ¿Qué signature suele influir en infer? 18. ¿Cómo extraer constructor instance? 19. ¿Qué es recursive Awaited? 20. ¿Qué es generic container extraction?

3. ¿Cómo extraer Box<T>? 22. ¿Qué es constrained infer? 23. ¿Por qué usar `infer S extends string`? 24. ¿Cómo combinar con template literals? 25. ¿Qué es route parameter extraction? 26. ¿Qué es recursive string parsing? 27. ¿Cómo infer interactúa con unions? 28. ¿Qué es distribution? 29. ¿Cómo detenerla? 30. ¿Qué es ambiguous inference?

4. ¿Qué es fallback? 32. ¿Por qué usar helper aliases? 33. ¿Qué riesgos tiene recursion? 34. ¿Qué es composition inference? 35. ¿Cómo currying usa infer? 36. ¿Qué es API response extraction? 37. ¿Qué es state extraction? 38. ¿Qué significa schema inference conceptualmente? 39. ¿Cómo probar utilities con infer? 40. Diseña una extracción propia.

### Examen

Construye 15 extractores de tipos, incluyendo parámetros, retorno, promise, arrays, tuples y patrones de strings.

### Proyecto

**Type Extraction Laboratory**.

### Dominio

Ser capaz de descomponer estructuras complejas exclusivamente a nivel de tipos.

---

# MÓDULO 24 — Template Literal Types

### 100 temas

**1–10:** 1. Template literal types; 2. String interpolation; 3. Literal unions; 4. Cross multiplication; 5. Generated strings; 6. Prefixes; 7. Suffixes; 8. Separators; 9. Namespaced strings; 10. Event names.

**11–20:** 11. `${T}`; 12. Generic strings; 13. Union interpolation; 14. Combinatorial unions; 15. Event systems; 16. CSS-like keys concept; 17. Locale keys; 18. Route patterns; 19. Command identifiers; 20. Resource names.

**21–30:** 21. `Uppercase`; 22. `Lowercase`; 23. `Capitalize`; 24. `Uncapitalize`; 25. Intrinsic string manipulation; 26. Naming transformations; 27. Getter names; 28. Setter names; 29. Event handler names; 30. Property methods.

**31–40:** 31. Template + mapped; 32. Key remapping; 33. `${Capitalize<K>}`; 34. Getter mapping; 35. Setter mapping; 36. Prefix mapping; 37. Suffix mapping; 38. Event mapping; 39. Async method naming; 40. API generation.

**41–50:** 41. Template + infer; 42. Pattern matching; 43. Prefix extraction; 44. Suffix extraction; 45. Split concept; 46. Join concept; 47. Replace concept; 48. Trim concept; 49. Recursive parsing; 50. Delimiter parsing.

**51–60:** 51. Route parameter parsing; 52. `/users/:id`; 53. Multiple parameters; 54. Optional segments concept; 55. Query patterns concept; 56. Event payload names; 57. Dot paths; 58. Nested paths; 59. Path parsing; 60. Property traversal.

**61–70:** 61. Dot-path generation; 62. Recursive object keys; 63. Leaf paths; 64. Nested path value; 65. Key constraints; 66. String keys only; 67. `string & keyof`; 68. Symbol exclusion; 69. Numeric keys; 70. Key conversion.

**71–80:** 71. String length impossibility/direct limitations; 72. Tuple-based helpers concept; 73. Parsing numbers concept; 74. Boolean strings; 75. Command grammar; 76. Mini DSLs; 77. SQL-like type strings concept; 78. Format strings; 79. Placeholder extraction; 80. Compile-time format validation.

**81–90:** 81. Combinatorial explosion; 82. Large union performance; 83. Ahead-of-time generation alternative; 84. Readability; 85. Error messages; 86. Scope limitation; 87. Keep types maintainable; 88. Document grammar; 89. Test grammar; 90. Type-level parser boundaries.

**91–100:** 91. Localization keys; 92. Event APIs; 93. Route APIs; 94. Property observers; 95. Configuration names; 96. Permission strings; 97. Branded string patterns; 98. Compile-time protocols; 99. DSL ergonomics; 100. Template literal mastery.

### Quiz

1. ¿Qué es template literal type? 2. ¿Cómo interpola union? 3. ¿Qué significa cross multiplication? 4. ¿Qué hace Uppercase? 5. ¿Lowercase? 6. ¿Capitalize? 7. ¿Uncapitalize? 8. ¿Cómo combinar con mapped type? 9. ¿Qué es key remapping? 10. ¿Cómo combinar con infer?

2. ¿Qué es pattern matching de strings? 12. ¿Cómo extraer prefix? 13. ¿Cómo extraer suffix? 14. ¿Cómo hacer Split conceptualmente? 15. ¿Cómo hacer Join? 16. ¿Cómo hacer Replace? 17. ¿Cómo hacer Trim? 18. ¿Qué es recursive parsing? 19. ¿Cómo extraer route params? 20. ¿Qué es dot path?

3. ¿Cómo generar nested paths? 22. ¿Cómo obtener value desde path? 23. ¿Por qué limitar a string keys? 24. ¿Qué ocurre con symbols? 25. ¿Qué es format validation? 26. ¿Qué es mini DSL? 27. ¿Qué es combinatorial explosion? 28. ¿Por qué puede afectar compilador? 29. ¿Cuándo generar strings anticipadamente? 30. ¿Qué significa type grammar?

4. ¿Por qué documentar grammar? 32. ¿Cómo probarla? 33. ¿Qué es event-name typing? 34. ¿Qué es permission-string typing? 35. ¿Cómo crear getters automáticamente? 36. ¿Cómo setters? 37. ¿Qué significa compile-time protocol? 38. ¿Qué limitaciones tiene TS para parsing? 39. ¿Cuándo abandonar type-level parser? 40. Diseña una DSL pequeña.

### Examen

Crea tipos capaces de convertir `/users/:userId/posts/:postId` en `{userId:string; postId:string}`.

### Proyecto

**Typed Route Grammar**.

### Dominio

Construir parsers de strings moderados sin provocar tipos inmanejables.

---

# MÓDULO 25 — Utility Types estándar y reconstrucción manual

### 100 temas

**1–10:** 1. Utility types; 2. `Partial`; 3. `Required`; 4. `Readonly`; 5. `Record`; 6. `Pick`; 7. `Omit`; 8. `Exclude`; 9. `Extract`; 10. `NonNullable`.

**11–20:** 11. `Parameters`; 12. `ConstructorParameters`; 13. `ReturnType`; 14. `InstanceType`; 15. `ThisParameterType`; 16. `OmitThisParameter`; 17. `ThisType`; 18. `Awaited`; 19. `NoInfer`; 20. Intrinsic string utilities.

**21–30:** 21. Manual Partial; 22. Manual Required; 23. Manual Readonly; 24. Manual Record; 25. Manual Pick; 26. Manual Omit; 27. Manual Exclude; 28. Manual Extract; 29. Manual NonNullable; 30. Manual ReturnType.

**31–40:** 31. Manual Parameters; 32. Manual ConstructorParameters; 33. Manual InstanceType; 34. Recursive Awaited; 35. This extraction; 36. Mapped foundations; 37. Conditional foundations; 38. Infer foundations; 39. Key remapping; 40. Utility composition.

**41–50:** 41. Partial update DTO; 42. Required configuration; 43. Readonly state; 44. Record dictionaries; 45. Pick public views; 46. Omit secrets; 47. Exclude union members; 48. Extract supported variants; 49. Non-null models; 50. Function introspection.

**51–60:** 51. Constructor introspection; 52. Awaited promises; 53. This utilities; 54. Function wrappers; 55. Generic APIs; 56. Configuration APIs; 57. Domain transformations; 58. State models; 59. DTO design; 60. View models.

**61–70:** 61. Utility nesting; 62. `Partial<Pick<...>>`; 63. Readability problems; 64. Named helpers; 65. Composition layers; 66. Utility order; 67. Semantic equivalence; 68. Optional property semantics; 69. Readonly shallowness; 70. Partial shallowness.

**71–80:** 71. Deep utilities not built-in; 72. DeepPartial; 73. DeepReadonly; 74. DeepRequired; 75. DeepNonNullable; 76. Array handling; 77. Function handling; 78. Tuple handling; 79. Built-in handling; 80. Recursive design.

**81–90:** 81. Utility abuse; 82. Huge compositions; 83. Leaking internal models; 84. Domain semantics loss; 85. Named intent; 86. API clarity; 87. Output stability; 88. Public contracts; 89. Versioning; 90. Structural compatibility.

**91–100:** 91. NoInfer use cases; 92. Inference source control; 93. ThisType use cases; 94. Contextual this; 95. Intrinsic manipulation; 96. Utility type testing; 97. Equality testing concepts; 98. Negative compilation tests; 99. Building utility library; 100. Utility mastery.

### Quiz

1. ¿Qué hace Partial? 2. ¿Required? 3. ¿Readonly? 4. ¿Record? 5. ¿Pick? 6. ¿Omit? 7. ¿Exclude? 8. ¿Extract? 9. ¿NonNullable? 10. ¿Parameters?

2. ¿ConstructorParameters? 12. ¿ReturnType? 13. ¿InstanceType? 14. ¿Awaited? 15. ¿NoInfer? 16. ¿ThisParameterType? 17. ¿OmitThisParameter? 18. ¿ThisType? 19. ¿Partial es profundo? 20. ¿Readonly es profundo?

3. ¿Cómo implementas Pick? 22. ¿Cómo Omit? 23. ¿Cómo Exclude? 24. ¿Cómo ReturnType? 25. ¿Qué herramientas requiere? 26. ¿Qué es utility composition? 27. ¿Qué problema presenta anidamiento excesivo? 28. ¿Qué es semantic helper? 29. ¿Qué es DeepPartial? 30. ¿Qué casos especiales necesita?

4. ¿Cómo tratar arrays? 32. ¿Cómo functions? 33. ¿Cómo tuples? 34. ¿Qué significa inference control? 35. ¿Por qué NoInfer? 36. ¿Qué son negative type tests? 37. ¿Por qué no exponer modelo interno con Omit arbitrario? 38. ¿Qué es public contract? 39. ¿Cómo versionar utilities? 40. Diseña tres utilities propios.

### Examen

Reimplementa 15 utility types sin utilizar los originales.

### Proyecto

**Standard Utility Reimplementation**.

### Dominio

Entender cómo funcionan los utilities, no simplemente memorizarlos.

---

# MÓDULO 26 — Recursive Types y Deep Utilities

### 100 temas

**1–10:** 1. Recursive aliases; 2. Recursive interfaces; 3. Trees; 4. Linked structures; 5. JSON-like values; 6. Nested categories; 7. Menu trees; 8. ASTs; 9. Recursive properties; 10. Base cases.

**11–20:** 11. Recursive mapped types; 12. DeepPartial; 13. DeepReadonly; 14. DeepRequired; 15. DeepNullable; 16. DeepNonNullable; 17. DeepMutable; 18. DeepPromise; 19. Deep transformations; 20. Leaf handling.

**21–30:** 21. Primitive base case; 22. Function base case; 23. Array branch; 24. Tuple branch; 25. Object branch; 26. Date-like concerns; 27. Map-like concerns; 28. Set-like concerns; 29. Promise-like concerns; 30. Built-in exclusions.

**31–40:** 31. Recursive conditional types; 32. Recursive tuple processing; 33. Head recursion; 34. Tail recursion concept; 35. Tuple accumulator; 36. Reverse tuple; 37. Flatten tuple; 38. Unique tuple concept; 39. Includes concept; 40. Length calculations.

**41–50:** 41. Nested array flatten; 42. Recursive Awaited; 43. Nested property paths; 44. Path generation; 45. Path values; 46. Dot path parsing; 47. Object traversal; 48. Recursive key collection; 49. Leaf key paths; 50. Branch key paths.

**51–60:** 51. Recursive string types; 52. Split; 53. Join; 54. Trim; 55. ReplaceAll concept; 56. String to tuple concept; 57. Delimited parsing; 58. Route parsing; 59. Path parsing; 60. Mini language parsing.

**61–70:** 61. Recursion termination; 62. Infinite recursion; 63. Compiler depth; 64. Instantiation limits; 65. Excessive depth errors; 66. Union expansion; 67. Performance profiling; 68. Simplification; 69. Intermediate helpers; 70. Recursion budgeting.

**71–80:** 71. Depth parameters; 72. Tuple counters; 73. Limited-depth utilities; 74. Decrement patterns; 75. Increment patterns; 76. Peano-like numbers concept; 77. Numeric computation limits; 78. Safe recursion; 79. Fallback at depth; 80. Practical limits.

**81–90:** 81. Cycle impossibility at type shape level nuances; 82. Recursive domain models; 83. Tree visitors typing; 84. Nested configuration; 85. Deep patch models; 86. Deep readonly configs; 87. Form models; 88. Error trees; 89. Translation trees; 90. Permission trees.

**91–100:** 91. Recursive utility testing; 92. Edge cases; 93. Empty object; 94. Never; 95. Unknown; 96. Any contamination; 97. Union recursion; 98. Readability; 99. Avoid cleverness; 100. Recursive type mastery.

### Quiz

1. ¿Qué es recursive type? 2. ¿Qué es base case? 3. ¿Cómo implementar DeepReadonly conceptualmente? 4. ¿Qué casos necesita? 5. ¿Por qué functions son especiales? 6. ¿Por qué arrays? 7. ¿Por qué tuples? 8. ¿Qué es recursive conditional? 9. ¿Qué es tuple recursion? 10. ¿Qué es accumulator?

2. ¿Cómo Reverse puede usar tuple recursion? 12. ¿Cómo Flatten? 13. ¿Qué es nested path generation? 14. ¿Qué es path value? 15. ¿Cómo se combinan template literals? 16. ¿Qué es recursive string parser? 17. ¿Qué significa termination? 18. ¿Qué ocurre sin base case? 19. ¿Qué son instantiation limits? 20. ¿Qué es excessive depth error?

3. ¿Qué es recursion budgeting? 22. ¿Qué es depth parameter? 23. ¿Cómo representar contador mediante tuple? 24. ¿Qué son practical limits? 25. ¿Por qué no resolver todo a nivel de tipos? 26. ¿Qué es deep patch? 27. ¿Qué es error tree? 28. ¿Qué es union recursion? 29. ¿Qué riesgo tiene any? 30. ¿Qué ocurre con never?

4. ¿Qué es recursive JSON model? 32. ¿Cómo modelar tree? 33. ¿Cómo modelar linked node? 34. ¿Qué es AST? 35. ¿Por qué TypeScript puede modelarlo? 36. ¿Qué significa leaf? 37. ¿Qué significa branch? 38. ¿Cómo mejorar readability? 39. ¿Cuándo detener cleverness? 40. Diseña DeepUtility segura.

### Examen

Implementa `DeepReadonly`, `DeepPartial`, `DeepRequired`, `DeepMutable`, `Flatten`, `Reverse`, `Paths` y `PathValue`.

### Proyecto

**Recursive Type Algorithms**.

### Dominio

Resolver recursiones moderadas comprendiendo sus límites de compilación.

---

# MÓDULO 27 — Branded Types, nominal typing y dominio seguro

### 100 temas

**1–10:** 1. Structural typing recap; 2. Nominal typing contrast; 3. Same-shape problem; 4. UserId vs ProductId; 5. Currency units; 6. Measurement units; 7. Validated strings; 8. Domain identity; 9. Brand pattern; 10. Phantom brands.

**11–20:** 11. Intersection brands; 12. `string & Brand`; 13. Unique symbol brands; 14. Private property branding; 15. Opaque-like types; 16. Creation functions; 17. Validation constructors; 18. Unsafe assertions; 19. Trusted constructors; 20. Smart constructors.

**21–30:** 21. Email brand; 22. URL brand; 23. UUID brand; 24. Positive number brand; 25. Integer brand; 26. Percentage brand; 27. Currency brand; 28. Unit brands; 29. Sanitized string brand; 30. NonEmptyString brand.

**31–40:** 31. Runtime validation; 32. Compile-time distinction; 33. Boundary conversion; 34. Serialization; 35. Deserialization; 36. Brand loss; 37. Revalidation; 38. Database-like boundaries conceptual; 39. Network boundaries conceptual; 40. Storage boundaries conceptual.

**41–50:** 41. Brand factories; 42. Result-returning factories; 43. Throwing factories; 44. Predicate factories; 45. Assertion factories; 46. Generic Brand utility; 47. Brand symbol; 48. Brand naming; 49. Multiple brands; 50. Composite brands.

**51–60:** 51. Units of measure; 52. Meters vs feet; 53. Celsius vs Fahrenheit; 54. Milliseconds vs seconds; 55. Dollars vs pesos; 56. Addition constraints; 57. Conversion functions; 58. Arithmetic brand loss; 59. Restoring brands; 60. Safe operations.

**61–70:** 61. State brands; 62. Validated entities; 63. Parsed entities; 64. Sanitized values; 65. Authorized values concept; 66. Domain pipelines; 67. Illegal transitions; 68. Smart constructors; 69. Invariant preservation; 70. Domain-driven types.

**71–80:** 71. Opaque API boundaries; 72. Exporting constructors only; 73. Hiding brand representation; 74. Module encapsulation; 75. Library consumers; 76. Declaration exposure; 77. Forging types; 78. Assertions defeat safety; 79. Trust model; 80. Documentation.

**81–90:** 81. Branded generics; 82. Generic IDs; 83. Entity ID mapping; 84. Brand keys; 85. Template brands; 86. Literal brands; 87. Readonly brands; 88. Intersections; 89. Conditional brand extraction; 90. Underlying type extraction.

**91–100:** 91. Branding tradeoffs; 92. Ergonomics cost; 93. Error messages; 94. Serialization cost; 95. Structural ecosystem; 96. When branding matters; 97. When it is overkill; 98. Domain safety; 99. API design; 100. Nominal-pattern mastery.

### Quiz

1. ¿Qué es structural typing? 2. ¿Qué problema crea para IDs iguales? 3. ¿Qué es branded type? 4. ¿Es nominal typing verdadero? 5. ¿Qué es phantom property? 6. ¿Por qué unique symbol? 7. ¿Qué es smart constructor? 8. ¿Por qué debe validar? 9. ¿Qué es brand forging? 10. ¿Cómo assertions rompen seguridad?

2. ¿Cómo modelar UserId? 12. ¿Cómo ProductId? 13. ¿Cómo evitar mezclarlos? 14. ¿Qué es opaque-like API? 15. ¿Cómo esconder construcción? 16. ¿Qué ocurre al serializar? 17. ¿Se conserva el brand runtime? 18. ¿Qué debes hacer al deserializar? 19. ¿Qué es revalidation? 20. ¿Qué es boundary conversion?

3. ¿Cómo modelar unidades? 22. ¿Por qué arithmetic puede perder brand? 23. ¿Cómo crear safe operations? 24. ¿Qué es invariant? 25. ¿Qué es domain pipeline? 26. ¿Cómo brand indica validated state? 27. ¿Qué es sanitization brand? 28. ¿Qué es NonEmptyString? 29. ¿Cómo crearlo? 30. ¿Qué es generic Brand?

4. ¿Cómo extraer underlying type? 32. ¿Qué tradeoff tienen brands? 33. ¿Qué problema de ergonomics? 34. ¿Cuándo son excesivos? 35. ¿Cuándo son valiosos? 36. ¿Cómo documentarlos? 37. ¿Qué significa trusted constructor? 38. ¿Qué diferencia tiene un predicate constructor? 39. ¿Qué es composite brand? 40. Diseña cinco brands de dominio.

### Examen

Diseña un sistema financiero donde sea imposible confundir AccountId, TransactionId, MXN, USD, Percentage y PositiveAmount.

### Proyecto

**Nominal Domain Safety Toolkit**.

### Dominio

Impedir errores semánticos que structural typing por sí solo no detectaría.

---

# MÓDULO 28 — Discriminated Unions y máquinas de estados Type-Safe

### 100 temas

**1–10:** 1. Tagged unions; 2. Discriminant property; 3. Literal tags; 4. Variant objects; 5. Narrowing; 6. Exhaustiveness; 7. `never`; 8. Switch; 9. If branches; 10. Pattern design.

**11–20:** 11. Result types; 12. Success; 13. Failure; 14. Error variants; 15. Loading states; 16. Idle state; 17. Pending state; 18. Success state; 19. Error state; 20. Cancelled state.

**21–30:** 21. Impossible state prevention; 22. Boolean flag problems; 23. Optional-property problems; 24. State-specific data; 25. State-specific operations; 26. Transition modeling; 27. Event unions; 28. Command unions; 29. Message unions; 30. Reducer-like functions.

**31–40:** 31. Finite state machines; 32. States; 33. Events; 34. Transition function; 35. Initial state; 36. Final states; 37. Invalid transitions; 38. Compile-time transition restrictions; 39. Runtime transition checking; 40. State graphs.

**41–50:** 41. Generic State; 42. Generic Event; 43. Event maps; 44. State maps; 45. Correlated state/event; 46. Conditional transition types; 47. Generic reducer; 48. Exhaustive reducer; 49. Action payloads; 50. Payload correlation.

**51–60:** 51. AST modeling; 52. Expression nodes; 53. Statement nodes; 54. Recursive unions; 55. Visitor functions; 56. Exhaustive visitors; 57. Evaluators; 58. Printers; 59. Transformers; 60. Tree walking.

**61–70:** 61. Domain events; 62. Order workflow; 63. Payment workflow; 64. Authentication workflow; 65. Document workflow; 66. Job workflow; 67. Approval workflow; 68. Connection state; 69. Resource lifecycle; 70. Retry states.

**71–80:** 71. Nested state machines; 72. Hierarchical states; 73. Parallel state concept; 74. History concept; 75. Type complexity; 76. State normalization; 77. Event names; 78. Event payload maps; 79. State payload maps; 80. Transition tables.

**81–90:** 81. Builder for machine; 82. Generic transition table; 83. `satisfies` transition config; 84. Literal preservation; 85. Deriving states; 86. Deriving events; 87. Deriving transitions; 88. Valid event per state; 89. Next-state inference; 90. Type-safe dispatch.

**91–100:** 91. Exhaustiveness helpers; 92. Future variants; 93. Versioning unions; 94. Open vs closed unions; 95. Library extensibility; 96. Error handling; 97. Testing state machines; 98. Property-based concepts; 99. Domain correctness; 100. State modeling mastery.

### Quiz

1. ¿Qué es discriminated union? 2. ¿Qué es discriminant? 3. ¿Por qué literal? 4. ¿Cómo narrowing funciona? 5. ¿Qué es exhaustiveness? 6. ¿Cómo never ayuda? 7. ¿Por qué múltiples booleans pueden ser malos? 8. ¿Qué es state-specific data? 9. ¿Qué es finite state machine? 10. ¿Qué es transition?

2. ¿Qué es invalid transition? 12. ¿Cómo intentar prevenirla estáticamente? 13. ¿Qué es event union? 14. ¿Qué es command union? 15. ¿Qué es reducer? 16. ¿Cómo correlacionar payload? 17. ¿Qué es AST? 18. ¿Por qué discriminated union sirve para AST? 19. ¿Qué es visitor? 20. ¿Cómo hacerlo exhaustivo?

3. ¿Qué es domain event? 22. ¿Qué es workflow? 23. ¿Qué es transition table? 24. ¿Por qué usar satisfies? 25. ¿Cómo derivar state names? 26. ¿Cómo event names? 27. ¿Cómo limitar events por state? 28. ¿Qué significa next-state inference? 29. ¿Qué es type-safe dispatch? 30. ¿Qué es open union?

4. ¿Qué es closed union? 32. ¿Qué impacto tiene añadir variant? 33. ¿Cómo ayuda compiler? 34. ¿Qué es nested machine? 35. ¿Qué es hierarchical state? 36. ¿Qué riesgo tiene type complexity? 37. ¿Cómo normalizar? 38. ¿Qué es exhaustive helper? 39. ¿Cómo testear transiciones? 40. Diseña una máquina de pedido.

### Examen

Construye una máquina de estados tipada para el ciclo completo de una compra con al menos ocho estados y doce eventos.

### Proyecto

**Compile-Time State Machine**.

### Dominio

Representar workflows donde una gran parte de estados y transiciones incorrectos no compile.

---

# MÓDULO 29 — Type Compatibility, variance y assignability avanzada

### 100 temas

**Qué aprenderás:** comprenderás las reglas profundas mediante las que TypeScript decide si un valor puede asignarse a otro tipo.
**Por qué:** es esencial para interpretar errores complejos con genéricos, funciones y librerías.
**Al finalizar:** podrás razonar sobre compatibilidad sin experimentar a ciegas.

**1–10:** 1. Assignability; 2. Type compatibility; 3. Structural typing; 4. Shape comparison; 5. Extra members; 6. Missing members; 7. Object compatibility; 8. Freshness; 9. Excess property checks; 10. Variable assignments.

**11–20:** 11. Function compatibility; 12. Parameter counts; 13. Discarding parameters; 14. Return compatibility; 15. Parameter types; 16. strictFunctionTypes; 17. Method exceptions; 18. Callback compatibility; 19. Void return behavior; 20. Overload compatibility.

**21–30:** 21. Class compatibility; 22. Static side ignored for instances; 23. Constructors; 24. Private members; 25. Protected members; 26. Origin requirements; 27. Subclasses; 28. Structural instances; 29. Nominal-like effects; 30. Generic classes.

**31–40:** 31. Generic compatibility; 32. Used type parameters; 33. Unused parameters; 34. Phantom positions; 35. Instantiations; 36. Variance concept; 37. Covariance; 38. Contravariance; 39. Invariance; 40. Bivariance.

**41–50:** 41. Producers; 42. Consumers; 43. Producer `T`; 44. Consumer `T`; 45. Input positions; 46. Output positions; 47. Mixed positions; 48. Mutable containers; 49. Readonly containers; 50. Soundness tradeoffs.

**51–60:** 51. Array covariance concerns; 52. Readonly arrays; 53. Function contravariance; 54. Methods bivariance context; 55. Event-handler patterns; 56. Listener safety; 57. Callback APIs; 58. Generic containers; 59. Variance annotations/concepts; 60. Compiler inference.

**61–70:** 61. Union assignability; 62. Intersection assignability; 63. Literal assignability; 64. Widening; 65. Narrowing; 66. Any assignability; 67. Unknown assignability; 68. Never assignability; 69. Void relationships; 70. Nullish relationships.

**71–80:** 71. Enum compatibility considerations; 72. Branded intersections; 73. Unique symbols; 74. Tuples; 75. Readonly tuples; 76. Optional elements; 77. Rest elements; 78. Function tuples; 79. Constructor signatures; 80. Abstract constructors.

**81–90:** 81. Conditional assignability; 82. Generic deferred evaluation; 83. Distributive effects; 84. Mapped modifier compatibility; 85. Optional exactness; 86. Readonly structural behavior; 87. Index signatures; 88. Record compatibility; 89. Key domains; 90. Symbol keys.

**91–100:** 91. Reading complex errors; 92. Source type; 93. Target type; 94. Property path errors; 95. Generic instantiation errors; 96. Simplifying reproductions; 97. Compatibility debugging; 98. Designing safe APIs; 99. Soundness awareness; 100. Assignability mastery.

### Quiz

1. ¿Qué es assignability? 2. ¿Qué significa structural typing? 3. ¿Puede objeto con propiedades extra asignarse normalmente? 4. ¿Qué cambia fresh literal? 5. ¿Qué es excess property check? 6. ¿Cómo se comparan funciones? 7. ¿Puede función aceptar menos parámetros? 8. ¿Por qué callbacks? 9. ¿Cómo se comparan retornos? 10. ¿Qué hace strictFunctionTypes?

2. ¿Qué es covariance? 12. ¿Qué es contravariance? 13. ¿Qué es invariance? 14. ¿Qué es bivariance? 15. ¿Qué es producer? 16. ¿Qué es consumer? 17. ¿Qué ocurre si T aparece en entrada y salida? 18. ¿Por qué mutable container complica covariance? 19. ¿Por qué readonly ayuda? 20. ¿Cómo private members afectan clases?

3. ¿Por qué dan efecto nominal? 22. ¿Qué pasa con unused generic parameter? 23. ¿Qué es phantom position? 24. ¿Cómo unions se asignan? 25. ¿Cómo never se asigna? 26. ¿Cómo unknown se asigna? 27. ¿Cómo any afecta garantías? 28. ¿Qué ocurre con literals? 29. ¿Qué es source type? 30. ¿Qué es target type?

4. ¿Cómo leer error anidado? 32. ¿Qué es minimal reproduction? 33. ¿Qué son index signatures? 34. ¿Cómo afectan compatibilidad? 35. ¿Qué cambia exactOptionalPropertyTypes? 36. ¿Readonly garantiza runtime immutability? 37. ¿Cómo tuples se comparan? 38. ¿Qué hace rest element? 39. ¿Por qué entender variance importa para APIs? 40. Explica un ejemplo producer/consumer.

### Examen

Implementa una colección de productores, consumidores y transformadores genéricos y demuestra mediante pruebas de compilación qué asignaciones son seguras.

### Proyecto

**Type Compatibility Laboratory**.

### Dominio

Poder leer un error complejo de assignability y explicar exactamente qué relación falló.

---

# MÓDULO 30 — Modules, namespaces y organización TypeScript

Los módulos modernos aíslan su propio scope; valores y tipos deben exportarse explícitamente para ser utilizados desde otros módulos. La documentación actual recomienda módulos frente a namespaces para código moderno. ([TypeScript][4])

### Qué aprenderás

Comprenderás profundamente módulos TypeScript/ECMAScript, imports, exports, type-only imports, barrels, namespaces y separación entre espacios de nombres de valores y tipos.

### Por qué

Los proyectos grandes dependen de límites modulares correctos. Una arquitectura mal modularizada produce dependencias circulares, APIs internas expuestas y problemas de compilación.

### Al finalizar podrás

Diseñar una codebase TypeScript modular sin depender todavía de React, Node u otro framework.

### 100 temas

**1–10:** 1. Qué es un módulo; 2. Qué es un script; 3. Module scope; 4. Global scope; 5. `export`; 6. `import`; 7. Named exports; 8. Default exports; 9. Re-exports; 10. Aliased imports.

**11–20:** 11. Aliased exports; 12. Export lists; 13. Import lists; 14. Namespace imports; 15. `import * as`; 16. Side-effect imports; 17. Dynamic imports concept; 18. Type-only imports; 19. `import type`; 20. Type-only exports.

**21–30:** 21. Value space; 22. Type space; 23. Dual-space declarations; 24. Classes in both spaces; 25. Enums in both spaces; 26. Interfaces type-only; 27. Type aliases type-only; 28. Functions value-only; 29. Import elision; 30. Emit considerations.

**31–40:** 31. `verbatimModuleSyntax`; 32. Preserving syntax; 33. Runtime imports; 34. Compile-time imports; 35. Accidental runtime dependencies; 36. Circular imports; 37. Circular type dependencies; 38. Dependency graph; 39. Module boundaries; 40. Public API.

**41–50:** 41. Barrel files; 42. `index.ts`; 43. Re-export APIs; 44. Barrel benefits; 45. Barrel risks; 46. Circular dependency risks; 47. Tree visibility conceptual; 48. Internal modules; 49. Public modules; 50. Encapsulation.

**51–60:** 51. Relative imports; 52. Non-relative imports; 53. File extensions conceptual; 54. Runtime resolution; 55. Compiler resolution; 56. Package boundaries; 57. Module specifiers; 58. Resolution debugging; 59. `traceResolution`; 60. Resolved files.

**61–70:** 61. Namespaces; 62. Namespace declarations; 63. Namespace exports; 64. Nested namespaces; 65. Namespace merging; 66. Historical internal modules; 67. Modules vs namespaces; 68. Modern guidance; 69. Global scripts; 70. Legacy integration.

**71–80:** 71. Declaration merging; 72. Interface merging; 73. Namespace merging; 74. Namespace + class; 75. Namespace + function; 76. Namespace + enum; 77. Augmentation concept; 78. Module augmentation preview; 79. Global augmentation preview; 80. Risks of augmentation.

**81–90:** 81. Dependency direction; 82. Layered modules; 83. Feature modules; 84. Domain modules; 85. Shared modules; 86. Circular dependency prevention; 87. Stable abstractions; 88. Public contracts; 89. Internal details; 90. API surface minimization.

**91–100:** 91. Module naming; 92. File naming; 93. Export discipline; 94. Default vs named decision; 95. Refactoring modules; 96. Moving types safely; 97. Splitting modules; 98. Dependency auditing; 99. Large-project organization; 100. Module architecture mastery.

### Quiz — 40 preguntas

1. ¿Qué convierte un archivo en módulo? 2. ¿Qué significa module scope? 3. ¿Qué ocurre en un script sin imports/exports? 4. ¿Qué es named export? 5. ¿Qué es default export? 6. ¿Qué es re-export? 7. ¿Qué hace namespace import? 8. ¿Qué es side-effect import? 9. ¿Qué es `import type`? 10. ¿Por qué existe?

2. ¿Qué es value space? 12. ¿Qué es type space? 13. ¿Una interface existe en runtime? 14. ¿Una class existe en ambos espacios? 15. ¿Un enum? 16. ¿Qué es import elision? 17. ¿Qué hace verbatimModuleSyntax conceptualmente? 18. ¿Qué es runtime dependency? 19. ¿Qué es circular dependency? 20. ¿Puede existir circular type dependency?

3. ¿Qué es barrel? 22. ¿Qué ventaja aporta? 23. ¿Qué riesgos tiene? 24. ¿Qué es relative import? 25. ¿Qué es module specifier? 26. ¿Qué diferencia hay entre runtime y compiler resolution? 27. ¿Para qué sirve traceResolution? 28. ¿Qué es namespace? 29. ¿Por qué se prefieren módulos modernos? 30. ¿Qué es declaration merging?

4. ¿Qué tipos de declaraciones pueden combinarse? 32. ¿Qué es module augmentation? 33. ¿Qué es global augmentation? 34. ¿Qué riesgos implican? 35. ¿Qué significa dependency direction? 36. ¿Qué es public API surface? 37. ¿Por qué minimizarla? 38. ¿Cómo prevenir cycles? 39. ¿Cuándo usar named exports? 40. Diseña una arquitectura modular para una librería.

### Examen práctico

Construye una librería TypeScript dividida en al menos:

```text
src/
├── domain/
├── models/
├── contracts/
├── errors/
├── utilities/
├── validation/
├── events/
├── commands/
├── internal/
└── index.ts
```

Requisitos:

* mínimo 25 archivos `.ts`;
* imports y exports correctamente delimitados;
* `import type` donde corresponda;
* ninguna dependencia circular;
* API pública controlada desde `index.ts`;
* implementación interna no exportada;
* al menos cinco módulos con tipos genéricos;
* unions discriminadas;
* type guards;
* utilities;
* branded types;
* `strict` activado;
* cero `any`.

### Proyecto final del módulo

## **TypeScript Modular Core Library**

Construirás una librería modular que reúna los conocimientos de los primeros 30 módulos sin utilizar React, Node.js frameworks ni otras tecnologías que distraigan del lenguaje.

 Verifiqué la continuación contra la documentación oficial actual de TypeScript. En particular, **Project References** sigue siendo la herramienta oficial para dividir proyectos grandes y trabajar con `tsc --build`, mientras que la documentación del Compiler API advierte actualmente que la API cambia de forma importante con la transición a TypeScript 7.1; por eso los módulos de internals y tooling están planteados para enseñar arquitectura y conceptos duraderos, no APIs congeladas. ([TypeScript][1])

El siguiente bloque está preparado para que lo pegues directamente después del Módulo 30 de tu `README.md`.

# PARTE V — MÓDULOS, DECLARACIONES Y ARQUITECTURA DE PROYECTOS TYPESCRIPT

# MÓDULO 31 — Module Resolution avanzado

### Qué aprenderás

Comprenderás cómo TypeScript localiza archivos, paquetes, declaraciones de tipos y módulos durante el proceso de compilación.

### Por qué debes aprenderlo

Muchos errores aparentemente relacionados con imports, paquetes o typings son realmente problemas de resolución de módulos.

### Al finalizar podrás

Diagnosticar problemas complejos de imports y configurar correctamente proyectos con diferentes estrategias de resolución.

### 100 temas

**1–10:** 1. Module resolution; 2. Module specifier; 3. Relative imports; 4. Bare imports; 5. Package imports; 6. File resolution; 7. Directory resolution; 8. Extension substitution; 9. Runtime resolution; 10. TypeScript resolution.

**11–20:** 11. `module`; 12. `moduleResolution`; 13. Node-style resolution; 14. Bundler-style resolution; 15. Node16 concepts; 16. NodeNext concepts; 17. Classic resolution histórica; 18. ES module resolution; 19. CommonJS resolution; 20. Resolver selection.

**21–30:** 21. `.ts` resolution; 22. `.tsx` resolution; 23. `.d.ts` resolution; 24. `.js` resolution; 25. `.jsx` resolution; 26. JSON modules; 27. Declaration preference; 28. Source substitution; 29. Type lookup; 30. Runtime correspondence.

**31–40:** 31. Package resolution; 32. `package.json`; 33. `types`; 34. `typings`; 35. `main`; 36. `exports`; 37. `imports`; 38. Conditional exports; 39. Package subpaths; 40. Package encapsulation.

**41–50:** 41. `typesVersions`; 42. Version-dependent typings; 43. Package conditions; 44. Type conditions; 45. Import conditions; 46. Require conditions; 47. Default conditions; 48. Resolution priorities; 49. Fallback resolution; 50. Package boundary diagnostics.

**51–60:** 51. Path mapping; 52. `baseUrl`; 53. `paths`; 54. Path aliases; 55. Wildcard mappings; 56. Multiple targets; 57. Path alias misconceptions; 58. Runtime alias mismatch; 59. Alias portability; 60. Alias debugging.

**61–70:** 61. `rootDirs`; 62. Virtual directories; 63. Generated declarations; 64. Generated sources; 65. Layered source trees; 66. Relative path virtualization; 67. Source/declaration pairing; 68. Build output mapping; 69. Generated code integration; 70. Resolution architecture.

**71–80:** 71. `typeRoots`; 72. `types`; 73. Automatic type inclusion; 74. `@types`; 75. Ambient packages; 76. Global declarations; 77. Package typings; 78. Type package conflicts; 79. Explicit type selection; 80. Typing isolation.

**81–90:** 81. `resolveJsonModule`; 82. `allowImportingTsExtensions`; 83. Extension-aware imports; 84. Explicit extensions; 85. ESM compatibility; 86. Declaration resolution; 87. `verbatimModuleSyntax`; 88. Type-only imports; 89. Runtime-safe imports; 90. Import portability.

**91–100:** 91. `--traceResolution`; 92. Reading resolution traces; 93. Failed lookup locations; 94. Successful resolution; 95. Cache behavior concept; 96. Dependency graphs; 97. Circular resolution; 98. Minimal reproductions; 99. Module debugging workflow; 100. Resolution mastery.

### Quiz — 40 preguntas

1. ¿Qué es module resolution? 2. ¿Qué es module specifier? 3. ¿Qué diferencia hay entre import relativo y bare import? 4. ¿Qué hace `moduleResolution`? 5. ¿Qué relación tiene con el runtime? 6. ¿Qué significa extension substitution? 7. ¿Qué archivo puede proporcionar solamente tipos? 8. ¿Qué papel tiene `.d.ts`? 9. ¿Qué información aporta `package.json`? 10. ¿Qué hace el campo `types`?

2. ¿Qué es `exports`? 12. ¿Qué son conditional exports? 13. ¿Qué son package subpaths? 14. ¿Qué hace `typesVersions`? 15. ¿Qué problema resuelve? 16. ¿Qué hace `baseUrl`? 17. ¿Qué hace `paths`? 18. ¿`paths` modifica automáticamente el runtime? 19. ¿Por qué es importante saberlo? 20. ¿Qué hace `rootDirs`?

3. ¿Qué son `typeRoots`? 22. ¿Qué hace `types` en `tsconfig`? 23. ¿Qué es automatic type inclusion? 24. ¿Qué es `@types`? 25. ¿Qué hace `resolveJsonModule`? 26. ¿Qué problema pueden producir extensiones incorrectas? 27. ¿Qué papel tiene `verbatimModuleSyntax`? 28. ¿Por qué usar `import type`? 29. ¿Qué es runtime-safe import? 30. ¿Qué es package encapsulation?

4. ¿Para qué sirve `traceResolution`? 32. ¿Qué es failed lookup location? 33. ¿Qué es successful resolution? 34. ¿Qué es dependency graph? 35. ¿Cómo detectarías una resolución inesperada? 36. ¿Qué diferencia existe entre module y moduleResolution? 37. ¿Por qué no conviene copiar `paths` sin entenderlos? 38. ¿Qué es una condición de paquete? 39. ¿Qué significa fallback resolution? 40. Explica el proceso completo de resolución de un import.

### Examen práctico

Construye un proyecto con varios paquetes simulados, aliases, subpath exports y declaraciones `.d.ts`. Provoca al menos diez errores distintos de resolución y documenta cómo diagnosticar cada uno mediante `--traceResolution`.

### Proyecto del módulo

## **Module Resolution Laboratory**

Crea una codebase diseñada específicamente para demostrar distintas estrategias de resolución, paquetes internos, aliases y resolución de tipos.

### Criterio de dominio

Debes poder determinar **exactamente qué archivo está resolviendo TypeScript para cada import y por qué**.

---

# MÓDULO 32 — Declaration Files `.d.ts` desde cero hasta experto

### Qué aprenderás

Aprenderás a describir con tipos bibliotecas y APIs cuyo código JavaScript ya existe.

### Por qué debes aprenderlo

Los declaration files son uno de los mecanismos fundamentales que permiten a TypeScript trabajar con el ecosistema JavaScript.

### Al finalizar podrás

Crear archivos `.d.ts` profesionales, tipar librerías existentes y comprender typings de terceros.

### 100 temas

**1–10:** 1. Qué es `.d.ts`; 2. Declaration files; 3. Runtime vs declarations; 4. Ambient declarations; 5. `declare`; 6. Type-only description; 7. No emit runtime; 8. Existing JavaScript; 9. API surface description; 10. Declaration consumption.

**11–20:** 11. `declare const`; 12. `declare let`; 13. `declare var`; 14. `declare function`; 15. `declare class`; 16. `declare enum`; 17. `declare namespace`; 18. `declare module`; 19. Interfaces en declarations; 20. Type aliases en declarations.

**21–30:** 21. Function overload declarations; 22. Optional parameters; 23. Rest parameters; 24. Generic declarations; 25. Generic constraints; 26. Callable interfaces; 27. Construct signatures; 28. Static members; 29. Instance members; 30. Declaration contracts.

**31–40:** 31. Global libraries; 32. Global declarations; 33. Script libraries; 34. Module libraries; 35. UMD libraries; 36. Global-modifying modules; 37. Module plugins; 38. Library structures; 39. Identifying library shape; 40. Declaration templates.

**41–50:** 41. `export =`; 42. `export as namespace`; 43. Default export declarations; 44. Named exports; 45. Re-exports; 46. Namespace exports; 47. CommonJS-style declarations; 48. ES module declarations; 49. Interop declarations; 50. Consumer syntax.

**51–60:** 51. Module declarations; 52. Ambient modules; 53. Wildcard modules; 54. Non-code imports; 55. Asset declarations concept; 56. Virtual modules; 57. Generated modules; 58. Module patterns; 59. Module specifier matching; 60. Declaration resolution.

**61–70:** 61. Global interfaces; 62. `Window` augmentation concept; 63. Global variables; 64. Global functions; 65. Global namespaces; 66. Global pollution; 67. Naming collisions; 68. Safe globals; 69. `globalThis`; 70. Global type design.

**71–80:** 71. Declaration emit; 72. Generated `.d.ts`; 73. Handwritten `.d.ts`; 74. Source declarations; 75. Public API leakage; 76. Private types leaking; 77. Declaration portability; 78. Declaration readability; 79. Stable declarations; 80. Consumer-facing types.

**81–90:** 81. `@types` packages; 82. DefinitelyTyped concept; 83. Package declaration structure; 84. Root declarations; 85. Dependency declarations; 86. Triple-slash references; 87. Type dependencies; 88. Global dependencies; 89. Module dependencies; 90. Version compatibility.

**91–100:** 91. Declaration testing; 92. Consumer fixtures; 93. Positive tests; 94. Negative tests; 95. `skipLibCheck` caveats; 96. Duplicate declarations; 97. Incompatible declarations; 98. Declaration debugging; 99. Declaration maintainability; 100. `.d.ts` mastery.

### Quiz — 40 preguntas

1. ¿Qué contiene un `.d.ts`? 2. ¿Genera JavaScript? 3. ¿Qué significa ambient declaration? 4. ¿Qué hace `declare`? 5. ¿Cuándo usar `declare function`? 6. ¿Qué diferencia hay entre implementación y declaración? 7. ¿Puede haber generics en `.d.ts`? 8. ¿Pueden existir overloads? 9. ¿Qué es global library? 10. ¿Qué es module library?

2. ¿Qué es UMD? 12. ¿Qué es global-modifying module? 13. ¿Qué hace `export =`? 14. ¿Qué hace `export as namespace`? 15. ¿Qué es ambient module? 16. ¿Qué es wildcard module? 17. ¿Cómo tiparías un tipo de archivo importado? 18. ¿Qué riesgo tienen globals? 19. ¿Qué es global pollution? 20. ¿Qué es declaration emit?

3. ¿Qué diferencia existe entre `.d.ts` generado y escrito manualmente? 22. ¿Qué es API leakage? 23. ¿Por qué las declaraciones deben ser portables? 24. ¿Qué es DefinitelyTyped? 25. ¿Qué es un paquete `@types`? 26. ¿Qué son triple-slash references? 27. ¿Cuándo se usan? 28. ¿Qué hace skipLibCheck? 29. ¿Por qué no soluciona declaraciones incorrectas? 30. ¿Qué es consumer fixture?

4. ¿Qué es positive type test? 32. ¿Qué es negative type test? 33. ¿Cómo se prueba una declaration? 34. ¿Qué diferencia hay entre named/default exports en `.d.ts`? 35. ¿Qué es library structure? 36. ¿Por qué primero debes conocer el runtime API? 37. ¿Puede un declaration file inventar comportamiento inexistente? 38. ¿Qué problema produciría? 39. ¿Qué significa consumer-facing type? 40. Diseña conceptualmente un `.d.ts` para una librería JavaScript.

### Examen práctico

Recibe una librería ficticia escrita únicamente en JavaScript y crea sus declarations completas sin modificar el runtime.

### Proyecto del módulo

## **JavaScript Library Typings**

Crea typings profesionales para una librería de utilidades con funciones, clases, eventos, callbacks, configuración y plugins.

### Criterio de dominio

Debes poder utilizar una librería JavaScript desconocida y construir su superficie TypeScript sin recurrir a `any`.

---

# MÓDULO 33 — Diseño y publicación profesional de tipos para librerías

### Qué aprenderás

Diseñarás superficies públicas TypeScript estables y consumibles.

### Por qué debes aprenderlo

Escribir código TypeScript para una aplicación y diseñar tipos para miles de consumidores son problemas diferentes.

### Al finalizar podrás

Diseñar librerías TypeScript con APIs públicas limpias y declarations mantenibles.

### 100 temas

**1–10:** 1. Library API design; 2. Public surface; 3. Internal surface; 4. Export discipline; 5. Stable contracts; 6. Semantic types; 7. Consumer ergonomics; 8. Inference ergonomics; 9. Error ergonomics; 10. API discoverability.

**11–20:** 11. Declaration emit; 12. `declaration`; 13. `emitDeclarationOnly`; 14. `declarationMap`; 15. Source declarations; 16. Public dependencies; 17. Internal dependencies; 18. Type leakage; 19. Private-name errors; 20. Portable declarations.

**21–30:** 21. Exported interfaces; 22. Exported aliases; 23. Exported classes; 24. Exported functions; 25. Generic APIs; 26. Generic defaults; 27. Constraint stability; 28. Literal unions; 29. Extensible contracts; 30. Closed contracts.

**31–40:** 31. Named exports; 32. Default exports; 33. Entry points; 34. Subpath APIs; 35. Public modules; 36. Internal modules; 37. Barrel architecture; 38. Export collisions; 39. Re-export stability; 40. API namespaces.

**41–50:** 41. Type-only exports; 42. Runtime exports; 43. Dual exports; 44. Class duality; 45. Enum runtime concerns; 46. Const objects; 47. Tree-shape concepts; 48. Type consumers; 49. JavaScript consumers; 50. Cross-language usability.

**51–60:** 51. Breaking type changes; 52. Source compatibility; 53. Consumer compatibility; 54. Generic breaking changes; 55. Union expansion; 56. Union narrowing; 57. Property addition; 58. Required property addition; 59. Function parameter changes; 60. Return-type changes.

**61–70:** 61. Overload evolution; 62. Deprecation; 63. `@deprecated`; 64. Migration signatures; 65. Alias migrations; 66. Backwards compatibility; 67. Compatibility testing; 68. Consumer matrices; 69. Versioned declarations; 70. Type evolution.

**71–80:** 71. `typesVersions`; 72. Multiple TS versions concept; 73. Syntax compatibility; 74. Feature compatibility; 75. Downlevel declaration concerns; 76. Minimum supported TypeScript; 77. Compiler-version testing; 78. Stable feature selection; 79. Documentation versioning; 80. Release discipline.

**81–90:** 81. Package declarations; 82. Declaration entry points; 83. Package metadata concepts; 84. `types`; 85. Conditional type entry points; 86. Export maps; 87. Subpath types; 88. Declaration resolution testing; 89. Package consumer tests; 90. Isolated installation tests.

**91–100:** 91. Public utility types; 92. Avoiding implementation details; 93. Nominal barriers; 94. Branded public types; 95. Extensibility hooks; 96. Plugin contracts; 97. Library documentation; 98. Type examples; 99. API review checklist; 100. Library typing mastery.

### Quiz — 40 preguntas

1. ¿Qué es public API surface? 2. ¿Qué es internal surface? 3. ¿Qué significa type leakage? 4. ¿Qué hace declaration emit? 5. ¿Qué hace declarationMap? 6. ¿Por qué importan los generics públicos? 7. ¿Qué significa consumer ergonomics? 8. ¿Qué significa inference ergonomics? 9. ¿Por qué importan los mensajes de error? 10. ¿Qué es API discoverability?

2. ¿Qué es breaking type change? 12. ¿Añadir una propiedad requerida puede romper consumidores? 13. ¿Por qué? 14. ¿Qué ocurre al estrechar una union? 15. ¿Qué ocurre al ampliar ciertas unions? 16. ¿Qué es overload evolution? 17. ¿Qué hace `@deprecated`? 18. ¿Qué es migration signature? 19. ¿Qué significa source compatibility? 20. ¿Qué es consumer compatibility?

3. ¿Qué hace `typesVersions`? 22. ¿Qué significa minimum supported TypeScript? 23. ¿Por qué debes probar varias versiones si las soportas? 24. ¿Qué es package entry point? 25. ¿Qué es subpath API? 26. ¿Qué significa declaration entry point? 27. ¿Qué es isolated consumer test? 28. ¿Por qué ocultar implementation details? 29. ¿Qué es public utility type? 30. ¿Qué es extensibility hook?

4. ¿Qué es plugin contract? 32. ¿Por qué named exports suelen facilitar evolución? 33. ¿Puede una clase ser tipo y valor? 34. ¿Qué diferencia hay con interface? 35. ¿Qué riesgo tienen barrels? 36. ¿Qué es export collision? 37. ¿Cómo documentar APIs genéricas? 38. ¿Cómo detectar declarations incorrectas? 39. ¿Qué debería incluir un API review? 40. Diseña una política de compatibilidad de tipos.

### Examen práctico

Diseña una librería pública con mínimo 30 símbolos exportados, genera sus `.d.ts`, revisa la API emitida y elimina toda dependencia accidental de tipos internos.

### Proyecto

## **Professional TypeScript Library**

### Criterio de dominio

Un consumidor debe poder utilizar la librería únicamente leyendo su API pública y obteniendo inferencia clara.

---

# MÓDULO 34 — Declaration Merging, Module Augmentation y Global Augmentation

### Qué aprenderás

Aprenderás cómo TypeScript combina declaraciones y cómo extender tipos definidos en otros módulos.

### Por qué debes aprenderlo

Es una característica poderosa utilizada por librerías, plugins y typings, pero también puede introducir modificaciones globales difíciles de mantener.

### Al finalizar podrás

Extender APIs existentes conscientemente y diagnosticar merges inesperados.

### 100 temas

**1–10:** 1. Declaration merging; 2. Merge concept; 3. Interface merging; 4. Multiple declarations; 5. Property merging; 6. Method merging; 7. Overload merging; 8. Generic consistency; 9. Merge conflicts; 10. Merge ordering.

**11–20:** 11. Namespace merging; 12. Namespace declarations; 13. Exported members; 14. Non-exported members; 15. Nested namespaces; 16. Namespace continuation; 17. Namespace organization; 18. Historical patterns; 19. Runtime namespace objects; 20. Type/value effects.

**21–30:** 21. Namespace + class; 22. Static extension pattern; 23. Namespace + function; 24. Function properties pattern; 25. Namespace + enum; 26. Enum extension pattern; 27. Merge limitations; 28. Disallowed merges; 29. Runtime ordering; 30. Declaration ordering.

**31–40:** 31. Module augmentation; 32. `declare module`; 33. Existing module extension; 34. Interface augmentation; 35. Method augmentation; 36. Plugin typing; 37. Side-effect imports; 38. Runtime implementation requirement; 39. Type/runtime synchronization; 40. Augmentation scope.

**41–50:** 41. Cannot invent runtime; 42. Patching prototypes; 43. Runtime monkey patching; 44. Matching augmentation; 45. Importing augmentation; 46. File-as-module requirement; 47. Module specifier matching; 48. Resolution interaction; 49. Multiple augmentations; 50. Conflict handling.

**51–60:** 51. Global augmentation; 52. `declare global`; 53. Global interfaces; 54. Global variables; 55. Window-like globals; 56. Built-in extension; 57. Prototype extensions; 58. Global pollution; 59. Name collisions; 60. Hidden dependencies.

**61–70:** 61. Plugin systems; 62. Extension registries; 63. Typed plugins; 64. Augmented context; 65. Augmented services; 66. Framework-like patterns; 67. Configuration augmentation; 68. Event augmentation; 69. Command augmentation; 70. Open-world APIs.

**71–80:** 71. Open interfaces; 72. Closed aliases; 73. Extensibility design; 74. Third-party extensions; 75. Declaration ownership; 76. Consumer augmentation; 77. Library augmentation; 78. Compatibility risks; 79. Upgrade risks; 80. Accidental collisions.

**81–90:** 81. Testing augmentation; 82. Isolated test files; 83. Import ordering; 84. Runtime tests; 85. Type tests; 86. Duplicate members; 87. Incompatible properties; 88. Overload surprises; 89. Debugging merged declarations; 90. Go-to-definition analysis.

**91–100:** 91. Prefer composition considerations; 92. Augmentation alternatives; 93. Wrapper APIs; 94. Adapter APIs; 95. Explicit extension objects; 96. Maintainability; 97. Documentation; 98. Dependency visibility; 99. Safe augmentation rules; 100. Augmentation mastery.

### Quiz — 40 preguntas

1. ¿Qué es declaration merging? 2. ¿Qué declaraciones pueden mergearse? 3. ¿Cómo funciona interface merging? 4. ¿Qué ocurre con métodos? 5. ¿Qué ocurre con propiedades incompatibles? 6. ¿Qué es namespace merging? 7. ¿Puede un namespace combinarse con clase? 8. ¿Qué efecto logra? 9. ¿Puede combinarse con función? 10. ¿Y enum?

2. ¿Qué es module augmentation? 12. ¿Qué hace `declare module` en este contexto? 13. ¿Puede augmentation crear comportamiento runtime? 14. ¿Por qué no? 15. ¿Qué debe existir además? 16. ¿Qué es global augmentation? 17. ¿Qué hace `declare global`? 18. ¿Qué riesgo tiene? 19. ¿Qué es global pollution? 20. ¿Qué es hidden dependency?

3. ¿Por qué el module specifier debe coincidir? 22. ¿Qué relación tiene con resolution? 23. ¿Qué es open-world API? 24. ¿Qué es open interface? 25. ¿Por qué type alias no declaration-merging igual? 26. ¿Qué es consumer augmentation? 27. ¿Qué riesgos aparecen al actualizar dependencia? 28. ¿Qué es accidental collision? 29. ¿Cómo probar augmentation? 30. ¿Por qué necesitas test runtime?

4. ¿Qué alternativa existe a augmentation? 32. ¿Qué es wrapper API? 33. ¿Qué es adapter? 34. ¿Cuándo augmentation tiene sentido? 35. ¿Cuándo evitarla? 36. ¿Cómo documentarla? 37. ¿Qué es prototype patching? 38. ¿Qué riesgo tiene? 39. ¿Cómo diagnosticar un merge inesperado? 40. Diseña un plugin system extensible.

### Examen práctico

Crea un sistema de plugins donde módulos externos amplíen mediante augmentation una interfaz central de comandos y eventos, implementando también el comportamiento runtime correspondiente.

### Proyecto

## **Typed Plugin Augmentation System**

### Criterio de dominio

Debes distinguir siempre **lo que TypeScript cree que existe** de **lo que realmente existe en runtime**.

---

# MÓDULO 35 — Mixins y composición avanzada de clases

### Qué aprenderás

Aprenderás a construir clases mediante composición reutilizable de comportamientos.

### Por qué debes aprenderlo

La herencia simple no siempre es suficiente ni deseable para modelar múltiples capacidades.

### Al finalizar podrás

Implementar mixins type-safe utilizando class expressions y generics.

### 100 temas

**1–10:** 1. Mixin concept; 2. Trait concept; 3. Composition; 4. Multiple behaviors; 5. Class expression pattern; 6. Generic base constructors; 7. Constructor type; 8. `new (...args)`; 9. Base class generic; 10. Mixin factory.

**11–20:** 11. Extending generic base; 12. Returning class expression; 13. Preserving base members; 14. Adding members; 15. Mixin instance type; 16. Constructor inference; 17. Generic constructor helpers; 18. Abstract constructor helpers; 19. Instance constraints; 20. Base requirements.

**21–30:** 21. Constrained mixins; 22. Require property; 23. Require method; 24. Require interface; 25. Multiple requirements; 26. Intersection constraints; 27. Capability mixins; 28. Timestamp mixin; 29. Serializable mixin; 30. Event-capable mixin.

**31–40:** 31. Composing two mixins; 32. Composing multiple mixins; 33. Mixin order; 34. Member collisions; 35. Override collisions; 36. Constructor chains; 37. `super`; 38. Initialization order; 39. Runtime prototype chain; 40. Static members.

**41–50:** 41. Static-side limitations; 42. Static generic limitations; 43. Static mixin properties; 44. Factory statics; 45. Symbol properties; 46. Private fields limitations; 47. Protected members; 48. ES private fields; 49. Nominal constraints; 50. Mixin interoperability.

**51–60:** 51. Fluent mixins; 52. `this` type; 53. Chain preservation; 54. Subclass preservation; 55. Builder-like mixins; 56. Stateful mixins; 57. State isolation; 58. Shared state dangers; 59. Composition contracts; 60. Behavior contracts.

**61–70:** 61. Mixin vs inheritance; 62. Mixin vs composition object; 63. Delegation alternative; 64. Decorator pattern alternative; 65. Interface-only capability; 66. Runtime capability; 67. Structural composition; 68. Multiple inheritance simulation; 69. Diamond-like issues; 70. Conflict resolution.

**71–80:** 71. Applying mixins helper approach; 72. Prototype copying approach; 73. Class-expression preferred pattern; 74. Type copying concerns; 75. Declaration output; 76. Library use; 77. Consumer inheritance; 78. Extension points; 79. Public mixins; 80. Internal mixins.

**81–90:** 81. Generic mixin parameters; 82. Parameterized behavior; 83. Configurable mixins; 84. Mixin factories returning factories; 85. Higher-order class types; 86. Constructor parameter preservation; 87. Variadic constructor tuples; 88. Rest parameters; 89. Generic forwarding; 90. Instance extraction.

**91–100:** 91. Testing mixins; 92. Type tests; 93. Runtime tests; 94. Collision tests; 95. Initialization tests; 96. Complexity control; 97. Documentation; 98. Avoiding mixin soup; 99. Architecture tradeoffs; 100. Mixin mastery.

### Quiz — 40 preguntas

1. ¿Qué es mixin? 2. ¿Qué problema resuelve? 3. ¿Qué es class expression pattern? 4. ¿Por qué necesita constructor type? 5. ¿Qué significa generic base? 6. ¿Cómo añades comportamiento? 7. ¿Qué es constrained mixin? 8. ¿Cómo exigir que la base tenga una propiedad? 9. ¿Cómo exigir método? 10. ¿Cómo combinar requisitos?

2. ¿Por qué importa el orden de mixins? 12. ¿Qué es member collision? 13. ¿Qué ocurre con `super`? 14. ¿Cómo funciona la cadena de prototypes? 15. ¿Qué limitaciones presentan private fields? 16. ¿Qué son static-side limitations? 17. ¿Cómo preservar `this`? 18. ¿Qué es fluent mixin? 19. ¿Qué diferencia hay entre mixin y delegation? 20. ¿Qué diferencia existe frente a composición convencional?

3. ¿Qué es multiple inheritance simulation? 22. ¿Qué problema recuerda al diamond problem? 23. ¿Por qué class-expression es preferible a copiar prototypes manualmente? 24. ¿Qué son public mixins? 25. ¿Qué son internal mixins? 26. ¿Qué es configurable mixin? 27. ¿Cómo preservar constructor params? 28. ¿Qué papel tienen variadic tuples? 29. ¿Qué es higher-order class? 30. ¿Cómo obtener instance type?

4. ¿Por qué probar comportamiento runtime? 32. ¿Por qué también type tests? 33. ¿Qué es mixin soup? 34. ¿Cómo evitarlo? 35. ¿Cuándo preferir inheritance? 36. ¿Cuándo preferir delegation? 37. ¿Cuándo usar mixins? 38. ¿Qué impacto tienen en declarations? 39. ¿Cómo documentar requisitos? 40. Diseña tres mixins composables.

### Examen práctico

Construye entidades componibles con `Timestamped`, `Identifiable`, `Serializable`, `Activatable` y `Eventful`, preservando tipos al combinar los cinco mixins.

### Proyecto

## **Type-Safe Mixin Composition Engine**

### Criterio de dominio

Debes crear composiciones de clases sin perder la información del tipo base ni de los comportamientos añadidos.

---

# MÓDULO 36 — Decorators modernos y decorators legacy

### Qué aprenderás

Comprenderás decorators de clases y miembros, su tipado, sus contextos y la diferencia entre decorators modernos y el modelo experimental histórico.

### Por qué debes aprenderlo

Los decorators son metaprogramación sobre clases y aparecen en múltiples ecosistemas TypeScript.

### Al finalizar podrás

Crear decorators correctamente tipados sin confundir las distintas propuestas y semánticas.

### 100 temas

**1–10:** 1. Decorator concept; 2. Metaprogramming; 3. Decorator syntax; 4. Decorator evaluation; 5. Decorator application; 6. Class decorators; 7. Method decorators; 8. Field decorators; 9. Accessor decorators; 10. Auto-accessors.

**11–20:** 11. Modern decorator contexts; 12. Class decorator context; 13. Method decorator context; 14. Field decorator context; 15. Accessor context; 16. `kind`; 17. `name`; 18. `static`; 19. `private`; 20. Context metadata concepts.

**21–30:** 21. Replacement functions; 22. Method wrapping; 23. Preserving `this`; 24. Preserving parameters; 25. Preserving returns; 26. Generic method decorators; 27. Logging decorator; 28. Timing decorator; 29. Validation decorator concepts; 30. Authorization decorator concepts.

**31–40:** 31. Class replacement; 32. Subclass return; 33. Constructor preservation; 34. Instance shape; 35. Static shape; 36. Initialization hooks; 37. `addInitializer`; 38. Instance initialization; 39. Static initialization; 40. Decorator composition.

**41–50:** 41. Field initialization transform; 42. Initial value transform; 43. Accessor get; 44. Accessor set; 45. Accessor init; 46. Encapsulation; 47. Private members; 48. Symbol names; 49. Computed names; 50. Typed decorator factories.

**51–60:** 51. Decorator factory; 52. Factory parameters; 53. Configuration typing; 54. Generic factories; 55. Literal configuration; 56. `satisfies`; 57. Decorator composition order; 58. Evaluation order; 59. Application order; 60. Side effects.

**61–70:** 61. Legacy decorators; 62. `experimentalDecorators`; 63. Legacy class decorator; 64. Legacy property decorator; 65. Legacy method decorator; 66. Legacy accessor decorator; 67. Legacy parameter decorator; 68. Descriptor APIs; 69. Legacy signatures; 70. Compatibility differences.

**71–80:** 71. Modern vs legacy semantics; 72. Different type signatures; 73. Migration concerns; 74. Parameter decorators difference; 75. Metadata ecosystems; 76. Runtime metadata concepts; 77. Reflection patterns; 78. Metadata limitations; 79. Framework interoperability; 80. Version awareness.

**81–90:** 81. Decorator typing helpers; 82. Generic `This`; 83. Generic `Args`; 84. Generic `Return`; 85. Method preservation; 86. Async methods; 87. Overloaded methods concerns; 88. Error handling; 89. Debugging decorated methods; 90. Stack traces.

**91–100:** 91. Decorator overuse; 92. Hidden behavior; 93. Explicit alternatives; 94. Higher-order functions; 95. Mixins; 96. Wrappers; 97. Testing decorators; 98. Type safety testing; 99. Architecture decisions; 100. Decorator mastery.

### Quiz — 40 preguntas

1. ¿Qué es decorator? 2. ¿Qué significa metaprogramming? 3. ¿Qué puede decorar? 4. ¿Qué es decorator context? 5. ¿Qué información proporciona `kind`? 6. ¿Qué representa name? 7. ¿Qué indica static? 8. ¿Qué indica private? 9. ¿Qué hace addInitializer? 10. ¿Cómo envolverías un método?

2. ¿Qué debes preservar al envolver método? 12. ¿Por qué preservar `this`? 13. ¿Por qué preservar parámetros? 14. ¿Por qué preservar retorno? 15. ¿Qué es decorator factory? 16. ¿Cómo tipar su configuración? 17. ¿Qué importancia tiene el orden? 18. ¿Qué diferencia hay entre evaluation y application? 19. ¿Qué es class replacement? 20. ¿Qué riesgos presenta?

3. ¿Qué es field initializer transform? 22. ¿Qué es accessor decorator? 23. ¿Qué diferencia tiene auto-accessor? 24. ¿Qué es legacy decorator? 25. ¿Qué flag se asocia al modelo experimental antiguo? 26. ¿Son idénticos los decorators modernos y legacy? 27. ¿Por qué no? 28. ¿Qué son parameter decorators legacy? 29. ¿Qué es reflection pattern? 30. ¿Los decorators crean automáticamente metadata completa?

4. ¿Qué es hidden behavior? 32. ¿Por qué puede ser negativo? 33. ¿Qué alternativas explícitas existen? 34. ¿Cuándo un higher-order function puede sustituir decorator? 35. ¿Cuándo mixin? 36. ¿Cómo testear un decorator? 37. ¿Por qué necesitas runtime tests? 38. ¿Qué problema presentan overloads decorados? 39. ¿Qué significa version awareness? 40. Diseña un decorator type-safe de logging.

### Examen práctico

Construye decorators para logging, timing, memoización controlada y validación de invariantes, preservando el tipo original de los métodos.

### Proyecto

## **Decorator Metaprogramming Toolkit**

### Criterio de dominio

Debes poder explicar las diferencias conceptuales y de tipado entre decorators modernos y la implementación experimental histórica.

---

# PARTE VI — PROTOCOLOS, JAVASCRIPT Y BUILD SYSTEM TYPESCRIPT

# MÓDULO 37 — Iterators, Generators y Async Iteration

### Qué aprenderás

Dominarás los protocolos de iteración y su representación dentro del sistema de tipos.

### Por qué debes aprenderlo

Muchas APIs avanzadas de JavaScript se basan en `Iterable`, `Iterator` y generators.

### Al finalizar podrás

Construir secuencias lazy y generadores completamente tipados.

### 100 temas

**1–10:** 1. Iteration protocol; 2. Iterable protocol; 3. Iterator; 4. Iterable; 5. `Symbol.iterator`; 6. `next`; 7. IteratorResult; 8. Done state; 9. Yielded value; 10. Return value.

**11–20:** 11. IterableIterator; 12. Arrays as iterables; 13. Strings as iterables; 14. Sets concept; 15. Maps concept; 16. Custom iterable; 17. Iterator factories; 18. Lazy iteration; 19. Eager vs lazy; 20. Infinite iterables.

**21–30:** 21. Generator functions; 22. `function*`; 23. `yield`; 24. Generator type; 25. Yield type; 26. Return type; 27. Next type; 28. `Generator<Y,R,N>`; 29. Generator inference; 30. Explicit generator typing.

**31–40:** 31. `yield*`; 32. Delegated iteration; 33. Yield delegation; 34. Return delegation; 35. Iterable delegation; 36. Generator composition; 37. Pipeline generators; 38. Transform generators; 39. Filter generators; 40. Flatten generators.

**41–50:** 41. Passing values into generator; 42. `next(value)`; 43. Next type; 44. Bidirectional communication; 45. State machines with generators; 46. Coroutine concept; 47. Generator state; 48. Suspended execution; 49. Completion; 50. Error propagation.

**51–60:** 51. `return()`; 52. `throw()`; 53. Generator cleanup; 54. `try/finally`; 55. Resource cleanup; 56. Early termination; 57. `for...of`; 58. Destructuring iterables; 59. Spread; 60. Iterator consumption.

**61–70:** 61. AsyncIterator; 62. AsyncIterable; 63. `Symbol.asyncIterator`; 64. AsyncGenerator; 65. `async function*`; 66. Async yield; 67. `for await...of`; 68. Promise values; 69. Streaming concepts; 70. Backpressure concept.

**71–80:** 71. `AsyncGenerator<Y,R,N>`; 72. Async generator typing; 73. Async transform; 74. Async filter; 75. Async pipelines; 76. Cancellation concept; 77. Error propagation; 78. Cleanup; 79. Lazy asynchronous work; 80. Producer/consumer model.

**81–90:** 81. Iterable generic constraints; 82. Element extraction; 83. `Iterable<infer T>`; 84. Iterator helper types concept; 85. Generic iterable utilities; 86. Readonly iteration; 87. Sequence abstraction; 88. Reusable pipelines; 89. Iterator adapters; 90. Type preservation.

**91–100:** 91. Downlevel iteration; 92. Target interactions; 93. `downlevelIteration`; 94. Runtime support; 95. Polyfill considerations; 96. Performance; 97. Generator debugging; 98. Testing lazy sequences; 99. Edge cases; 100. Iteration mastery.

### Quiz — 40 preguntas

1. ¿Qué es iterator? 2. ¿Qué es iterable? 3. ¿Qué hace Symbol.iterator? 4. ¿Qué retorna `next()`? 5. ¿Qué representa `done`? 6. ¿Qué es IterableIterator? 7. ¿Qué es lazy iteration? 8. ¿Qué ventaja tiene? 9. ¿Qué es generator? 10. ¿Qué hace yield?

2. ¿Qué representa `Generator<Y,R,N>`? 12. ¿Qué representa Y? 13. ¿R? 14. ¿N? 15. ¿Qué hace yield*? 16. ¿Qué es delegated iteration? 17. ¿Puede enviarse valor a generator mediante next? 18. ¿Qué es bidirectional communication? 19. ¿Qué hace return()? 20. ¿Qué hace throw()?

3. ¿Cómo ejecutar cleanup? 22. ¿Qué es AsyncIterable? 23. ¿Qué hace Symbol.asyncIterator? 24. ¿Qué es async generator? 25. ¿Qué hace for await? 26. ¿Qué representa AsyncGenerator? 27. ¿Qué es streaming conceptualmente? 28. ¿Qué es backpressure? 29. ¿Cómo extraerías el elemento de Iterable<T>? 30. ¿Qué es generic iterable utility?

4. ¿Qué hace downlevelIteration? 32. ¿Por qué depende del target? 33. ¿Qué significa runtime support? 34. ¿Qué es infinite iterable? 35. ¿Cómo evitar consumirlo totalmente? 36. ¿Qué es iterator adapter? 37. ¿Qué es transform generator? 38. ¿Qué es filter generator? 39. ¿Por qué probar laziness? 40. Diseña un pipeline generator.

### Examen práctico

Construye una biblioteca lazy con `range`, `map`, `filter`, `take`, `flatMap` y versiones asíncronas seleccionadas.

### Proyecto

## **Lazy Typed Sequences**

### Criterio de dominio

Debes poder tipar correctamente los tres parámetros de un Generator y comprender los protocolos runtime.

---

# MÓDULO 38 — JSX y el sistema de tipos de TypeScript sin depender de React

### Qué aprenderás

Comprenderás cómo TypeScript analiza y tipa JSX independientemente de cualquier framework concreto.

### Por qué debes aprenderlo

JSX posee reglas especiales de type checking que forman parte de TypeScript.

### Al finalizar podrás

Entender cómo se definen elementos JSX, atributos, children e intrinsic elements.

### 100 temas

**1–10:** 1. JSX concept; 2. `.tsx`; 3. Parsing JSX; 4. JSX expressions; 5. JSX elements; 6. Self-closing elements; 7. Attributes; 8. Children; 9. Expressions in JSX; 10. Type checking JSX.

**11–20:** 11. JSX compiler option; 12. Preserve concepts; 13. Runtime transform concepts; 14. Development transform concepts; 15. Factory concepts; 16. Fragment concepts; 17. JSX runtime imports concept; 18. Emit strategies; 19. Type checking vs emit; 20. Framework independence.

**21–30:** 21. Intrinsic elements; 22. Value-based elements; 23. Lowercase elements; 24. Uppercase elements; 25. JSX namespace concept; 26. IntrinsicElements interface; 27. Custom intrinsic tags; 28. Attribute validation; 29. Unknown intrinsic tags; 30. Element result typing.

**31–40:** 31. Function components concept; 32. Function parameter props; 33. Class component concept; 34. Constructor lookup; 35. Instance lookup; 36. Element class type; 37. Element attributes property; 38. Children property concepts; 39. Component return checking; 40. Component overload considerations.

**41–50:** 41. Attribute types; 42. Required props; 43. Optional props; 44. Literal props; 45. Union props; 46. Generic props; 47. Spread attributes; 48. Excess property behavior; 49. Event-like props; 50. Callback props.

**51–60:** 51. Children types; 52. Single child; 53. Multiple children; 54. Optional children; 55. Text children; 56. Expression children; 57. Nested elements; 58. Child validation; 59. Custom children property; 60. Variadic child models.

**61–70:** 61. Generic JSX components; 62. Generic inference in JSX; 63. Explicit generic arguments; 64. Constraints; 65. Correlated props; 66. Discriminated props; 67. Mutually exclusive props; 68. Conditional props; 69. Builder-like components; 70. Render function concepts.

**71–80:** 71. JSX.Element concepts; 72. ElementType concepts; 73. Component-like typing; 74. Intrinsic attribute augmentation; 75. Library-managed attributes concept; 76. Attribute transformation; 77. Default-like props concept; 78. Ref-like attributes concept; 79. Custom JSX runtimes; 80. Library authoring.

**81–90:** 81. JSX namespace customization; 82. Custom runtime declarations; 83. Declaration merging; 84. Intrinsic element augmentation; 85. Type library design; 86. Global vs module-scoped JSX concepts; 87. Namespace resolution; 88. Compiler lookup; 89. Diagnostics; 90. JSX inference debugging.

**91–100:** 91. JSX type-level patterns; 92. Polymorphic component concepts; 93. Tag-dependent props; 94. Generic tag parameters; 95. Prop extraction; 96. Component props utility concepts; 97. Child constraints; 98. JSX API ergonomics; 99. Framework-neutral JSX engine; 100. JSX typing mastery.

### Quiz — 40 preguntas

1. ¿Qué extensión usa TypeScript normalmente para JSX? 2. ¿Qué diferencia hay entre type checking y emit de JSX? 3. ¿Qué es intrinsic element? 4. ¿Cómo distingue TS intrinsic de value-based element? 5. ¿Qué representa IntrinsicElements? 6. ¿Cómo se validan atributos? 7. ¿Qué ocurre con tag desconocido? 8. ¿Qué es value-based element? 9. ¿Cómo puede modelarse una función que actúa como elemento? 10. ¿Cómo se tipan props?

2. ¿Qué son required props? 12. ¿Qué son optional props? 13. ¿Cómo spread afecta atributos? 14. ¿Qué son children? 15. ¿Cómo se valida children? 16. ¿Puede configurarse la propiedad usada para children? 17. ¿Qué es generic JSX component? 18. ¿Puede TS inferir generics desde props? 19. ¿Qué son correlated props? 20. ¿Cómo usar discriminated union en props?

3. ¿Qué son mutually exclusive props? 22. ¿Qué es JSX namespace? 23. ¿Cómo personalizar intrinsic elements? 24. ¿Qué es custom JSX runtime? 25. ¿Qué relación tiene declaration merging? 26. ¿Qué es attribute transformation? 27. ¿Qué es polymorphic component conceptualmente? 28. ¿Qué significa tag-dependent props? 29. ¿Cómo extraerías props de un tipo de componente? 30. ¿Qué son JSX diagnostics?

4. ¿JSX pertenece exclusivamente a React? 32. ¿Por qué no? 33. ¿Qué hace el compilador con `.tsx`? 34. ¿Qué son fragment concepts? 35. ¿Qué es runtime transform? 36. ¿Cómo diseñarías intrinsic tag propio? 37. ¿Qué riesgos tiene global augmentation? 38. ¿Cómo evitar `any` en JSX custom? 39. ¿Qué es framework-neutral JSX? 40. Diseña un mini runtime tipado conceptualmente.

### Examen práctico

Define tus propias declarations JSX y crea un conjunto de elementos intrínsecos y componentes genéricos sin instalar React.

### Proyecto

## **Framework-Neutral Typed JSX**

### Criterio de dominio

Debes comprender JSX como característica sintáctica y de type checking, no como sinónimo de React.

---

# MÓDULO 39 — JavaScript Interop, `allowJs`, `checkJs` y JSDoc TypeScript

### Qué aprenderás

Aprenderás a aplicar el sistema de tipos de TypeScript sobre proyectos JavaScript.

### Por qué debes aprenderlo

Las migraciones progresivas y codebases mixtas son situaciones profesionales frecuentes.

### Al finalizar podrás

Tipar JavaScript mediante JSDoc y migrarlo gradualmente a `.ts`.

### 100 temas

**1–10:** 1. JavaScript projects; 2. `allowJs`; 3. `checkJs`; 4. `// @ts-check`; 5. `// @ts-nocheck`; 6. `// @ts-ignore`; 7. `// @ts-expect-error`; 8. Mixed TS/JS; 9. Gradual adoption; 10. Migration strategy.

**11–20:** 11. JS inference; 12. Object inference differences; 13. Open-ended objects; 14. CommonJS patterns; 15. Function inference; 16. Class inference; 17. Constructor properties; 18. Prototype patterns; 19. Module detection; 20. JavaScript semantics.

**21–30:** 21. JSDoc `@type`; 22. JSDoc `@param`; 23. JSDoc `@returns`; 24. JSDoc `@return`; 25. `@typedef`; 26. `@callback`; 27. `@template`; 28. Generic JSDoc; 29. `@extends`; 30. `@implements`.

**31–40:** 31. Optional parameters JSDoc; 32. Default parameters; 33. Rest parameters; 34. Object shapes; 35. Record-like objects; 36. Union syntax; 37. Nullable values; 38. Function types; 39. Constructor types; 40. Literal types in JSDoc.

**41–50:** 41. Import types in JSDoc; 42. `import()` type syntax; 43. Referencing TS types; 44. Cross-file JSDoc types; 45. External package types; 46. Type-only relationships; 47. Avoiding runtime import; 48. Generic imports; 49. Namespaced types; 50. Declaration reuse.

**51–60:** 51. `@satisfies`; 52. `@type` assertions; 53. Const-like behavior concepts; 54. Type checking configurations; 55. Strict JS projects; 56. `noImplicitAny` implications; 57. Null checking in JS; 58. Index access; 59. Unknown inputs; 60. Runtime validation.

**61–70:** 61. Generating declarations from JS; 62. `declaration`; 63. `emitDeclarationOnly`; 64. JSDoc-to-d.ts; 65. Public JS library typing; 66. JSDoc API surface; 67. Consumer typings; 68. Declaration quality; 69. Inference limitations; 70. Explicit annotations.

**71–80:** 71. Migration file by file; 72. Rename `.js` to `.ts`; 73. Fix diagnostics; 74. Remove implicit any; 75. Model nullability; 76. Replace assertions; 77. Introduce generics; 78. Convert CommonJS; 79. Type external boundaries; 80. Enable strictness incrementally.

**81–90:** 81. Error suppression; 82. `@ts-ignore`; 83. `@ts-expect-error`; 84. Difference between them; 85. Documenting expected errors; 86. Suppression debt; 87. Measuring migration; 88. Typed percentage concept; 89. Migration checkpoints; 90. Regression prevention.

**91–100:** 91. JS library maintenance; 92. TS library migration; 93. Mixed-source declarations; 94. Build organization; 95. Editor experience; 96. Documentation synchronization; 97. JSDoc limits; 98. When to switch to TS; 99. Progressive typing strategy; 100. JS interop mastery.

### Quiz — 40 preguntas

1. ¿Qué hace allowJs? 2. ¿Qué hace checkJs? 3. ¿Qué hace @ts-check? 4. ¿Qué hace @ts-nocheck? 5. ¿Qué hace @ts-ignore? 6. ¿Qué hace @ts-expect-error? 7. ¿Cuál es preferible cuando esperas un error concreto? 8. ¿Qué es gradual adoption? 9. ¿Qué es JSDoc @type? 10. ¿Qué hace @param?

2. ¿Qué hace @returns? 12. ¿Qué es @typedef? 13. ¿Qué es @callback? 14. ¿Qué es @template? 15. ¿Puede haber generics en JSDoc? 16. ¿Cómo referencias un tipo externo? 17. ¿Qué hace `import()` en type position JSDoc? 18. ¿Por qué no requiere necesariamente runtime import? 19. ¿Puede generarse `.d.ts` desde JS? 20. ¿Qué se necesita para ello?

3. ¿Qué es JSDoc-to-d.ts? 22. ¿Cómo migrar gradualmente? 23. ¿Por qué no renombrar todos los archivos de golpe? 24. ¿Qué es suppression debt? 25. ¿Qué problema tiene @ts-ignore? 26. ¿Cómo @ts-expect-error mejora pruebas? 27. ¿Qué es mixed codebase? 28. ¿Cómo introducir strictness gradualmente? 29. ¿Qué son external boundaries? 30. ¿Por qué empezar por ellas?

4. ¿Qué limitaciones tiene inferencia en JS? 32. ¿Qué son open-ended objects? 33. ¿Cómo TypeScript interpreta ciertas clases JS? 34. ¿Qué es CommonJS pattern? 35. ¿Puede JSDoc modelar unions? 36. ¿Puede modelar literals? 37. ¿Puede modelar callbacks? 38. ¿Cuándo JSDoc deja de ser suficiente? 39. ¿Cuándo pasar a `.ts`? 40. Diseña estrategia para migrar 500 archivos JS.

### Examen práctico

Construye primero una librería JavaScript con JSDoc completo y `checkJs`; después migra una parte representativa a TypeScript manteniendo exactamente la misma API.

### Proyecto

## **Progressive JavaScript-to-TypeScript Migration**

### Criterio de dominio

Debes poder mejorar type safety sin exigir una migración total inmediata.

---

# MÓDULO 40 — Project References, composite projects y `tsc --build`

### Qué aprenderás

Dividirás proyectos TypeScript grandes en unidades compilables relacionadas.

### Por qué debes aprenderlo

Las codebases grandes necesitan límites lógicos, compilaciones incrementales y gestión explícita de dependencias.

### Al finalizar podrás

Diseñar una arquitectura multiproyecto utilizando referencias de TypeScript.

### 100 temas

**1–10:** 1. Project References; 2. `references`; 3. Referenced project; 4. Dependent project; 5. Project graph; 6. Logical separation; 7. Build separation; 8. Declaration boundaries; 9. Dependency order; 10. Incremental architecture.

**11–20:** 11. `composite`; 12. Composite requirements; 13. Declaration requirement; 14. Root file constraints; 15. Output expectations; 16. Project boundary; 17. `.d.ts` consumption; 18. Source redirection concepts; 19. Editor behavior; 20. Build artifacts.

**21–30:** 21. `tsc --build`; 22. `tsc -b`; 23. Build mode; 24. Dependency ordering; 25. Out-of-date detection; 26. Incremental rebuilding; 27. Build graph; 28. Build failures; 29. Stop behavior; 30. Exit codes.

**31–40:** 31. `--clean`; 32. Clean builds; 33. `--force`; 34. Forced rebuild; 35. `--verbose`; 36. Build diagnostics; 37. Dry reasoning; 38. Stale outputs; 39. Timestamp concepts; 40. Build correctness.

**41–50:** 41. `.tsbuildinfo`; 42. Incremental metadata; 43. `incremental`; 44. `tsBuildInfoFile`; 45. Cache location; 46. Cache invalidation; 47. Rebuild reasons; 48. Compiler version changes; 49. Config changes; 50. Source changes.

**51–60:** 51. Base tsconfig; 52. Shared configs; 53. Extending configs; 54. Package configs; 55. Library configs; 56. Application configs concept; 57. Test configs concept; 58. References arrays; 59. Circular references; 60. DAG requirement concept.

**61–70:** 61. Core project; 62. Utility project; 63. Domain project; 64. API types project; 65. Shared contracts; 66. Dependency direction; 67. Layered references; 68. Feature references; 69. Avoiding mega-projects; 70. Boundary enforcement.

**71–80:** 71. Declaration maps; 72. Go-to-definition experience; 73. Editor memory; 74. Editor project loading; 75. Large project performance; 76. Source redirects; 77. Disable source redirect concepts; 78. Declaration navigation; 79. IDE scalability; 80. Developer experience.

**81–90:** 81. Build output ownership; 82. Output collisions; 83. `outDir`; 84. `rootDir`; 85. declarationDir concepts; 86. Shared source problems; 87. Referencing source incorrectly; 88. Package-like boundaries; 89. Artifact isolation; 90. Clean architecture.

**91–100:** 91. Build graph debugging; 92. Missing references; 93. Invalid composite configs; 94. Stale declarations; 95. Circular dependencies; 96. CI build concept; 97. Selective builds; 98. Migration from single project; 99. Scaling strategy; 100. Project Reference mastery.

### Quiz — 40 preguntas

1. ¿Qué es Project Reference? 2. ¿Qué propiedad define references? 3. ¿Qué es composite? 4. ¿Por qué se necesita? 5. ¿Qué tipo de outputs son importantes entre proyectos? 6. ¿Cómo consume un proyecto referenciado? 7. ¿Qué hace `tsc -b`? 8. ¿Qué es build mode? 9. ¿Cómo determina orden? 10. ¿Qué es project graph?

2. ¿Qué hace --clean? 12. ¿Qué hace --force? 13. ¿Qué hace --verbose? 14. ¿Qué es `.tsbuildinfo`? 15. ¿Qué almacena conceptualmente? 16. ¿Qué hace incremental? 17. ¿Qué cambia si modificas config? 18. ¿Qué ocurre si cambia compiler version? 19. ¿Por qué usar base tsconfig? 20. ¿Qué problema tienen referencias circulares?

3. ¿Qué es DAG conceptualmente? 22. ¿Qué significa dependency direction? 23. ¿Qué ventaja tiene separar domain de utilities? 24. ¿Cómo ayudan declarations a los límites? 25. ¿Qué son declaration maps? 26. ¿Cómo mejoran navegación? 27. ¿Qué problema puede causar output collision? 28. ¿Por qué cada proyecto debe poseer sus artifacts? 29. ¿Qué es stale declaration? 30. ¿Cómo detectarla?

4. ¿Cómo migrarías un proyecto enorme a references? 32. ¿Qué separarías primero? 33. ¿Cómo evitar mega-project? 34. ¿Qué impacto puede tener sobre memory del editor? 35. ¿Qué es source redirect? 36. ¿Por qué existen referencias explícitas? 37. ¿Qué es selective build conceptualmente? 38. ¿Cómo probarías el graph? 39. ¿Cómo diagnosticarías build inesperado? 40. Diseña un graph de ocho proyectos.

### Examen práctico

Divide una codebase TypeScript monolítica en mínimo seis proyectos composite relacionados y compílalos únicamente mediante `tsc -b`.

### Proyecto

## **Large-Scale TypeScript Project Graph**

### Criterio de dominio

Debes ser capaz de dibujar el grafo de referencias y explicar por qué cada dependencia apunta en una dirección concreta.

---

# PARTE VII — TYPE-LEVEL PROGRAMMING AVANZADO

# MÓDULO 41 — Variadic Tuple Types y algoritmos avanzados sobre tuples

### Qué aprenderás

Manipularás listas de tipos como estructuras sobre las que pueden ejecutarse transformaciones recursivas.

### Por qué debes aprenderlo

Las tuples son la base de muchas APIs avanzadas de funciones, pipelines, currying y type-level algorithms.

### Al finalizar podrás

Construir utilities complejos sobre listas de parámetros preservando cada elemento.

### 100 temas

**1–10:** 1. Tuple review; 2. Variadic tuples; 3. Generic tuple constraint; 4. `T extends readonly unknown[]`; 5. Rest tuple inference; 6. Prefix rest; 7. Suffix rest; 8. Middle rest; 9. Tuple concatenation; 10. Tuple preservation.

**11–20:** 11. Head; 12. Tail; 13. Last; 14. Init; 15. First; 16. Shift; 17. Pop; 18. Push; 19. Unshift; 20. Concat.

**21–30:** 21. Reverse; 22. Recursive Reverse; 23. Accumulator Reverse; 24. Flatten; 25. Deep Flatten; 26. Includes; 27. IndexOf concept; 28. LastIndexOf concept; 29. Unique; 30. Filter.

**31–40:** 31. Map tuple concept; 32. Transform elements; 33. Replace; 34. Remove; 35. Zip; 36. ZipWith concept; 37. Chunk concept; 38. Slice concept; 39. Drop; 40. Take.

**41–50:** 41. Tuple length; 42. Literal length; 43. Tuple counters; 44. BuildTuple; 45. Increment; 46. Decrement; 47. Add concept; 48. Subtract concept; 49. Compare lengths; 50. Numeric limitations.

**51–60:** 51. Function parameter tuples; 52. `Parameters<T>`; 53. Preserving arguments; 54. Generic wrappers; 55. Append argument; 56. Prepend argument; 57. Remove first argument; 58. Partial application; 59. Bind-like typing; 60. Function composition.

**61–70:** 61. Currying; 62. Curry one-by-one; 63. Curry groups concept; 64. Uncurrying; 65. Pipeline arguments; 66. Composition constraints; 67. Return-to-next-input matching; 68. Variadic compose; 69. Variadic pipe; 70. Inference limits.

**71–80:** 71. Named/labeled tuples; 72. Label preservation; 73. Optional tuple entries; 74. Rest entries; 75. Readonly tuples; 76. Mutable conversion; 77. Tuple union; 78. Distributed tuple operations; 79. Union-to-tuple challenges concept; 80. Ordering caveats.

**81–90:** 81. Recursive depth; 82. Tail-style recursion; 83. Accumulator patterns; 84. Instantiation limits; 85. Large tuple performance; 86. Helper types; 87. Simplification; 88. Compiler diagnostics; 89. Type test matrices; 90. Performance-conscious algorithms.

**91–100:** 91. Tuple parser tokens; 92. Argument DSLs; 93. Builder state tuples; 94. Event argument tuples; 95. Command parameters; 96. Function adapters; 97. Type-level data processing; 98. Practical boundaries; 99. Algorithm design; 100. Variadic tuple mastery.

### Quiz — 40 preguntas

1. ¿Qué es variadic tuple? 2. ¿Cómo restringes un generic a tuple? 3. ¿Qué significa `...infer R`? 4. ¿Cómo obtienes Head? 5. ¿Cómo Tail? 6. ¿Cómo Last? 7. ¿Cómo Init? 8. ¿Cómo concatenar tuples? 9. ¿Cómo Reverse recursivamente? 10. ¿Qué es accumulator?

2. ¿Cómo Flatten? 12. ¿Qué es Includes? 13. ¿Qué es Zip? 14. ¿Qué es Chunk conceptualmente? 15. ¿Qué representa tuple length? 16. ¿Cómo puede servir como número? 17. ¿Qué es BuildTuple? 18. ¿Por qué la aritmética tiene límites? 19. ¿Cómo preservar parameters de una función? 20. ¿Cómo prepend argument?

3. ¿Qué es partial application? 22. ¿Qué es currying? 23. ¿Qué es uncurrying? 24. ¿Cómo pipe relaciona retornos con inputs? 25. ¿Qué problema tiene compose variádico? 26. ¿Qué son labeled tuples? 27. ¿Se conservan siempre las labels en todas las operaciones? 28. ¿Qué son optional tuple entries? 29. ¿Qué es readonly tuple? 30. ¿Cómo convertirlo conceptualmente a mutable?

4. ¿Qué es union-to-tuple challenge? 32. ¿Por qué el orden puede ser problemático? 33. ¿Qué es instantiation depth? 34. ¿Cómo accumulator puede ayudar? 35. ¿Qué es performance-conscious algorithm? 36. ¿Cómo testear utilities de tuples? 37. ¿Qué es event argument tuple? 38. ¿Qué es function adapter? 39. ¿Cuándo dejar de hacer aritmética a nivel de tipos? 40. Diseña un variadic pipe.

### Examen práctico

Implementa 20 algoritmos sobre tuples, incluyendo `Reverse`, `Flatten`, `Zip`, `Take`, `Drop`, `Filter`, `Includes`, `Curry` y un `Pipe` type-safe.

### Proyecto

## **Type-Level Tuple Algorithms Library**

### Criterio de dominio

Debes poder razonar sobre una tuple recursiva igual que sobre una estructura de datos, pero comprendiendo los límites del compilador.

---

# MÓDULO 42 — Inferencia genérica avanzada, higher-order generics y control de inferencia

### Qué aprenderás

Comprenderás cómo TypeScript selecciona argumentos genéricos en APIs complejas.

### Por qué debes aprenderlo

La calidad de una API avanzada depende en gran medida de que los consumidores obtengan inferencia útil sin escribir tipos manualmente.

### Al finalizar podrás

Diseñar APIs genéricas con inferencia predecible y controlada.

### 100 temas

**1–10:** 1. Generic inference review; 2. Inference candidates; 3. Input inference; 4. Contextual inference; 5. Return context; 6. Multiple candidates; 7. Best candidate concept; 8. Literal widening; 9. Literal preservation; 10. Inference debugging.

**11–20:** 11. Inference from arrays; 12. Tuples; 13. Objects; 14. Functions; 15. Callbacks; 16. Constructors; 17. Nested generics; 18. Promises; 19. Conditional positions; 20. Contravariant positions.

**21–30:** 21. Generic parameter defaults; 22. Default inference fallback; 23. Constraints; 24. Constraint candidates; 25. Constraint fallback; 26. Dependent parameters; 27. Key/value correlation; 28. Cross-parameter inference; 29. Bidirectional relationships; 30. Inference order.

**31–40:** 31. `NoInfer`; 32. Blocking inference source; 33. Preferred inference source; 34. Defaults from another argument; 35. Validation against inferred type; 36. State parameters; 37. Configuration defaults; 38. API ergonomics; 39. Avoiding unwanted widening; 40. Inference steering.

**41–50:** 41. Const type parameters; 42. Literal-preserving generics; 43. Readonly inference; 44. Tuple inference; 45. Object literal inference; 46. Const constraints; 47. Narrow API results; 48. Avoiding `as const` in consumers; 49. Generic API design; 50. Const generic tradeoffs.

**51–60:** 51. Higher-order generics; 52. Generic functions accepting generic functions; 53. Generic function returns; 54. Preserving generic signatures; 55. Higher-order inference; 56. Wrapper functions; 57. Identity wrappers; 58. Memoization typing; 59. Decorator-style wrappers; 60. Middleware-like composition concepts.

**61–70:** 61. Generic factories; 62. Generic constructors; 63. Class factories; 64. Mixin factories; 65. Higher-order classes; 66. Generic builder factories; 67. Callback factories; 68. Predicate factories; 69. Guard factories; 70. Parser factories.

**71–80:** 71. Variance and inference; 72. Covariant inference; 73. Contravariant inference; 74. Mixed variance; 75. Invariance effects; 76. Callback parameter inference; 77. Return inference; 78. Method inference; 79. Assignment context; 80. Structural compatibility effects.

**81–90:** 81. Generic overloads; 82. Overload vs conditional; 83. Overload vs generic; 84. Generic unions; 85. Generic discriminated unions; 86. Conditional return types; 87. Correlated generics; 88. Implementation assertions sometimes needed; 89. Safe implementation boundaries; 90. Public signature quality.

**91–100:** 91. Inference failure diagnostics; 92. `unknown` inference; 93. `never` inference; 94. Broad constraint results; 95. Over-constrained API; 96. Under-constrained API; 97. Type parameter minimization; 98. Inference-first design; 99. Consumer testing; 100. Generic inference mastery.

### Quiz — 40 preguntas

1. ¿Qué es inference candidate? 2. ¿De dónde puede inferirse T? 3. ¿Qué es contextual inference? 4. ¿Qué es literal widening? 5. ¿Cómo preservar literals? 6. ¿Qué papel tiene constraint? 7. ¿Qué son dependent parameters? 8. ¿Qué es key/value correlation? 9. ¿Qué es inference order? 10. ¿Qué hace NoInfer?

2. ¿Por qué bloquear una fuente de inferencia? 12. ¿Qué es preferred source? 13. ¿Qué son const type parameters? 14. ¿Qué problema ayudan a resolver? 15. ¿Cómo afectan tuples? 16. ¿Cómo afectan object literals? 17. ¿Qué es higher-order generic? 18. ¿Cómo preservar signature genérica? 19. ¿Qué es identity wrapper? 20. ¿Qué problema tiene memoization genérica?

3. ¿Qué es generic class factory? 22. ¿Qué es higher-order class? 23. ¿Qué es parser factory? 24. ¿Cómo variance afecta inferencia? 25. ¿Qué es covariant inference? 26. ¿Qué es contravariant inference? 27. ¿Qué ocurre con posiciones mixtas? 28. ¿Cuándo overload puede ser mejor? 29. ¿Cuándo conditional type? 30. ¿Qué son correlated generics?

4. ¿Qué indica una inferencia a unknown inesperada? 32. ¿Cómo puede surgir never? 33. ¿Qué es over-constrained API? 34. ¿Qué es under-constrained API? 35. ¿Por qué minimizar type parameters? 36. ¿Qué significa inference-first design? 37. ¿Por qué probar desde la perspectiva del consumidor? 38. ¿Cómo detectar widening indeseado? 39. ¿Qué es safe implementation boundary? 40. Diseña API genérica con NoInfer.

### Examen práctico

Diseña una biblioteca genérica donde configuraciones, valores predeterminados, callbacks y resultados mantengan inferencia literal sin que el consumidor especifique parámetros manualmente.

### Proyecto

## **Generic Inference Engineering Laboratory**

### Criterio de dominio

Debes ser capaz de explicar **de qué argumento obtuvo TypeScript cada generic**.

---

# MÓDULO 43 — Type-State, Builders y Fluent APIs Type-Safe

### Qué aprenderás

Codificarás el estado de construcción de un objeto directamente dentro de sus tipos.

### Por qué debes aprenderlo

Permite impedir secuencias incorrectas de llamadas antes de ejecutar el programa.

### Al finalizar podrás

Crear builders y fluent APIs donde solamente las operaciones válidas estén disponibles.

### 100 temas

**1–10:** 1. Builder pattern; 2. Fluent API; 3. Method chaining; 4. Polymorphic `this`; 5. Immutable builder; 6. Mutable builder; 7. State encoding; 8. Type-state pattern; 9. Compile-time state; 10. Runtime state.

**11–20:** 11. Generic state parameter; 12. Empty state; 13. Partial state; 14. Complete state; 15. Required steps; 16. Optional steps; 17. Ordered steps; 18. Unordered steps; 19. Duplicate steps; 20. Forbidden steps.

**21–30:** 21. Boolean generic flags; 22. Literal state flags; 23. Object state generic; 24. Tuple state; 25. Union state; 26. Branded state; 27. Phantom state; 28. State transitions; 29. Transition return type; 30. State preservation.

**31–40:** 31. Conditional method availability; 32. `this` constraints; 33. Conditional returns; 34. Interface splitting; 35. Progressive interfaces; 36. Builder intersections; 37. Omit consumed methods; 38. Remove-after-use methods; 39. State-specific APIs; 40. Illegal sequence prevention.

**41–50:** 41. Required field tracking; 42. Set-key tracking; 43. Remaining-key calculation; 44. `Exclude`; 45. `keyof`; 46. Mapped state; 47. Complete-check conditional; 48. Build availability; 49. Missing-field diagnostics; 50. Better error types.

**51–60:** 51. Query builder concept; 52. Request builder; 53. Configuration builder; 54. Pipeline builder; 55. Command builder; 56. Schema builder; 57. State machine builder; 58. Class builder; 59. Object builder; 60. Validation builder.

**61–70:** 61. Generic accumulating object; 62. Intersection accumulation; 63. Object spread type accumulation; 64. Literal preservation; 65. Property inference; 66. Dynamic keys; 67. Key restrictions; 68. Value correlation; 69. Duplicate-key prevention; 70. Builder output inference.

**71–80:** 71. Fluent generics; 72. Subclass fluent APIs; 73. `this` return; 74. Generic `this`; 75. Immutable return objects; 76. Snapshot builders; 77. Forking builder state; 78. Reusable fragments; 79. Composition; 80. Extension.

**81–90:** 81. Ergonomics vs safety; 82. Error complexity; 83. IntelliSense experience; 84. Method discoverability; 85. Excess generic state; 86. Compiler performance; 87. Simplifying state; 88. Runtime validation still required; 89. External data; 90. Trust boundaries.

**91–100:** 91. Type-state testing; 92. Valid sequence tests; 93. Invalid sequence tests; 94. Expected errors; 95. Refactoring states; 96. Documentation; 97. Public API stability; 98. Practical limitations; 99. Builder architecture; 100. Type-state mastery.

### Quiz — 40 preguntas

1. ¿Qué es fluent API? 2. ¿Qué es builder? 3. ¿Qué es type-state? 4. ¿Cuál es la diferencia entre compile-time state y runtime state? 5. ¿Cómo usar generic para representar estado? 6. ¿Qué es phantom state? 7. ¿Qué es transition return type? 8. ¿Cómo impedir una llamada antes de tiempo? 9. ¿Qué es conditional method availability? 10. ¿Qué significa remove-after-use?

2. ¿Cómo rastrear required fields? 12. ¿Cómo calcular remaining keys? 13. ¿Qué papel tiene Exclude? 14. ¿Cuándo habilitar `build()`? 15. ¿Qué es accumulating object? 16. ¿Cómo intersections pueden acumular propiedades? 17. ¿Cómo evitar duplicate key? 18. ¿Cómo preservar literal values? 19. ¿Qué es builder output inference? 20. ¿Qué es immutable builder?

3. ¿Qué es mutable builder? 22. ¿Qué ventaja tiene immutable? 23. ¿Qué significa fork builder? 24. ¿Cómo extender un builder? 25. ¿Qué es schema builder? 26. ¿Qué es pipeline builder? 27. ¿Qué es state-machine builder? 28. ¿Qué problema tienen demasiados generics? 29. ¿Cómo afecta IntelliSense? 30. ¿Qué es safety/ergonomics tradeoff?

4. ¿El type-state elimina validación runtime? 32. ¿Por qué no para external input? 33. ¿Qué es trust boundary? 34. ¿Cómo probar secuencias inválidas? 35. ¿Para qué sirve @ts-expect-error? 36. ¿Qué significa public API stability? 37. ¿Cómo simplificar estados? 38. ¿Cuándo builder es overengineering? 39. ¿Cuándo aporta valor? 40. Diseña un request builder con pasos obligatorios.

### Examen práctico

Construye un builder donde `build()` no exista hasta completar todos los campos obligatorios y donde ciertas operaciones solamente puedan ejecutarse una vez.

### Proyecto

## **Compile-Time Type-State Builder**

### Criterio de dominio

Una secuencia inválida de configuración debe provocar error **antes de runtime**.

---

# MÓDULO 44 — Type-Safe DSLs, parsers y lenguajes a nivel de tipos

### Qué aprenderás

Combinarás template literals, recursion, `infer`, tuples y conditional types para construir pequeños lenguajes estáticamente verificados.

### Por qué debes aprenderlo

Es uno de los niveles más avanzados del sistema de tipos de TypeScript y enseña a combinar prácticamente todas sus herramientas.

### Al finalizar podrás

Diseñar DSLs moderadas cuya gramática se interprete durante el type checking.

### 100 temas

**1–10:** 1. DSL concept; 2. Domain-specific language; 3. Type-level parser; 4. Grammar concept; 5. Tokens; 6. Delimiters; 7. Parsing strings; 8. Template literals; 9. Recursive conditionals; 10. `infer`.

**11–20:** 11. Prefix parser; 12. Suffix parser; 13. Split; 14. Join; 15. Trim; 16. Replace; 17. ReplaceAll; 18. Tokenization; 19. Recursive token list; 20. Parsing termination.

**21–30:** 21. Route grammar; 22. Parameter markers; 23. Optional marker concept; 24. Wildcards; 25. Path segments; 26. Route parameter object; 27. Duplicate parameter handling; 28. Literal segments; 29. Invalid routes; 30. Route validation.

**31–40:** 31. Event grammar; 32. Namespace separator; 33. Event payload mapping; 34. Command grammar; 35. Command arguments; 36. Permission strings; 37. Resource/action syntax; 38. Key paths; 39. Dot-path parser; 40. Nested property resolution.

**41–50:** 41. Format string grammar; 42. Placeholder detection; 43. Placeholder type mapping; 44. Typed formatter; 45. Number placeholder; 46. String placeholder; 47. Boolean placeholder; 48. Argument tuple generation; 49. Arity checking; 50. Format validation.

**51–60:** 51. Query-like DSL concept; 52. Selector tokens; 53. Field names; 54. Operators; 55. Value categories; 56. Schema validation; 57. Key existence; 58. Operator compatibility; 59. Result projection; 60. Query result inference.

**61–70:** 61. Parser result union; 62. Success type; 63. Failure type; 64. Error information; 65. Error position concept; 66. Remaining input; 67. Recursive parser state; 68. Token accumulators; 69. Parser combinator concepts; 70. Composition.

**71–80:** 71. Tuple-based parser; 72. Character tuple concept; 73. String recursion; 74. Grammar recursion; 75. Nested syntax; 76. Parentheses concept; 77. Depth tracking; 78. State tracking; 79. Lookahead concept; 80. Complexity explosion.

**81–90:** 81. Compiler performance; 82. Union explosion; 83. Instantiation depth; 84. Input length limits; 85. Error readability; 86. Grammar simplification; 87. AOT generation alternative; 88. Runtime parser alternative; 89. Hybrid static/runtime validation; 90. Practical DSL scope.

**91–100:** 91. DSL documentation; 92. Grammar tests; 93. Valid examples; 94. Invalid examples; 95. Regression tests; 96. Versioning grammar; 97. Backwards compatibility; 98. Developer ergonomics; 99. Knowing when to stop; 100. Type-level DSL mastery.

### Quiz — 40 preguntas

1. ¿Qué es DSL? 2. ¿Qué es type-level parser? 3. ¿Qué herramientas principales usarías? 4. ¿Qué es grammar? 5. ¿Qué es token? 6. ¿Qué es delimiter? 7. ¿Cómo Split usa infer? 8. ¿Qué es recursion termination? 9. ¿Cómo parsear route param? 10. ¿Cómo generar objeto de parámetros?

2. ¿Qué es format string parser? 12. ¿Cómo derivar argument tuple? 13. ¿Qué es arity checking? 14. ¿Cómo comprobar key existence? 15. ¿Qué es result projection? 16. ¿Qué es parser success type? 17. ¿Qué es failure type? 18. ¿Cómo incluir información de error? 19. ¿Qué es remaining input? 20. ¿Qué es parser state?

3. ¿Qué es accumulator? 22. ¿Qué es parser combinator conceptualmente? 23. ¿Qué es lookahead? 24. ¿Qué es depth tracking? 25. ¿Qué es complexity explosion? 26. ¿Qué es union explosion? 27. ¿Qué es instantiation depth? 28. ¿Por qué limitar longitud? 29. ¿Cuándo usar runtime parser? 30. ¿Qué es hybrid validation?

4. ¿Qué significa AOT generation? 32. ¿Cuándo sería mejor? 33. ¿Por qué documentar grammar? 34. ¿Cómo testear invalid strings? 35. ¿Cómo versionar grammar? 36. ¿Qué es developer ergonomics? 37. ¿Puede una DSL de tipos ser demasiado inteligente? 38. ¿Qué síntomas lo indican? 39. ¿Cuándo parar? 40. Diseña la gramática de un sistema de permisos.

### Examen práctico

Implementa dos DSLs: un parser de rutas y un formatter cuyos argumentos se deriven automáticamente de los placeholders utilizados.

### Proyecto

## **Compile-Time DSL Engine**

### Criterio de dominio

Debes combinar recursion, template literals, infer, tuples y conditionals sin perder control de la complejidad.

---

# MÓDULO 45 — Testing de tipos y verificación de APIs TypeScript

### Qué aprenderás

Aprenderás a probar no solamente el comportamiento runtime, sino también qué código debe o no debe compilar.

### Por qué debes aprenderlo

Una librería TypeScript puede funcionar correctamente en runtime y aun así ofrecer tipos incorrectos.

### Al finalizar podrás

Construir suites de regresión para APIs de tipos.

### 100 temas

**1–10:** 1. Type testing; 2. Runtime tests vs type tests; 3. Positive type tests; 4. Negative type tests; 5. Compilation success; 6. Compilation failure; 7. Expected diagnostics; 8. Regression prevention; 9. Type API contracts; 10. Consumer-perspective testing.

**11–20:** 11. `@ts-expect-error`; 12. Expected failure; 13. Unused expect-error; 14. `@ts-ignore` difference; 15. Why expect-error is testable; 16. Error location; 17. Error intent; 18. Comment documentation; 19. Multiple errors per line; 20. Refactoring test cases.

**21–30:** 21. Assignability tests; 22. Function tests; 23. Generic inference tests; 24. Literal inference tests; 25. Overload tests; 26. Conditional utility tests; 27. Mapped utility tests; 28. Recursive utility tests; 29. Declaration tests; 30. Module-resolution tests.

**31–40:** 31. Type equality concept; 32. `Equal<A,B>` patterns; 33. `Expect<T>` patterns; 34. Assignable vs equal; 35. Bidirectional assignability; 36. `any` complications; 37. never complications; 38. Unknown complications; 39. Union normalization; 40. Structural equality limitations.

**41–50:** 41. Inference snapshots concept; 42. Expected return types; 43. Expected parameter types; 44. Hover-like inspection; 45. Generic instantiation checks; 46. Tuple checks; 47. Literal preservation tests; 48. Readonly tests; 49. Optionality tests; 50. Excess property tests.

**51–60:** 51. Consumer fixture projects; 52. tsconfig matrices; 53. Strict mode tests; 54. Different compiler options; 55. Different TypeScript versions concept; 56. Declaration consumer tests; 57. Package boundary tests; 58. Import tests; 59. ESM-like consumer concept; 60. CJS-like consumer concept.

**61–70:** 61. Public API regression; 62. Added exports; 63. Removed exports; 64. Signature changes; 65. Generic changes; 66. Declaration snapshots concept; 67. API report concept; 68. Compatibility matrices; 69. Type semantic versioning; 70. Consumer breakage.

**71–80:** 71. Test cases for overloads; 72. Ambiguous calls; 73. Invalid calls; 74. Inference edge cases; 75. Empty arrays; 76. Readonly arrays; 77. Literal objects; 78. Unions; 79. Never cases; 80. Any contamination cases.

**81–90:** 81. Compile-time performance tests; 82. Large unions; 83. Recursive types; 84. Instantiation stress; 85. Editor responsiveness concepts; 86. Type benchmark fixtures; 87. Baseline diagnostics; 88. Regression thresholds concept; 89. Test minimization; 90. Failure reproduction.

**91–100:** 91. Type test organization; 92. Naming cases; 93. Documentation through tests; 94. API examples as tests; 95. Negative examples; 96. CI concepts; 97. Release gates; 98. Library confidence; 99. Testing philosophy; 100. Type-testing mastery.

### Quiz — 40 preguntas

1. ¿Qué es type test? 2. ¿Qué diferencia tiene con runtime test? 3. ¿Qué es positive test? 4. ¿Qué es negative test? 5. ¿Qué hace @ts-expect-error? 6. ¿Qué ocurre si el error desaparece? 7. ¿Por qué eso es útil? 8. ¿Qué diferencia tiene con @ts-ignore? 9. ¿Qué es assignability test? 10. ¿Qué es inference test?

2. ¿Qué es type equality pattern? 12. ¿Es igualdad estructural trivial de implementar? 13. ¿Por qué any complica tests? 14. ¿Por qué never? 15. ¿Qué es consumer fixture? 16. ¿Por qué probar distintos tsconfigs? 17. ¿Qué es declaration consumer test? 18. ¿Qué es package-boundary test? 19. ¿Qué es public API regression? 20. ¿Qué cambios pueden romper consumers?

3. ¿Qué es compatibility matrix? 22. ¿Qué significa semantic versioning de tipos conceptualmente? 23. ¿Cómo probar overload? 24. ¿Por qué probar llamadas inválidas? 25. ¿Qué casos límite tienen empty arrays? 26. ¿Por qué probar readonly? 27. ¿Qué es any contamination test? 28. ¿Qué es type performance test? 29. ¿Cómo recursive types pueden degradar compilación? 30. ¿Qué es baseline?

4. ¿Qué es minimal failure reproduction? 32. ¿Cómo tests sirven como documentación? 33. ¿Qué es negative example? 34. ¿Qué es release gate? 35. ¿Por qué una librería necesita type tests además de runtime? 36. ¿Qué significa consumer perspective? 37. ¿Qué es literal preservation test? 38. ¿Qué es optionality test? 39. ¿Qué es excess-property test? 40. Diseña suite para un generic builder.

### Examen práctico

Crea al menos 100 pruebas de tipos para las utilities y APIs creadas en módulos anteriores, incluyendo casos que deben compilar y casos que deben fallar.

### Proyecto

## **TypeScript Compile-Time Test Suite**

### Criterio de dominio

Tus tipos deben estar respaldados por pruebas igual que el comportamiento runtime.

---

# PARTE VIII — RENDIMIENTO, COMPILADOR Y TOOLING

# MÓDULO 46 — Declaration Emit avanzado y diseño de APIs públicas

### Qué aprenderás

Analizarás cómo TypeScript transforma una codebase en declarations consumibles.

### Por qué debes aprenderlo

Los tipos internos de una librería pueden ser excelentes y aun así producir `.d.ts` difíciles o imposibles de consumir.

### Al finalizar podrás

Diseñar código fuente teniendo en cuenta la calidad de la declaration API emitida.

### 100 temas

**1–10:** 1. Declaration emit pipeline; 2. Export reachability; 3. Public symbols; 4. Private symbols; 5. Type serialization; 6. Declaration printer concept; 7. Inferred public types; 8. Explicit public types; 9. Named types; 10. Anonymous types.

**11–20:** 11. Portable type names; 12. Non-portable inference; 13. External dependency types; 14. Internal dependency types; 15. Declaration naming; 16. Import generation; 17. Type-only imports; 18. Re-exported declarations; 19. Alias preservation concepts; 20. Type expansion.

**21–30:** 21. `declaration`; 22. `emitDeclarationOnly`; 23. `declarationMap`; 24. Map sources; 25. Navigation; 26. Debugging declarations; 27. Declaration-only builds; 28. Build separation; 29. Source + declarations; 30. Output organization.

**31–40:** 31. `stripInternal` concept; 32. Internal annotations; 33. Public API filtering; 34. Limitations; 35. Explicit exports preferred; 36. Private helpers; 37. Internal symbols; 38. Public dependencies; 39. Accidental exposure; 40. Export audits.

**41–50:** 41. Generic declarations; 42. Conditional declarations; 43. Mapped declarations; 44. Recursive declarations; 45. Readability; 46. Simplification aliases; 47. Stable names; 48. Error display; 49. Consumer hovers; 50. API comprehensibility.

**51–60:** 51. Class declaration emit; 52. Constructor surface; 53. Private members; 54. Protected members; 55. Static members; 56. Interfaces; 57. Type aliases; 58. Functions; 59. Overloads; 60. Constants.

**61–70:** 61. Const object declarations; 62. Literal preservation; 63. `as const` declaration output; 64. Huge literal types; 65. Widening public outputs; 66. Intentional abstraction; 67. Hiding implementation literals; 68. Public unions; 69. Public enums; 70. Public brands.

**71–80:** 71. Barrel effects; 72. Entry-point declarations; 73. Subpath declarations; 74. Declaration bundles concept; 75. Individual declaration files; 76. Import paths inside d.ts; 77. Package relocation; 78. Consumer resolution; 79. Cross-package declarations; 80. Project References output.

**81–90:** 81. API extraction concepts; 82. Declaration snapshots; 83. Diffing APIs; 84. Breaking changes; 85. Compatibility review; 86. Public symbol inventory; 87. Stable generic names; 88. Deprecation comments; 89. Documentation comments; 90. JSDoc preservation.

**91–100:** 91. Declaration performance; 92. Large types; 93. Recursive declaration cost; 94. Consumer compile time; 95. Type simplification; 96. API boundaries; 97. Declaration quality checklist; 98. Library audits; 99. Consumer simulation; 100. Declaration emit mastery.

### Quiz — 40 preguntas

1. ¿Qué es declaration emit? 2. ¿Qué es export reachability? 3. ¿Qué es public symbol? 4. ¿Qué es private symbol? 5. ¿Qué significa portable type name? 6. ¿Qué es non-portable inference? 7. ¿Por qué puede convenir anotar APIs públicas? 8. ¿Qué hace emitDeclarationOnly? 9. ¿Qué hace declarationMap? 10. ¿Qué es accidental exposure?

2. ¿Qué significa stripInternal conceptualmente? 12. ¿Por qué export discipline suele ser mejor? 13. ¿Cómo se emite una clase? 14. ¿Cómo afectan private members? 15. ¿Cómo se representan overloads? 16. ¿Qué ocurre con `as const` en declarations? 17. ¿Puede producir tipos enormes? 18. ¿Por qué widening intencional puede ser útil? 19. ¿Qué es entry-point declaration? 20. ¿Qué es subpath declaration?

3. ¿Qué problema pueden causar import paths internos? 22. ¿Qué es declaration snapshot? 23. ¿Qué es API diff? 24. ¿Qué indica breaking change? 25. ¿Cómo documentar deprecations? 26. ¿Se pueden conservar comentarios? 27. ¿Por qué imports type-only importan en declarations? 28. ¿Cómo Project References utilizan `.d.ts`? 29. ¿Qué es public symbol inventory? 30. ¿Qué es consumer simulation?

4. ¿Por qué declarations complejas afectan al consumidor? 32. ¿Qué es consumer compile time? 33. ¿Cómo simplificar tipos públicos? 34. ¿Por qué dar nombres a tipos complejos? 35. ¿Qué significa API comprehensibility? 36. ¿Qué es declaration quality? 37. ¿Cómo detectar leakage? 38. ¿Por qué revisar el `.d.ts` emitido? 39. ¿Qué no debes asumir del source code? 40. Diseña política de declarations.

### Examen práctico

Genera las declarations de una librería grande, audítalas manualmente y refactoriza el source hasta reducir complejidad accidental y leakage.

### Proyecto

## **Declaration API Audit**

### Criterio de dominio

Debes tratar el `.d.ts` generado como un producto público, no como un artifact irrelevante.

---

# MÓDULO 47 — Rendimiento del compilador y optimización de tipos

### Qué aprenderás

Aprenderás qué estructuras pueden hacer lento el type checking y cómo investigar problemas de rendimiento.

### Por qué debes aprenderlo

Los tipos extremadamente complejos pueden convertir una codebase segura en una codebase difícil de editar y compilar.

### Al finalizar podrás

Detectar y reducir cuellos de botella causados por arquitectura o metaprogramación excesiva.

### 100 temas

**1–10:** 1. Compiler performance; 2. Type checking cost; 3. Parsing cost; 4. Binding cost; 5. Checking cost; 6. Emit cost; 7. Incremental cost; 8. Editor latency; 9. Build latency; 10. Performance measurement.

**11–20:** 11. `--diagnostics`; 12. `--extendedDiagnostics`; 13. Files count; 14. Lines count; 15. Identifiers; 16. Symbols; 17. Types count; 18. Instantiations; 19. Memory usage; 20. Check time.

**21–30:** 21. `--listFiles`; 22. Unexpected files; 23. Library files; 24. Duplicate libraries; 25. Large inclusions; 26. `include`; 27. `exclude`; 28. Type roots; 29. Automatic types; 30. Project boundaries.

**31–40:** 31. Generic instantiation cost; 32. Conditional distributions; 33. Union explosion; 34. Intersection complexity; 35. Recursive types; 36. Deep recursion; 37. Template literal expansion; 38. Large mapped types; 39. Key remapping; 40. Nested utilities.

**41–50:** 41. Named intermediates; 42. Alias caching concepts; 43. Reusing types; 44. Flattened intersections; 45. Interface vs complex intersection considerations; 46. Base types; 47. Simpler constraints; 48. Reduced union size; 49. Early normalization; 50. Avoiding combinatorial types.

**51–60:** 51. Distributive conditional control; 52. Tuple wrappers; 53. Avoid unnecessary distribution; 54. Recursive base cases; 55. Depth limits; 56. Explicit recursion depth; 57. Accumulator strategies; 58. Tail-style patterns; 59. Fallback types; 60. Graceful degradation.

**61–70:** 61. Project References; 62. Smaller programs; 63. Declaration boundaries; 64. Build mode; 65. Incremental builds; 66. `.tsbuildinfo`; 67. Editor project sizes; 68. Shared packages; 69. Dependency graph; 70. Architectural performance.

**71–80:** 71. `skipLibCheck`; 72. What it saves; 73. What it hides; 74. Appropriate use; 75. Dependency duplication; 76. Conflicting types; 77. Upgrade strategies; 78. Declaration complexity; 79. Third-party costs; 80. Isolation strategies.

**81–90:** 81. Trace concepts; 82. Compiler tracing; 83. Performance profiling workflow; 84. Baselines; 85. Before/after measurement; 86. Reproducible benchmarks; 87. Cold vs incremental builds; 88. Editor vs CLI performance; 89. Regression detection; 90. Type performance tests.

**91–100:** 91. Clever types vs maintainable types; 92. User-facing latency; 93. IntelliSense latency; 94. Error latency; 95. Compile-time budget; 96. Type complexity budget; 97. Performance reviews; 98. Refactoring heavy types; 99. Practical optimization; 100. Performance mastery.

### Quiz — 40 preguntas

1. ¿Qué fases pueden consumir tiempo? 2. ¿Qué mide diagnostics? 3. ¿Qué aporta extendedDiagnostics? 4. ¿Qué significa instantiations? 5. ¿Qué indica check time? 6. ¿Cómo detectar archivos inesperados? 7. ¿Por qué include importa? 8. ¿Qué es union explosion? 9. ¿Por qué conditional distribution puede ser cara? 10. ¿Cómo detener distribution?

2. ¿Por qué recursive types pueden ralentizar? 12. ¿Qué es depth limit? 13. ¿Qué es combinatorial type? 14. ¿Por qué template literal puede explotar? 15. ¿Cómo ayudan named intermediates? 16. ¿Por qué simplificar intersections? 17. ¿Cómo reducir union size? 18. ¿Qué es graceful degradation? 19. ¿Por qué Project References pueden ayudar? 20. ¿Qué papel tiene `.tsbuildinfo`?

3. ¿Qué hace skipLibCheck? 22. ¿Qué no hace? 23. ¿Qué problemas puede esconder? 24. ¿Qué es baseline? 25. ¿Por qué medir antes y después? 26. ¿Qué es reproducible benchmark? 27. ¿Qué diferencia hay entre cold e incremental build? 28. ¿Por qué editor performance puede diferir de CLI? 29. ¿Qué es type performance test? 30. ¿Qué significa compile-time budget?

4. ¿Qué es complexity budget? 32. ¿Cuándo un tipo es demasiado inteligente? 33. ¿Qué síntomas experimenta el desarrollador? 34. ¿Qué es IntelliSense latency? 35. ¿Qué es error latency? 36. ¿Cómo refactorizarías un conditional enorme? 37. ¿Cuándo introducir fallback? 38. ¿Cuándo mover validación a runtime? 39. ¿Por qué rendimiento también es parte del diseño de tipos? 40. Diseña workflow de profiling.

### Examen práctico

Crea intencionalmente varias utilities costosas, mide su impacto y refactorízalas hasta demostrar una mejora cuantificable en diagnósticos.

### Proyecto

## **TypeScript Performance Laboratory**

### Criterio de dominio

Toda optimización debe estar respaldada por medición, no por intuición.

---

# MÓDULO 48 — Arquitectura del compilador, AST y Compiler API de forma version-aware

### Qué aprenderás

Estudiarás cómo un compilador TypeScript representa código, construye programas y realiza análisis.

### Por qué debes aprenderlo

Comprender internals mejora debugging, tooling, análisis estático y tu modelo mental del lenguaje.

### Al finalizar podrás

Navegar conceptos de AST y Compiler API verificando siempre la versión de TypeScript utilizada.

### 100 temas

**1–10:** 1. Compiler architecture; 2. Source text; 3. Lexer concept; 4. Tokens; 5. Parser; 6. Syntax tree; 7. AST; 8. Nodes; 9. Node kinds; 10. Source files.

**11–20:** 11. Syntax vs semantics; 12. Binding; 13. Symbols; 14. Scopes; 15. Declarations; 16. References; 17. Type checking; 18. Types; 19. Signatures; 20. Diagnostics.

**21–30:** 21. Program concept; 22. Compilation unit; 23. Source-file graph; 24. Compiler options; 25. Root files; 26. Dependency discovery; 27. Type checker concept; 28. Emit pipeline; 29. Declaration emit; 30. Incremental concepts.

**31–40:** 31. AST traversal; 32. Child nodes; 33. Parent relationships; 34. Node positions; 35. Source ranges; 36. Trivia concepts; 37. Comments; 38. Tokens vs nodes; 39. Syntax inspection; 40. AST viewers.

**41–50:** 41. Identifiers; 42. Declarations; 43. Variable statements; 44. Function declarations; 45. Class declarations; 46. Interface declarations; 47. Type aliases; 48. Import declarations; 49. Export declarations; 50. Expressions.

**51–60:** 51. Symbol table concept; 52. Symbol resolution; 53. Aliased symbols; 54. Declarations per symbol; 55. Type of symbol; 56. Type at location; 57. Signature extraction; 58. Return type concept; 59. Apparent types concept; 60. Type display.

**61–70:** 61. Diagnostics API concepts; 62. Syntactic diagnostics; 63. Semantic diagnostics; 64. Options diagnostics; 65. Declaration diagnostics; 66. Diagnostic locations; 67. Diagnostic formatting; 68. Error categories; 69. Codes; 70. Tooling output.

**71–80:** 71. Transform concepts; 72. Visitors; 73. Node factories concept; 74. Tree rewriting; 75. Printer concept; 76. Source transformation; 77. Code generation; 78. Source maps concept; 79. Preservation concerns; 80. Transform limitations.

**81–90:** 81. Compiler host concept; 82. File-system abstraction; 83. Reading files; 84. Writing files; 85. Virtual filesystems concept; 86. In-memory compilation; 87. Custom resolution concepts; 88. Host responsibilities; 89. Tooling architectures; 90. Build integrations.

**91–100:** 91. API version changes; 92. Unstable surfaces; 93. TypeScript 6-era APIs; 94. TypeScript 7 transition awareness; 95. Documentation verification; 96. Feature detection; 97. Adapter layers; 98. Version pinning; 99. Tool maintenance; 100. Compiler architecture mastery.

### Quiz — 40 preguntas

1. ¿Qué es AST? 2. ¿Qué hace parser? 3. ¿Qué es node? 4. ¿Qué es SyntaxKind conceptualmente? 5. ¿Qué es SourceFile? 6. ¿Qué diferencia hay entre syntax y semantics? 7. ¿Qué ocurre durante binding? 8. ¿Qué es symbol? 9. ¿Qué es declaration? 10. ¿Qué hace type checker?

2. ¿Qué es Program conceptualmente? 12. ¿Qué son root files? 13. ¿Cómo se descubre dependency graph? 14. ¿Qué es AST traversal? 15. ¿Qué son node positions? 16. ¿Qué son tokens? 17. ¿Cómo difieren de nodes? 18. ¿Qué es symbol resolution? 19. ¿Qué es aliased symbol? 20. ¿Qué significa type at location?

3. ¿Qué es signature? 22. ¿Qué es syntactic diagnostic? 23. ¿Qué es semantic diagnostic? 24. ¿Qué es declaration diagnostic? 25. ¿Qué es transform? 26. ¿Qué es visitor? 27. ¿Qué es tree rewriting? 28. ¿Qué es printer? 29. ¿Qué es compiler host? 30. ¿Por qué abstrae filesystem?

4. ¿Qué es in-memory compilation? 32. ¿Qué es custom host? 33. ¿Por qué Compiler API debe tratarse como version-sensitive? 34. ¿Qué significa version pinning? 35. ¿Qué es adapter layer? 36. ¿Por qué verificar documentación de la versión? 37. ¿Qué riesgo tiene copiar tutorial antiguo? 38. ¿Qué es tooling architecture? 39. ¿Cómo construirías un analyzer sin modificar código? 40. Explica pipeline del compilador.

### Examen práctico

Utiliza la API correspondiente a la versión de TypeScript de tu proyecto para recorrer un AST y generar un reporte de clases, interfaces, funciones, imports y exports.

### Proyecto

## **TypeScript Static Analyzer**

### Criterio de dominio

Debes comprender los conceptos del compilador independientemente de que nombres concretos de APIs cambien entre versiones.

---

# MÓDULO 49 — Language Service, tooling y análisis estático avanzado

### Qué aprenderás

Comprenderás cómo las herramientas obtienen información inteligente sobre una codebase TypeScript.

### Por qué debes aprenderlo

Autocomplete, rename, definitions, references y diagnostics forman parte esencial de la experiencia TypeScript.

### Al finalizar podrás

Diseñar herramientas conceptualmente similares a analyzers, refactors y asistentes de código.

### 100 temas

**1–10:** 1. Language Service concept; 2. Editor integration; 3. Incremental analysis; 4. Open files; 5. Project files; 6. Snapshots concept; 7. Versioned files; 8. Compiler options; 9. Project context; 10. Language intelligence.

**11–20:** 11. Diagnostics; 12. Syntactic diagnostics; 13. Semantic diagnostics; 14. Suggestion diagnostics concept; 15. Completions; 16. Completion entries; 17. Quick info; 18. Hover; 19. Signature help; 20. Parameter help.

**21–30:** 21. Definitions; 22. Type definitions; 23. Implementations; 24. References; 25. Rename; 26. Document highlights; 27. Navigation tree; 28. Outlining; 29. Symbols; 30. Workspace navigation concepts.

**31–40:** 31. Code fixes; 32. Quick fixes; 33. Refactors; 34. Extract function concept; 35. Extract constant; 36. Organize imports; 37. Add missing import; 38. Convert syntax concepts; 39. Rewrite safety; 40. Text changes.

**41–50:** 41. Language Service host concept; 42. File snapshots; 43. Script versions; 44. File existence; 45. Project versions; 46. Module resolution integration; 47. Compiler options integration; 48. Filesystem abstraction; 49. Incremental updates; 50. Caching.

**51–60:** 51. Project service concepts; 52. Configured projects; 53. Inferred projects; 54. External projects concept; 55. tsconfig discovery; 56. Project roots; 57. File ownership; 58. Multi-project files; 59. References integration; 60. Editor scalability.

**61–70:** 61. tsserver concepts; 62. Editor protocol concepts; 63. Requests; 64. Responses; 65. Events; 66. Synchronization; 67. File changes; 68. Diagnostics updates; 69. Logging; 70. Troubleshooting editor behavior.

**71–80:** 71. Plugin concepts; 72. Language Service plugins; 73. Completion customization concept; 74. Diagnostic customization concept; 75. Navigation customization; 76. Framework tooling concepts; 77. Embedded languages concepts; 78. Virtual files; 79. Generated TypeScript; 80. Mapping positions.

**81–90:** 81. Static analysis rules; 82. Semantic analyzers; 83. AST + checker; 84. Finding unsafe patterns; 85. Dependency analyzers; 86. API analyzers; 87. Refactoring tools; 88. Codemod concepts; 89. Migration tooling; 90. Source transformation safety.

**91–100:** 91. Tool version compatibility; 92. Compiler API differences; 93. Language Service API differences; 94. Adapter architectures; 95. Test fixtures; 96. Snapshot tests concepts; 97. Performance tests; 98. Tool distribution concepts; 99. Maintainability; 100. Tooling mastery.

### Quiz — 40 preguntas

1. ¿Qué es Language Service? 2. ¿Qué tipo de funciones proporciona? 3. ¿Qué es completion? 4. ¿Qué es quick info? 5. ¿Qué es signature help? 6. ¿Qué es definition? 7. ¿Qué diferencia tiene type definition? 8. ¿Qué es references? 9. ¿Qué es rename? 10. ¿Qué es code fix?

2. ¿Qué es refactor? 12. ¿Qué es text change? 13. ¿Qué es Language Service host? 14. ¿Qué es snapshot conceptualmente? 15. ¿Por qué existen versiones de archivos? 16. ¿Qué es incremental update? 17. ¿Qué es configured project? 18. ¿Qué es inferred project? 19. ¿Cómo se relaciona tsconfig? 20. ¿Qué es file ownership?

3. ¿Qué es tsserver conceptualmente? 22. ¿Cómo se comunica con editor conceptualmente? 23. ¿Qué son requests? 24. ¿Qué son events? 25. ¿Cómo diagnosticar problemas de editor? 26. ¿Qué es Language Service plugin? 27. ¿Qué es virtual file? 28. ¿Por qué frameworks pueden generar TypeScript virtual? 29. ¿Qué es mapping positions? 30. ¿Qué es semantic analyzer?

4. ¿Qué diferencia hay entre AST-only y checker-aware analyzer? 32. ¿Qué es codemod? 33. ¿Qué es migration tooling? 34. ¿Por qué source transformation debe ser cuidadosa? 35. ¿Qué significa version compatibility? 36. ¿Qué es adapter architecture? 37. ¿Cómo testear tooling? 38. ¿Por qué medir performance? 39. ¿Qué relación tiene este módulo con el Compiler API? 40. Diseña una herramienta de refactoring conceptual.

### Examen práctico

Crea una herramienta que analice un proyecto y encuentre símbolos, referencias, imports no deseados y determinados patrones de API.

### Proyecto

## **TypeScript Developer Tooling Engine**

### Criterio de dominio

Debes comprender cómo TypeScript pasa de “compilador” a convertirse en una plataforma de herramientas inteligentes.

---

# PARTE IX — NIVEL MASTER

# MÓDULO 50 — TYPESCRIPT MASTER ENGINEERING CAPSTONE

### Qué aprenderás

Integrarás los 49 módulos anteriores en una única codebase TypeScript diseñada como si fuera una librería profesional de gran escala.

### Por qué debes aprenderlo

Saber temas aislados no equivale a dominar TypeScript. Debes demostrar que puedes combinarlos sin producir una arquitectura imposible de mantener.

### Al finalizar podrás

Diseñar, implementar, documentar, probar y optimizar una arquitectura avanzada escrita exclusivamente con TypeScript.

### 100 temas

**1–10:** 1. Definición del dominio; 2. Requisitos; 3. Modelado type-first; 4. Domain invariants; 5. Public API; 6. Internal API; 7. Module boundaries; 8. Project graph; 9. Package-like boundaries; 10. Architecture decisions.

**11–20:** 11. Strict configuration; 12. Multiple tsconfigs; 13. Project References; 14. Composite projects; 15. Incremental builds; 16. Declaration emit; 17. Declaration maps; 18. Build outputs; 19. Resolution strategy; 20. Dependency direction.

**21–30:** 21. Primitive domain types; 22. Literal domains; 23. Branded identifiers; 24. Branded units; 25. Interfaces; 26. Type aliases; 27. Readonly models; 28. Discriminated unions; 29. Domain events; 30. State machines.

**31–40:** 31. Generic abstractions; 32. Generic constraints; 33. Const generics; 34. `NoInfer`; 35. `keyof`; 36. `typeof`; 37. Indexed access; 38. Mapped types; 39. Conditional types; 40. `infer`.

**41–50:** 41. Template literal types; 42. Recursive types; 43. Variadic tuples; 44. Deep utilities; 45. Type-level algorithms; 46. Route-like grammar; 47. Format-like grammar; 48. Builder states; 49. Fluent APIs; 50. Compile-time protocols.

**51–60:** 51. Type guards; 52. Assertion functions; 53. Unknown boundaries; 54. Runtime validation; 55. Parse-don't-cast; 56. Result types; 57. Exhaustiveness; 58. Never checks; 59. Error modeling; 60. Trust boundaries.

**61–70:** 61. Classes where appropriate; 62. Abstract classes where appropriate; 63. Mixins; 64. Composition; 65. Decorators where justified; 66. Iterators; 67. Generators; 68. Async iterators concepts; 69. Symbols; 70. Protocol-oriented APIs.

**71–80:** 71. Modules; 72. Type-only imports; 73. Public entry points; 74. `.d.ts`; 75. Declaration merging where justified; 76. Augmentation where justified; 77. Library declarations; 78. Consumer fixtures; 79. Compatibility; 80. API versioning.

**81–90:** 81. Type tests; 82. Positive cases; 83. Negative cases; 84. Compile-time assertions; 85. Runtime tests concepts; 86. Declaration tests; 87. Module-resolution tests; 88. Performance measurement; 89. Extended diagnostics; 90. Type complexity budgets.

**91–100:** 91. AST analyzer; 92. Static analysis; 93. API audit; 94. Documentation; 95. Architecture report; 96. Refactoring report; 97. Performance report; 98. Consumer experience review; 99. Final defense; 100. TypeScript mastery evaluation.

### Quiz final — 40 preguntas

1. ¿Cuál es la diferencia esencial entre TypeScript y runtime validation? 2. ¿Cómo modelarías una identidad nominal sobre structural typing? 3. ¿Cuándo preferirías interface sobre alias? 4. ¿Cuándo alias es necesario? 5. ¿Cómo modelarías estados mutuamente excluyentes? 6. ¿Cómo garantizarías exhaustividad? 7. ¿Cuándo usar unknown? 8. ¿Por qué evitar any? 9. ¿Qué representa never? 10. ¿Cómo construirías un type guard sound?

2. ¿Cómo correlacionarías una key con su value mediante generics? 12. ¿Qué hace `keyof`? 13. ¿Qué hace indexed access? 14. ¿Qué problema resuelven mapped types? 15. ¿Qué problema resuelven conditional types? 16. ¿Cuándo ocurre distribución? 17. ¿Cómo la detienes? 18. ¿Qué hace infer? 19. ¿Cómo funcionan template literal types? 20. ¿Cómo construirías un parser de rutas?

3. ¿Qué es recursive type? 22. ¿Cómo limitarías su profundidad? 23. ¿Qué es variadic tuple? 24. ¿Cómo tiparías pipe? 25. ¿Qué hace NoInfer? 26. ¿Qué ventaja tienen const type parameters? 27. ¿Qué es type-state? 28. ¿Cómo impedirías llamar build prematuramente? 29. ¿Qué es declaration file? 30. ¿Qué es module augmentation?

4. ¿Qué problema resuelven Project References? 32. ¿Cómo investigarías compilación lenta? 33. ¿Qué métricas mirarías? 34. ¿Qué es AST? 35. ¿Qué diferencia existe entre symbol y type? 36. ¿Qué es Language Service? 37. ¿Cómo probarías una API solamente de tipos? 38. ¿Cómo auditarías `.d.ts` públicos? 39. ¿Cómo decidirías si una abstracción type-level es demasiado compleja? 40. Explica cómo diseñarías una librería TypeScript profesional desde cero.

# EXAMEN MASTER DE TYPESCRIPT

Construye una biblioteca denominada:

```text
typescript-master-core/
```

con una arquitectura mínima similar a:

```text
typescript-master-core/
├── packages/
│   ├── core/
│   ├── types/
│   ├── domain/
│   ├── validation/
│   ├── state/
│   ├── events/
│   ├── builders/
│   ├── dsl/
│   ├── utilities/
│   ├── analyzer/
│   └── public-api/
│
├── tests/
│   ├── runtime/
│   ├── types/
│   ├── declarations/
│   └── consumers/
│
├── tsconfig.base.json
├── tsconfig.json
└── README.md
```

## Requisitos obligatorios del examen

El proyecto deberá demostrar dominio real de:

```text
strict TypeScript

Type inference

Literal Types

as const

satisfies

unknown

never

void

Object Types

readonly

Arrays

Tuples

Variadic Tuples

Interfaces

Type Aliases

Union Types

Intersection Types

Discriminated Unions

Functions

Function Types

Overloads

Call Signatures

Construct Signatures

Narrowing

Control Flow Analysis

Type Guards

Assertion Functions

Enums o alternativas enum-like

Symbols

unique symbol

Classes

Abstract Classes

Mixins

Generics

Generic Constraints

Generic Defaults

Const Type Parameters

NoInfer

keyof

typeof

Indexed Access Types

Mapped Types

Key Remapping

Conditional Types

Distributive Conditional Types

infer

Template Literal Types

Utility Types

Recursive Types

Deep Utility Types

Branded Types

Type-State

Builders

Fluent APIs

Type-Level Parsers

Type-Level Algorithms

Iterators

Generators

Modules

Module Resolution

Declaration Files

Declaration Emit

Declaration Merging

Module Augmentation

Project References

Composite Projects

Build Mode

Compile-Time Type Tests

Performance Diagnostics

AST Analysis
```

## Restricciones

No podrás resolver problemas simplemente escribiendo:

```ts
any
```

ni esconder errores indiscriminadamente mediante:

```ts
as SomeType
```

o:

```ts
// @ts-ignore
```

Toda assertion utilizada deberá tener una justificación técnica.

Las entradas externas deberán comenzar desde:

```ts
unknown
```

y pasar por una frontera explícita de validación.

Todos los proyectos deben utilizar:

```json
{
  "compilerOptions": {
    "strict": true
  }
}
```

Además deberás activar progresivamente flags estrictos adicionales estudiados durante el programa.

# PROYECTO FINAL — TYPESCRIPT MASTER CORE

El proyecto deberá implementar como mínimo los siguientes subsistemas.

## 1. Domain Type System

Sistema de tipos de dominio con:

```text
Branded IDs
Validated strings
Units
Currencies
Readonly entities
Domain events
Result types
State machines
```

## 2. Runtime Validation Layer

Entrada:

```ts
unknown
```

Salida únicamente después de validación:

```ts
ValidatedDomainObject
```

Deberás construir:

```text
primitive guards
object guards
array guards
tuple guards
union guards
assertion functions
recursive validators
```

## 3. Generic Utility Library

Implementarás tus propias versiones de:

```text
DeepPartial
DeepReadonly
DeepRequired
DeepMutable
DeepNonNullable
Flatten
Reverse
Zip
Take
Drop
Head
Tail
Last
Paths
PathValue
OnlyFunctions
OnlyProperties
```

## 4. Type-Safe Event System

Deberá ofrecer una experiencia similar a:

```ts
events.on("user.created", event => {
  // event debe inferirse automáticamente
});
```

sin:

```ts
any
```

y sin escribir manualmente el payload en cada callback.

## 5. Compile-Time State Machine

Ejemplo conceptual:

```text
Idle
  ↓
Loading
  ↓
Success
  ↓
Completed

Loading
  ↓
Failure
  ↓
Retrying
```

TypeScript deberá impedir determinadas transiciones inválidas.

## 6. Type-State Builder

Ejemplo conceptual:

```ts
builder
  .setName("John")
  .setEmail("john@example.com")
  .setRole("developer")
  .build();
```

`build()` solamente deberá estar disponible cuando la configuración requerida esté completa.

## 7. Type-Level Route Parser

De:

```ts
"/users/:userId/posts/:postId"
```

TypeScript deberá derivar:

```ts
{
  userId: string;
  postId: string;
}
```

sin escribir el objeto manualmente.

## 8. Typed Formatting DSL

De algo conceptualmente similar a:

```ts
format("User %s has %d points", name, points);
```

los tipos deberán verificar los argumentos requeridos por el formato.

## 9. Iteration Layer

Implementarás secuencias tipadas con:

```text
Iterator
Iterable
Generator
AsyncIterable
AsyncGenerator
```

y operaciones lazy.

## 10. Declaration API

El proyecto deberá producir declarations:

```text
.d.ts
```

auditables y consumibles desde un proyecto externo.

## 11. Project References

La arquitectura deberá utilizar múltiples:

```text
tsconfig.json
```

con:

```text
references
composite
incremental
declaration
```

y compilar correctamente mediante:

```bash
tsc --build
```

## 12. Type Testing

Deberás crear como mínimo:

```text
200 pruebas de tipos
```

incluyendo código que:

```text
debe compilar
```

y código que:

```text
NO debe compilar
```

utilizando comprobaciones intencionales.

## 13. Compiler Performance

Deberás analizar:

```bash
tsc --extendedDiagnostics
```

y documentar:

```text
files
types
instantiations
memory
check time
total time
```

según lo disponible en tu versión.

## 14. Static Analyzer

Crearás una herramienta basada en las APIs disponibles para tu versión de TypeScript capaz de analizar tu proyecto y generar información sobre:

```text
classes
interfaces
type aliases
functions
imports
exports
generics
any usage
type assertions
modules
```

## 15. API Audit

Finalmente deberás inspeccionar:

```text
public exports
generated declarations
module boundaries
dependency graph
consumer inference
error messages
compile-time performance
```

# DEFENSA FINAL DEL PROYECTO

No bastará con que el proyecto compile.

Deberás poder explicar verbalmente y sin consultar documentación:

```text
por qué utilizaste cada generic

por qué una estructura es interface o type

por qué utilizaste union o intersection

por qué un valor entra como unknown

dónde ocurre narrowing

dónde se utilizan type guards

qué estados son imposibles

cómo funciona tu exhaustiveness

cómo funciona tu builder

cómo funciona tu parser

dónde utilizas infer

dónde utilizas mapped types

dónde utilizas conditional types

dónde existe distribución

cómo funcionan tus recursive types

cómo funcionan tus variadic tuples

cómo se resuelven tus módulos

cómo se generan tus declarations

cómo funciona tu Project Reference graph

qué partes afectan al rendimiento del compilador

qué API es pública

qué API es interna
```

# CRITERIOS PARA CONSIDERAR DOMINADO EL MÓDULO 50

Debes cumplir simultáneamente:

* obtener mínimo **36/40** en el quiz final;
* completar el proyecto Master;
* compilar bajo configuración estricta;
* no depender de `any`;
* justificar todas las assertions;
* superar todas las pruebas positivas;
* superar todas las pruebas negativas;
* producir declarations válidas;
* compilar correctamente mediante Project References;
* demostrar que consumidores externos pueden utilizar la API;
* demostrar exhaustiveness;
* demostrar inferencia genérica;
* demostrar type-level programming;
* demostrar runtime validation;
* medir rendimiento del compilador;
* explicar tu arquitectura sin limitarte a repetir código.

---

# RUTA COMPLETA — TYPESCRIPT DE CERO A MASTER

Al finalizar los **50 módulos**, habrás recorrido:

```text
50 módulos
×
100 temas
=
5,000 temas de TypeScript
```

Además:

```text
50 quizzes
×
40 preguntas
=
2,000 preguntas de evaluación
```

más:

```text
50 exámenes prácticos
50 proyectos de módulo
1 proyecto Master
```

# MAPA COMPLETO DE LOS 50 MÓDULOS

## Nivel 1 — Fundamentos

```text
01. Introducción profesional a TypeScript
02. Toolchain y compilador
03. tsconfig.json
04. Tipos primitivos e inferencia
05. Literal Types, as const y satisfies
```

## Nivel 2 — Sistema de tipos fundamental

```text
06. any, unknown, never, void, null y undefined
07. Object Types
08. Arrays y Tuples
09. Type Aliases e Interfaces
10. Union e Intersection Types
```

## Nivel 3 — Funciones y Narrowing

```text
11. Funciones Type-Safe
12. Overloads y firmas avanzadas
13. Narrowing y Control Flow Analysis
14. Type Guards y Assertion Functions
15. Enums, Symbols y constantes tipadas
```

## Nivel 4 — Clases y Generics

```text
16. Clases TypeScript
17. Herencia, abstracción y polimorfismo
18. Generics
19. Generic Constraints
20. keyof, typeof e Indexed Access Types
```

## Nivel 5 — Type Manipulation

```text
21. Mapped Types
22. Conditional Types
23. infer
24. Template Literal Types
25. Utility Types
```

## Nivel 6 — Type-Level Programming

```text
26. Recursive Types
27. Branded Types
28. Discriminated Unions y State Machines
29. Type Compatibility y Variance
30. Modules y organización
```

## Nivel 7 — Librerías y arquitectura

```text
31. Module Resolution
32. Declaration Files
33. Library Type Design
34. Declaration Merging y Augmentation
35. Mixins
```

## Nivel 8 — Metaprogramación y ecosistema

```text
36. Decorators
37. Iterators y Generators
38. JSX Type System
39. JavaScript + JSDoc Interop
40. Project References
```

## Nivel 9 — Type-Level Engineering avanzado

```text
41. Variadic Tuple Algorithms
42. Generic Inference Engineering
43. Type-State y Builders
44. Type-Safe DSLs y Parsers
45. Type Testing
```

## Nivel 10 — Ingeniería TypeScript Master

```text
46. Declaration Emit avanzado
47. Compiler Performance
48. Compiler Architecture y AST
49. Language Service y Tooling
50. TypeScript Master Engineering Capstone
```

# OBJETIVO FINAL

Al terminar esta ruta no deberías limitarte a saber:

```ts
const name: string = "John";
```

o:

```ts
interface User {
  id: number;
  name: string;
}
```

El objetivo es que seas capaz de comprender y diseñar estructuras como:

```ts
type DeepReadonly<T> =
    T extends (...args: any[]) => unknown
        ? T
        : T extends readonly [infer Head, ...infer Tail]
            ? readonly [
                DeepReadonly<Head>,
                ...DeepReadonly<Tail>
              ]
            : T extends readonly (infer Item)[]
                ? readonly DeepReadonly<Item>[]
                : T extends object
                    ? {
                        readonly [K in keyof T]:
                            DeepReadonly<T[K]>
                      }
                    : T;
```

pero también saber cuándo **no** deberías crear algo así.

El verdadero nivel Master no consiste en escribir el tipo más complicado posible.

Consiste en saber elegir entre:

```text
inference

explicit annotations

generics

unions

interfaces

mapped types

conditional types

runtime validation

simple code
```

según el problema real.

La meta final de estos **5,000 temas** es llegar a un punto donde puedas:

```text
leer TypeScript avanzado;

diseñar TypeScript avanzado;

debuggear TypeScript avanzado;

crear librerías TypeScript;

diseñar APIs type-safe;

crear tus propios utility types;

construir state machines;

crear DSLs;

escribir declaration files;

optimizar proyectos TypeScript grandes;

comprender errores genéricos complejos;

trabajar con el AST;

crear herramientas sobre TypeScript;

y, sobre todo, escribir código mantenible.
```

Con esto queda terminada la estructura completa:

# **TYPESCRIPT — 50 MÓDULOS × 100 TEMAS — DE CERO A MASTER**

sin mezclar React, Node.js, Next.js, NestJS, bases de datos, Docker, Kubernetes, cloud u otras tecnologías que tendrán posteriormente sus propios programas independientes.

Con esto ya puedes unir directamente **Módulos 1–30 + 31–50** y tener el `README.md` maestro completo del currículo de **5,000 temas de TypeScript**.

[1]: https://www.typescriptlang.org/docs/handbook/project-references?utm_source=chatgpt.com "TypeScript: Documentation - Project References"
