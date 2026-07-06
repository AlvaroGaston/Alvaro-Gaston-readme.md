1. ¿Qué es Extreme Programming (XP) y cuál es su objetivo principal?
   Extreme Programming (XP) es la metodología ágil más enfocada en la calidad técnica del código. Su objetivo es simple: entregar software de altísima calidad que responda rápidamente a los cambios del cliente. Para lograrlo, lleva al "extremo" las buenas prácticas de la ingeniería de software, aplicándolas de forma intensiva en ciclos de desarrollo muy cortos.

2. ¿Cuáles son los cinco valores principales de XP?

- **Comunicación:** Charla constante y cara a cara entre todos: desarrolladores y cliente. El objetivo es eliminar los malentendidos.
- **Simplicidad:** Hacer siempre lo más simple que funcione. No agregar complejidad pensando en un futuro incierto ("No lo vas a necesitar" o YAGNI).
- **Retroalimentación (Feedback):** Obtener respuestas lo más rápido posible. Del sistema, a través de pruebas que se ejecutan en segundos. Del cliente, a través de entregas frecuentes.
- **Valentía:** Tener el coraje de tirar a la basura código que no sirve, de refactorizar sin miedo (gracias a las pruebas) y de decir la verdad sobre el estado del proyecto.
- **Respeto:** Respetar a los compañeros, sus opiniones y su trabajo. Un equipo donde hay respeto es un equipo donde todos se sienten seguros para aportar y colaborar.

3. ¿Por qué XP considera que las pruebas son un elemento fundamental?
   Porque en XP, las pruebas son la red de seguridad que permite moverse rápido. El código cambia todo el tiempo, y las pruebas automatizadas son la garantía de que un cambio no rompió algo que antes funcionaba. Sin esta red, el equipo no tendría la "valentía" para refactorizar y mejorar el código constantemente.

4. ¿Qué es Test Driven Development (TDD) y cómo se relaciona con XP?
   TDD (Desarrollo Guiado por Pruebas) es un ciclo: primero, escribes una prueba para una funcionalidad que aún no existe (la prueba, obviamente, falla). Segundo, escribes el código más simple posible para que esa prueba pase. Tercero, refactorizas y limpias el código. TDD es una práctica central de XP porque obliga a que todo el código nazca con una prueba asociada y promueve diseños simples.

5. ¿Qué es Pair Programming? Ventajas y dificultad.
   Es la práctica de que dos programadores trabajen juntos en una sola computadora. Uno es el "conductor" (escribe el código) y el otro es el "navegador" (piensa en la estrategia, revisa y sugiere).

- **Ventajas:** El código resultante tiene muchísima más calidad (cuatro ojos ven más que dos) y es una forma increíble de compartir conocimiento en el equipo.
- **Dificultad:** Requiere mucha concentración y puede ser agotador. También pueden surgir roces si los estilos de programación son muy diferentes, por lo que exige una buena dosis de "respeto".

6. ¿Qué son las historias de usuario y por qué se prefieren?
   Son descripciones cortas de una funcionalidad, escritas desde la perspectiva del usuario. Por ejemplo: "Como cliente, quiero poder ver mi saldo para saber cuánta plata tengo". Se prefieren a los documentos de requisitos largos porque son una "promesa de conversación": no especifican todos los detalles, sino que invitan al diálogo entre el cliente y los desarrolladores. Son fáciles de entender, estimar y priorizar.

7. ¿Qué es Continuous Integration (CI) y qué beneficios aporta?
   Es la práctica de que cada desarrollador integre su trabajo al repositorio principal varias veces al día. Cada vez que se integra, un sistema automático compila el código y corre todas las pruebas. Su principal beneficio es que los errores de integración se detectan al instante, evitando el "infierno" de intentar juntar el trabajo de todo el equipo al final del proyecto.

8. ¿Cómo se aplica el concepto de Weekly Cycle en XP?
   El ciclo de trabajo en XP es de una semana. Al inicio de la semana, el cliente elige las historias de usuario que más valor le aportan. El equipo las estima y se compromete a terminarlas. Al final de la semana, se le muestra al cliente el software funcionando con esas nuevas características. Este ciclo tan corto permite una retroalimentación constante y una adaptación muy rápida.

9. Fijar tiempo, costo y calidad, y negociar el alcance.
   Este es un principio clave de XP. En un proyecto, se fijan tres variables: el tiempo (la fecha de entrega), el costo (el equipo) y la calidad (siempre alta). La única variable que se negocia es el alcance (la cantidad de funcionalidades).

- **Ejemplo:** Si tenemos un mes para terminar un proyecto con un presupuesto fijo, y la calidad no se negocia, ¿qué pasa si el trabajo es más de lo que pensábamos? En lugar de pedirle al equipo que trabaje fines de semana (lo que baja la calidad) o de entregar algo mal hecho, se habla con el cliente y se decide qué funcionalidades (historias de usuario) menos importantes se pueden dejar para una próxima entrega.

10. Aplicación de tres prácticas de XP en un proyecto real.

- **Pair Programming:** Usarlo para desarrollar una parte crítica del sistema, como el procesador de pagos. La lógica es tan delicada que tener a dos personas pensando juntas reduce drásticamente la posibilidad de un bug costoso.
- **Refactoring:** Después de agregar una nueva funcionalidad, el equipo nota que hay código duplicado. Dedican un par de horas a refactorizarlo (limpiarlo y unificarlo) para que el sistema siga siendo fácil de mantener.
- **Small Releases (Entregas Pequeñas):** En lugar de un gran lanzamiento en 6 meses, el equipo entrega una nueva versión funcional al cliente cada dos semanas. Esto permite obtener feedback real del mercado y ajustar la estrategia sobre la marcha.
