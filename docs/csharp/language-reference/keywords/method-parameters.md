---
title: Справочник по C#. Параметры методов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 6746b572719b3233f3b99afde3dd8b5c0b7abcf1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592958"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="e18b3-102">Параметры методов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e18b3-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="e18b3-103">Параметры, объявленные для метода без [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), передаются в вызываемый метод по значению.</span><span class="sxs-lookup"><span data-stu-id="e18b3-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="e18b3-104">Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e18b3-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="e18b3-105">С помощью ключевого слова параметра метода это поведение можно изменить.</span><span class="sxs-lookup"><span data-stu-id="e18b3-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="e18b3-106">В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:</span><span class="sxs-lookup"><span data-stu-id="e18b3-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="e18b3-107">[params](../../../csharp/language-reference/keywords/params.md) указывает, что этот параметр может принимать переменное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="e18b3-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="e18b3-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) указывает, что этот параметр передается по ссылке, но лишь считывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="e18b3-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="e18b3-109">[ref](../../../csharp/language-reference/keywords/ref.md) указывает, что этот параметр передается по ссылке и может быть считан или записан вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="e18b3-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="e18b3-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) указывает, что этот параметр передается по ссылке и записывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="e18b3-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e18b3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e18b3-111">See also</span></span>

- [<span data-ttu-id="e18b3-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e18b3-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e18b3-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e18b3-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e18b3-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e18b3-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
