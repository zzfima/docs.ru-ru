---
title: '#endif. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 13b43919b666dcc8c5adfc3490eaad73960547ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243911"
---
# <a name="endif-c-reference"></a><span data-ttu-id="1c1c0-102">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1c1c0-102">#endif (C# Reference)</span></span>
<span data-ttu-id="1c1c0-103">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="1c1c0-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="1c1c0-104">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="1c1c0-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c1c0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c1c0-105">Remarks</span></span>  
 <span data-ttu-id="1c1c0-106">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="1c1c0-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="1c1c0-107">В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="1c1c0-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c1c0-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1c1c0-108">See Also</span></span>

- [<span data-ttu-id="1c1c0-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1c1c0-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1c1c0-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1c1c0-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1c1c0-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="1c1c0-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
