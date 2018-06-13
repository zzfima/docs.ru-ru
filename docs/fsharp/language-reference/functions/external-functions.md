---
title: Внешние функции (F#)
description: 'Дополнительные сведения о поддержке языка F # для вызова функции в машинный код.'
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564486"
---
# <a name="external-functions"></a><span data-ttu-id="b2ba0-103">Внешние функции</span><span class="sxs-lookup"><span data-stu-id="b2ba0-103">External Functions</span></span>

<span data-ttu-id="b2ba0-104">В этом разделе описывается поддержка языка F # для вызова функции в машинный код.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2ba0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2ba0-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="b2ba0-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2ba0-106">Remarks</span></span>

<span data-ttu-id="b2ba0-107">В предыдущем синтаксисе *аргументы* представляет аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибута.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="b2ba0-108">Первым аргументом является строка, представляющая имя библиотеки DLL, содержащей эту функцию без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="b2ba0-109">Дополнительные аргументы, которые можно указать для любого из открытых свойств объекта `System.Runtime.InteropServices.DllImportAttribute` класса, например, соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="b2ba0-110">Предположим, что у вас есть собственный библиотеки DLL C++, содержащий следующую экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="b2ba0-111">Эту функцию можно вызвать из F #, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="b2ba0-112">Взаимодействие с машинным кодом называется *неуправляемого* и является компонентом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="b2ba0-113">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2ba0-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="b2ba0-114">Сведения в этом разделе применима в F #.</span><span class="sxs-lookup"><span data-stu-id="b2ba0-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="b2ba0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b2ba0-115">See Also</span></span>

[<span data-ttu-id="b2ba0-116">Функции</span><span class="sxs-lookup"><span data-stu-id="b2ba0-116">Functions</span></span>](index.md)
