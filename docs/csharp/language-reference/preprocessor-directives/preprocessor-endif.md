---
title: '#endif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712550"
---
# <a name="endif-c-reference"></a><span data-ttu-id="90969-102">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="90969-102">#endif (C# Reference)</span></span>
<span data-ttu-id="90969-103">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="90969-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="90969-104">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="90969-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="90969-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="90969-105">Remarks</span></span>  
 <span data-ttu-id="90969-106">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="90969-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="90969-107">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="90969-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90969-108">См. также</span><span class="sxs-lookup"><span data-stu-id="90969-108">See also</span></span>

- [<span data-ttu-id="90969-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="90969-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="90969-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="90969-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="90969-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="90969-111">C# Preprocessor Directives</span></span>](./index.md)
