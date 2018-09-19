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
# <a name="external-functions"></a><span data-ttu-id="f7aa2-103">Внешние функции</span><span class="sxs-lookup"><span data-stu-id="f7aa2-103">External Functions</span></span>

<span data-ttu-id="f7aa2-104">В этом разделе описывается поддержка языка F # для вызова функций в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="f7aa2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7aa2-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="f7aa2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7aa2-106">Remarks</span></span>

<span data-ttu-id="f7aa2-107">В приведенном выше синтаксисе *аргументы* представляет аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибута.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="f7aa2-108">Первым аргументом является строка, представляющая имя библиотеки DLL, содержащий данную функцию, без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="f7aa2-109">Дополнительные аргументы, которые могут быть представлены для всех открытых свойств `System.Runtime.InteropServices.DllImportAttribute` класса, например соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="f7aa2-110">Предположим, что у вас есть собственный библиотеки DLL на C++, содержащий следующую экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="f7aa2-111">Эту функцию можно вызвать из F #, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="f7aa2-112">Взаимодействие с машинным кодом называется *неуправляемого* и входит в состав среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="f7aa2-113">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="f7aa2-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="f7aa2-114">Информация в этом разделе применима к F #.</span><span class="sxs-lookup"><span data-stu-id="f7aa2-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7aa2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f7aa2-115">See also</span></span>

- [<span data-ttu-id="f7aa2-116">Функции</span><span class="sxs-lookup"><span data-stu-id="f7aa2-116">Functions</span></span>](index.md)
