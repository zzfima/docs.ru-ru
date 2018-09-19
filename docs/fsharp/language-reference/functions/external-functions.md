---
title: Внешние функции (F#)
description: 'Сведения о поддержке языка F # для вызова функций в машинном коде.'
ms.date: 05/16/2016
ms.openlocfilehash: db0d3362d867b07b333951f3380c6735ff471d5e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45973109"
---
# <a name="external-functions"></a>Внешние функции

В этом разделе описывается поддержка языка F # для вызова функций в машинном коде.

## <a name="syntax"></a>Синтаксис

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *аргументы* представляет аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибута. Первым аргументом является строка, представляющая имя библиотеки DLL, содержащий данную функцию, без расширения DLL. Дополнительные аргументы, которые могут быть представлены для всех открытых свойств `System.Runtime.InteropServices.DllImportAttribute` класса, например соглашение о вызовах.

Предположим, что у вас есть собственный библиотеки DLL на C++, содержащий следующую экспортированную функцию.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Эту функцию можно вызвать из F #, используя следующий код.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Взаимодействие с машинным кодом называется *неуправляемого* и входит в состав среды CLR. Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../../docs/framework/interop/index.md). Информация в этом разделе применима к F #.

## <a name="see-also"></a>См. также

- [Функции](index.md)
