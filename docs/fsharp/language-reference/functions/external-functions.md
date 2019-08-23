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
# <a name="external-functions"></a><span data-ttu-id="b77ee-103">Внешние функции</span><span class="sxs-lookup"><span data-stu-id="b77ee-103">External Functions</span></span>

<span data-ttu-id="b77ee-104">В этом разделе F# описывается языковая поддержка для вызова функций в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="b77ee-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="b77ee-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b77ee-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="b77ee-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b77ee-106">Remarks</span></span>

<span data-ttu-id="b77ee-107">В приведенном выше синтаксисе *аргументы* представляют аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибуту.</span><span class="sxs-lookup"><span data-stu-id="b77ee-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="b77ee-108">Первым аргументом является строка, представляющая имя библиотеки DLL, содержащей эту функцию, без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="b77ee-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="b77ee-109">Дополнительные аргументы могут быть указаны для любого из открытых свойств `System.Runtime.InteropServices.DllImportAttribute` класса, например соглашения о вызовах.</span><span class="sxs-lookup"><span data-stu-id="b77ee-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="b77ee-110">Предположим, что у вас C++ есть собственная библиотека DLL, содержащая следующую экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="b77ee-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="b77ee-111">Эту функцию можно вызвать из F# с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="b77ee-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="b77ee-112">Взаимодействие с машинным кодом называется *вызовом* неуправляемого кода и является функцией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b77ee-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="b77ee-113">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="b77ee-113">For more information, see [Interoperating with Unmanaged Code](../../../framework/interop/index.md).</span></span> <span data-ttu-id="b77ee-114">Сведения в этом разделе применимы к F#.</span><span class="sxs-lookup"><span data-stu-id="b77ee-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="b77ee-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b77ee-115">See also</span></span>

- [<span data-ttu-id="b77ee-116">Функции</span><span class="sxs-lookup"><span data-stu-id="b77ee-116">Functions</span></span>](index.md)
