---
title: "Параметры методов (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4ba57e1a9e904befe11ff41796c987bd8f93b081
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="ba309-102">Параметры методов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ba309-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="ba309-103">С параметром, который объявлен для метода без ключевого слова [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md), может быть связано значение.</span><span class="sxs-lookup"><span data-stu-id="ba309-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="ba309-104">Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="ba309-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="ba309-105">С помощью ключевого слова параметра метода это поведение можно изменить.</span><span class="sxs-lookup"><span data-stu-id="ba309-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="ba309-106">В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:</span><span class="sxs-lookup"><span data-stu-id="ba309-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="ba309-107">params</span><span class="sxs-lookup"><span data-stu-id="ba309-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="ba309-108">ref</span><span class="sxs-lookup"><span data-stu-id="ba309-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="ba309-109">out</span><span class="sxs-lookup"><span data-stu-id="ba309-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba309-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ba309-110">See Also</span></span>  
 <span data-ttu-id="ba309-111">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba309-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ba309-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba309-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ba309-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ba309-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

