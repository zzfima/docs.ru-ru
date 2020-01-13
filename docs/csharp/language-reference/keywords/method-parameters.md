---
title: Справочник по C#. Параметры методов
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713375"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="6bd98-102">Параметры методов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6bd98-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="6bd98-103">Параметры, объявленные для метода без [in](./in-parameter-modifier.md), [ref](./ref.md) или [out](./out-parameter-modifier.md), передаются в вызываемый метод по значению.</span><span class="sxs-lookup"><span data-stu-id="6bd98-103">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="6bd98-104">Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="6bd98-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="6bd98-105">С помощью ключевого слова параметра метода это поведение можно изменить.</span><span class="sxs-lookup"><span data-stu-id="6bd98-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="6bd98-106">В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:</span><span class="sxs-lookup"><span data-stu-id="6bd98-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="6bd98-107">[params](./params.md) указывает, что этот параметр может принимать переменное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="6bd98-107">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="6bd98-108">[in](./in-parameter-modifier.md) указывает, что этот параметр передается по ссылке, но лишь считывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="6bd98-108">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="6bd98-109">[ref](./ref.md) указывает, что этот параметр передается по ссылке и может быть считан или записан вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="6bd98-109">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="6bd98-110">[out](./out-parameter-modifier.md) указывает, что этот параметр передается по ссылке и записывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="6bd98-110">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6bd98-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6bd98-111">See also</span></span>

- [<span data-ttu-id="6bd98-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6bd98-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6bd98-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6bd98-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6bd98-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6bd98-114">C# Keywords</span></span>](./index.md)
