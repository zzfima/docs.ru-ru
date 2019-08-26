---
title: Руководство по программированию на C#. Передача параметров
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 1c42ce7b258ca35d4e91e1ef28c71b60fe1f01de
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596257"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="347ac-102">Передача параметров (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="347ac-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="347ac-103">В C# аргументы могут передаваться параметрам либо по значению, либо по ссылке.</span><span class="sxs-lookup"><span data-stu-id="347ac-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="347ac-104">Передача по ссылке позволяет изменять и сохранять измененные значения параметров членов функций, методов, свойств, индексаторов, операторов и конструкторов в вызывающей среде.</span><span class="sxs-lookup"><span data-stu-id="347ac-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="347ac-105">Чтобы передать параметр по ссылке, намереваясь изменить значение, используйте ключевое слово `ref` или `out`.</span><span class="sxs-lookup"><span data-stu-id="347ac-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="347ac-106">Чтобы передать по ссылке, намереваясь предотвратить копирование, но не изменение значения, используйте модификатор `in`.</span><span class="sxs-lookup"><span data-stu-id="347ac-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="347ac-107">Для простоты в этих примерах используется только ключевое слово `ref`.</span><span class="sxs-lookup"><span data-stu-id="347ac-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="347ac-108">Дополнительные сведения о различиях между ключевыми словами `in`, `ref` и `out` см. в разделах [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="347ac-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="347ac-109">В приведенном ниже примере показано различие между параметрами-значениями и ссылочными параметрами.</span><span class="sxs-lookup"><span data-stu-id="347ac-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="347ac-110">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="347ac-110">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="347ac-111">Передача параметров типа значения</span><span class="sxs-lookup"><span data-stu-id="347ac-111">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="347ac-112">Передача параметров ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="347ac-112">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="347ac-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="347ac-113">C# Language Specification</span></span>  

<span data-ttu-id="347ac-114">Дополнительные сведения см. в разделе [Список аргументов](~/_csharplang/spec/expressions.md#argument-lists) в [Спецификации языка C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="347ac-114">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="347ac-115">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="347ac-115">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="347ac-116">См. также</span><span class="sxs-lookup"><span data-stu-id="347ac-116">See also</span></span>

- [<span data-ttu-id="347ac-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="347ac-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="347ac-118">Методы</span><span class="sxs-lookup"><span data-stu-id="347ac-118">Methods</span></span>](./methods.md)
