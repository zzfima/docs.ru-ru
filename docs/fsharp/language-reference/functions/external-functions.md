---
title: "Внешние функции (F#)"
description: "Дополнительные сведения о поддержке языка F # для вызова функции в машинный код."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 69b73983a91bc6c7cc38fa34484a3c89fc01858f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="external-functions"></a><span data-ttu-id="1a593-104">Внешние функции</span><span class="sxs-lookup"><span data-stu-id="1a593-104">External Functions</span></span>

<span data-ttu-id="1a593-105">В этом разделе описывается поддержка языка F # для вызова функции в машинный код.</span><span class="sxs-lookup"><span data-stu-id="1a593-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a593-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a593-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="1a593-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a593-107">Remarks</span></span>

<span data-ttu-id="1a593-108">В предыдущем синтаксисе *аргументы* представляет аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибута.</span><span class="sxs-lookup"><span data-stu-id="1a593-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="1a593-109">Первым аргументом является строка, представляющая имя библиотеки DLL, содержащей эту функцию без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="1a593-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="1a593-110">Дополнительные аргументы, которые можно указать для любого из открытых свойств объекта `System.Runtime.InteropServices.DllImportAttribute` класса, например, соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="1a593-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="1a593-111">Предположим, что у вас есть собственный библиотеки DLL C++, содержащий следующую экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="1a593-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="1a593-112">Эту функцию можно вызвать из F #, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="1a593-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="1a593-113">Взаимодействие с машинным кодом называется *неуправляемого* и является компонентом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1a593-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="1a593-114">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a593-114">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="1a593-115">Сведения в этом разделе применима в F #.</span><span class="sxs-lookup"><span data-stu-id="1a593-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="1a593-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1a593-116">See Also</span></span>

[<span data-ttu-id="1a593-117">Функции</span><span class="sxs-lookup"><span data-stu-id="1a593-117">Functions</span></span>](index.md)
