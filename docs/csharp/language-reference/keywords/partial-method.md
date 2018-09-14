---
title: Метод partial (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: f859506ef59f4fc709e9942d86130fc222c14faf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516373"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="5db6e-102">Метод partial (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5db6e-102">partial method (C# Reference)</span></span>

<span data-ttu-id="5db6e-103">Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа.</span><span class="sxs-lookup"><span data-stu-id="5db6e-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="5db6e-104">С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="5db6e-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="5db6e-105">Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="5db6e-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="5db6e-106">В отношении разделяемых методов применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="5db6e-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="5db6e-107">Сигнатуры в обеих частях разделяемого типа должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="5db6e-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="5db6e-108">Метод должен возвращать значение void.</span><span class="sxs-lookup"><span data-stu-id="5db6e-108">The method must return void.</span></span>

- <span data-ttu-id="5db6e-109">Модификаторы доступа не допускаются.</span><span class="sxs-lookup"><span data-stu-id="5db6e-109">No access modifiers are allowed.</span></span> <span data-ttu-id="5db6e-110">Разделяемые методы являются неявно частными.</span><span class="sxs-lookup"><span data-stu-id="5db6e-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="5db6e-111">В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:</span><span class="sxs-lookup"><span data-stu-id="5db6e-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="5db6e-112">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5db6e-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5db6e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5db6e-113">See also</span></span>

- [<span data-ttu-id="5db6e-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5db6e-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5db6e-115">Тип partial</span><span class="sxs-lookup"><span data-stu-id="5db6e-115">partial type</span></span>](partial-type.md)