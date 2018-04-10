---
title: '#endif (справочник по C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d7e68dd20d914052c3fe5cabcb83abdae100465c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="endif-c-reference"></a><span data-ttu-id="af805-102">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="af805-102">#endif (C# Reference)</span></span>
<span data-ttu-id="af805-103">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="af805-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="af805-104">Например:</span><span class="sxs-lookup"><span data-stu-id="af805-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="af805-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="af805-105">Remarks</span></span>  
 <span data-ttu-id="af805-106">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="af805-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="af805-107">В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="af805-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af805-108">См. также</span><span class="sxs-lookup"><span data-stu-id="af805-108">See Also</span></span>  
 [<span data-ttu-id="af805-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="af805-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="af805-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="af805-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="af805-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="af805-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
