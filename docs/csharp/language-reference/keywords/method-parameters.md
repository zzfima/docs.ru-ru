---
title: "Параметры методов (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 924e261cc876d2428e28ed0f490beb46b95f96e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="9f374-102">Параметры методов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9f374-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="9f374-103">С параметром, который объявлен для метода без ключевого слова [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md), может быть связано значение.</span><span class="sxs-lookup"><span data-stu-id="9f374-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="9f374-104">Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="9f374-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="9f374-105">С помощью ключевого слова параметра метода это поведение можно изменить.</span><span class="sxs-lookup"><span data-stu-id="9f374-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="9f374-106">В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:</span><span class="sxs-lookup"><span data-stu-id="9f374-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="9f374-107">params</span><span class="sxs-lookup"><span data-stu-id="9f374-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="9f374-108">ref</span><span class="sxs-lookup"><span data-stu-id="9f374-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="9f374-109">out</span><span class="sxs-lookup"><span data-stu-id="9f374-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f374-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9f374-110">See Also</span></span>  
 [<span data-ttu-id="9f374-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9f374-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9f374-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9f374-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9f374-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9f374-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
