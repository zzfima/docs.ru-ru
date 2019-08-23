---
title: Внешние функции
description: Сведения о F# языковой поддержке для вызова функций в машинном коде.
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968734"
---
# <a name="external-functions"></a>Внешние функции

В этом разделе F# описывается языковая поддержка для вызова функций в машинном коде.

## <a name="syntax"></a>Синтаксис

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *аргументы* представляют аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибуту. Первым аргументом является строка, представляющая имя библиотеки DLL, содержащей эту функцию, без расширения DLL. Дополнительные аргументы могут быть указаны для любого из открытых свойств `System.Runtime.InteropServices.DllImportAttribute` класса, например соглашения о вызовах.

Предположим, что у вас C++ есть собственная библиотека DLL, содержащая следующую экспортированную функцию.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Эту функцию можно вызвать из F# с помощью следующего кода.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Взаимодействие с машинным кодом называется *вызовом* неуправляемого кода и является функцией среды CLR. Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../framework/interop/index.md). Сведения в этом разделе применимы к F#.

## <a name="see-also"></a>См. также

- [Функции](index.md)
