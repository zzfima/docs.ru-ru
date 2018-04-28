---
title: Внешние функции (F#)
description: 'Дополнительные сведения о поддержке языка F # для вызова функции в машинный код.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 28e74258d91ff2d9742caa7a6c06f515cd987c0a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="external-functions"></a><span data-ttu-id="77eb1-103">Внешние функции</span><span class="sxs-lookup"><span data-stu-id="77eb1-103">External Functions</span></span>

<span data-ttu-id="77eb1-104">В этом разделе описывается поддержка языка F # для вызова функции в машинный код.</span><span class="sxs-lookup"><span data-stu-id="77eb1-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="77eb1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77eb1-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="77eb1-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="77eb1-106">Remarks</span></span>

<span data-ttu-id="77eb1-107">В предыдущем синтаксисе *аргументы* представляет аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибута.</span><span class="sxs-lookup"><span data-stu-id="77eb1-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="77eb1-108">Первым аргументом является строка, представляющая имя библиотеки DLL, содержащей эту функцию без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="77eb1-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="77eb1-109">Дополнительные аргументы, которые можно указать для любого из открытых свойств объекта `System.Runtime.InteropServices.DllImportAttribute` класса, например, соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="77eb1-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="77eb1-110">Предположим, что у вас есть собственный библиотеки DLL C++, содержащий следующую экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="77eb1-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="77eb1-111">Эту функцию можно вызвать из F #, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="77eb1-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="77eb1-112">Взаимодействие с машинным кодом называется *неуправляемого* и является компонентом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="77eb1-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="77eb1-113">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="77eb1-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="77eb1-114">Сведения в этом разделе применима в F #.</span><span class="sxs-lookup"><span data-stu-id="77eb1-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="77eb1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="77eb1-115">See Also</span></span>

[<span data-ttu-id="77eb1-116">Функции</span><span class="sxs-lookup"><span data-stu-id="77eb1-116">Functions</span></span>](index.md)
