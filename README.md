Kernel source file style guide (KNF)
====================================

Этот файл определяет предпочтительный стиль исходных файлов ядра в дереве
исходных текстов OpenBSD. Он также является руководством по предпочтительному
стилю кода пользовательского пространства. Этим рекомендациям следует следовать
для всего нового кода. В общем случае, код можно считать "новым", если он
составляет около 50% или более от общего объема файла(ов). Этого достаточно,
чтобы отказаться от прецедентов в существующем коде и использовать текущее
руководство по стилю.

```
/*
 * Style guide for the OpenBSD KNF (Kernel Normal Form).
 */

/*
 * VERY important single-line comments look like this.
 */

/* Most single-line comments look like this. */

/*
 * Multi-line comments look like this.  Make them real sentences.
 * Fill them so they look like real paragraphs.
 */
```

На первом месте стоят включаемые файлы ядра (т.е. __<sys/*.h>__); обычно
требуется
__<sys/types.h>__ ИЛИ __<sys/param.h>__, но не оба! __<sys/types.h>__ включает
__<sys/cdefs.h>__, и от него можно зависеть.

```
#include <sys/types.h>   /* Non-local includes in brackets. */
```

Если это сетевая программа, поместите сетевые включаемые файлы рядом.

```
#include <net/if.h>
#include <net/if_dl.h>
#include <net/route.h>
#include <netinet/in.h>
```
