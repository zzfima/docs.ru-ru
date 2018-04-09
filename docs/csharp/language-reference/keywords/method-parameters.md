---
title: Параметры методов (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 35d96066deb866e02f6bf624121376fe3ae94373
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="3fd3f-102">Параметры методов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3fd3f-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="3fd3f-103">Параметры, объявленные для метода без [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), передаются в вызываемый метод по значению.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="3fd3f-104">Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="3fd3f-105">С помощью ключевого слова параметра метода это поведение можно изменить.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="3fd3f-106">В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:</span><span class="sxs-lookup"><span data-stu-id="3fd3f-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="3fd3f-107">[params](../../../csharp/language-reference/keywords/params.md) указывает, что этот параметр может принимать переменное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="3fd3f-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) указывает, что этот параметр передается по ссылке, но лишь считывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="3fd3f-109">[ref](../../../csharp/language-reference/keywords/ref.md) указывает, что этот параметр передается по ссылке и может быть считан или записан вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="3fd3f-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) указывает, что этот параметр передается по ссылке и записывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3fd3f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3fd3f-111">See Also</span></span>  
 [<span data-ttu-id="3fd3f-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3fd3f-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3fd3f-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3fd3f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3fd3f-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="3fd3f-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
