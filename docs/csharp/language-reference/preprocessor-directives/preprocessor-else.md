---
title: '#else. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 67d3e6b8fc136e16fb0e307a9f8ceca494169bfc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696143"
---
# <a name="else-c-reference"></a><span data-ttu-id="019bc-102">#else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="019bc-102">#else (C# Reference)</span></span>
<span data-ttu-id="019bc-103">С помощью директивы `#else` можно создать составную условную директиву со следующим поведением: если ни одно из выражений в предшествующих директивах [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или (необязательно) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) не принимает значение `true`, компилятор выполняет код между директивой `#else` и последующей директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="019bc-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="019bc-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="019bc-104">Remarks</span></span>  
 <span data-ttu-id="019bc-105">Директива [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) обязательно указывается в качестве следующей директивы препроцессора после `#else`.</span><span class="sxs-lookup"><span data-stu-id="019bc-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="019bc-106">В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#else`.</span><span class="sxs-lookup"><span data-stu-id="019bc-106">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019bc-107">См. также</span><span class="sxs-lookup"><span data-stu-id="019bc-107">See also</span></span>

- [<span data-ttu-id="019bc-108">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="019bc-108">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="019bc-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="019bc-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="019bc-110">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="019bc-110">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
