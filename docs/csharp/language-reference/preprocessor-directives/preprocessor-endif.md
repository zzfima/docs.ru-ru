---
title: '#endif (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: a652c1226f8f0c624ec8ebf0e665a4aa77ddf6f0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43420818"
---
# <a name="endif-c-reference"></a><span data-ttu-id="0c229-102">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0c229-102">#endif (C# Reference)</span></span>
<span data-ttu-id="0c229-103">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="0c229-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="0c229-104">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="0c229-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c229-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c229-105">Remarks</span></span>  
 <span data-ttu-id="0c229-106">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="0c229-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="0c229-107">В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="0c229-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c229-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0c229-108">See Also</span></span>

- [<span data-ttu-id="0c229-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0c229-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0c229-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0c229-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0c229-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="0c229-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
