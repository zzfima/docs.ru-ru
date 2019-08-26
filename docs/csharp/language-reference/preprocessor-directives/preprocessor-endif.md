---
title: '#endif. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 74205c836b4eeb2d8b17b907bb13708f3225df08
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608579"
---
# <a name="endif-c-reference"></a><span data-ttu-id="27ac2-102">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="27ac2-102">#endif (C# Reference)</span></span>
<span data-ttu-id="27ac2-103">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="27ac2-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="27ac2-104">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="27ac2-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="27ac2-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="27ac2-105">Remarks</span></span>  
 <span data-ttu-id="27ac2-106">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="27ac2-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="27ac2-107">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="27ac2-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ac2-108">См. также</span><span class="sxs-lookup"><span data-stu-id="27ac2-108">See also</span></span>

- [<span data-ttu-id="27ac2-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="27ac2-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="27ac2-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="27ac2-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="27ac2-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="27ac2-111">C# Preprocessor Directives</span></span>](./index.md)
