# Uso de defineAsyncComponent
La función defineAsyncComponent permite encapsular un componente dinámico. Este se carga únicamente cuando Vue lo necesita en tiempo de ejecución. Se puede usar de manera simple (solo con import) o compleja (envolviendo el import en una promesa con retrasos simulados u otras condiciones).

En su forma simple, el componente se importa tan pronto como se requiere, lo que es ideal para producción.

En su forma extendida, se puede retrasar intencionalmente la carga (por ejemplo, usando setTimeout) para simular una carga lenta, útil en prototipos o para mostrar una pantalla de bienvenida temporal.

# Uso de <Suspense> con defineAsyncComponent
Vue proporciona la etiqueta <Suspense> para manejar la carga de componentes asíncronos de manera elegante. Esta etiqueta permite definir dos secciones:

#default: es el contenido principal. Aquí se renderiza el componente una vez que ya ha sido cargado completamente.

#fallback: es el contenido alternativo que se muestra mientras el componente principal aún se está cargando.

Esto mejora la experiencia del usuario, mostrando una pantalla o animación (como un splash screen o spinner) mientras se resuelve el componente.

# Consideraciones
El fallback se mostrará automáticamente si el componente tarda en cargarse (ya sea por red lenta o por un retardo forzado).

Si la carga es muy rápida, el fallback puede no verse, ya que el componente asíncrono estará disponible casi de inmediato.

El uso de Suspense es opcional pero altamente recomendable para manejar componentes asíncronos de forma más controlada y visualmente fluida.

# Funcionalidad del Layout
En este proyecto se emplea un enfoque de composición basada en layouts para estructurar las vistas. El componente Layout.vue actúa como contenedor base que organiza y distribuye otras partes visuales de la interfaz, como cabeceras, contenido, pies de página u otras secciones. Esto permite mantener el código más ordenado, reutilizable y fácil de escalar.

# ¿Qué es Layout.vue?
Layout.vue es un componente que define la estructura general de una página. Su función principal es proporcionar una plantilla envolvente, dentro de la cual se colocan diferentes secciones usando slots. Estos espacios funcionan como puntos de inserción para que otros componentes puedan colocarse en la estructura del layout sin modificarlo directamente.

# ¿Qué es #header?
Dentro del componente Layout.vue, se utiliza un slot con nombre llamado header. Un slot nombrado es una funcionalidad de Vue que permite insertar contenido personalizado en lugares específicos de un componente.

En este caso, #header hace referencia a un slot reservado para la cabecera de la vista. Cuando el componente Layout es usado desde otra vista o componente, se puede insertar un componente específico (como Header.vue) en ese lugar usando la directiva v-slot:#header o, como en este caso, la sintaxis abreviada #header dentro del <template>.

Esto hace que el contenido del Header.vue se coloque exactamente donde el slot header fue definido dentro de Layout.vue.