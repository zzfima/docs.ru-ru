---
title: Внешние функции
description: Дополнительные сведения о F# языковая поддержка для вызова функций в машинном коде.
ms.date: 05/16/2016
ms.openlocfilehash: 86ea78844fb812361233f8360c377465d83be203
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934632"
---
# <a name="external-functions"></a>Внешние функции

В этом разделе описывается F# языковая поддержка для вызова функций в машинном коде.

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

Вы сможете вызвать эту функцию из F# , используя следующий код.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Взаимодействие с машинным кодом называется *неуправляемого* и входит в состав среды CLR. Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../../docs/framework/interop/index.md). Информация в этом разделе применима к F#.

## <a name="see-also"></a>См. также

- [Функции](index.md)