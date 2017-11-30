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
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="85db4-104">Внешние функции</span><span class="sxs-lookup"><span data-stu-id="85db4-104">External Functions</span></span>

<span data-ttu-id="85db4-105">В этом разделе описывается поддержка языка F # для вызова функции в машинный код.</span><span class="sxs-lookup"><span data-stu-id="85db4-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="85db4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85db4-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="85db4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="85db4-107">Remarks</span></span>

<span data-ttu-id="85db4-108">В предыдущем синтаксисе *аргументы* представляет аргументы, передаваемые `System.Runtime.InteropServices.DllImportAttribute` атрибута.</span><span class="sxs-lookup"><span data-stu-id="85db4-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="85db4-109">Первым аргументом является строка, представляющая имя библиотеки DLL, содержащей эту функцию без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="85db4-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="85db4-110">Дополнительные аргументы, которые можно указать для любого из открытых свойств объекта `System.Runtime.InteropServices.DllImportAttribute` класса, например, соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="85db4-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="85db4-111">Предположим, что у вас есть собственный библиотеки DLL C++, содержащий следующую экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="85db4-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="85db4-112">Эту функцию можно вызвать из F #, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="85db4-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="85db4-113">Взаимодействие с машинным кодом называется *неуправляемого* и является компонентом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="85db4-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="85db4-114">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k.aspx).</span><span class="sxs-lookup"><span data-stu-id="85db4-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="85db4-115">Сведения в этом разделе применима в F #.</span><span class="sxs-lookup"><span data-stu-id="85db4-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="85db4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="85db4-116">See Also</span></span>

[<span data-ttu-id="85db4-117">Функции</span><span class="sxs-lookup"><span data-stu-id="85db4-117">Functions</span></span>](index.md)
