---
title: '#else. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 967ef38687b739ef3bea3f8923ab26bba0b6cea9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712563"
---
# <a name="else-c-reference"></a><span data-ttu-id="275a4-102">#else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="275a4-102">#else (C# Reference)</span></span>
<span data-ttu-id="275a4-103">С помощью директивы `#else` можно создать составную условную директиву со следующим поведением: если ни одно из выражений в предшествующих директивах [#if](./preprocessor-if.md) или (необязательно) [#elif](./preprocessor-elif.md) не принимает значение `true`, компилятор выполняет код между директивой `#else` и последующей директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="275a4-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="275a4-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="275a4-104">Remarks</span></span>  
 <span data-ttu-id="275a4-105">Директива [#endif](./preprocessor-endif.md) обязательно указывается в качестве следующей директивы препроцессора после `#else`.</span><span class="sxs-lookup"><span data-stu-id="275a4-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="275a4-106">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#else`.</span><span class="sxs-lookup"><span data-stu-id="275a4-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275a4-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="275a4-107">See also</span></span>

- [<span data-ttu-id="275a4-108">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="275a4-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="275a4-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="275a4-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="275a4-110">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="275a4-110">C# Preprocessor Directives</span></span>](./index.md)
