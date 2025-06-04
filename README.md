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