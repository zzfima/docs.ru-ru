---
title: 'Справочник по C#. Оператор ::'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 5bd43bb60736bbcaf8034cc2b369c34f977319ac
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633912"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c9313-102">Справочник по C#. Оператор ::</span><span class="sxs-lookup"><span data-stu-id="c9313-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="c9313-103">Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="c9313-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="c9313-104">Он всегда размещается между двумя идентификаторами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c9313-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="c9313-105">Оператор `::` также может использоваться с *директивой псевдонима using*:</span><span class="sxs-lookup"><span data-stu-id="c9313-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="c9313-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9313-106">Remarks</span></span>

<span data-ttu-id="c9313-107">Квалификатор псевдонима пространства имен может быть `global`.</span><span class="sxs-lookup"><span data-stu-id="c9313-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="c9313-108">Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="c9313-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c9313-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9313-109">For more information</span></span>

<span data-ttu-id="c9313-110">Пример использования оператора `::` см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="c9313-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="c9313-111">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="c9313-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="c9313-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c9313-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c9313-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c9313-113">See also</span></span>

- [<span data-ttu-id="c9313-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c9313-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c9313-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c9313-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c9313-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="c9313-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="c9313-117">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="c9313-117">Namespace Keywords</span></span>](../keywords/namespace-keywords.md)
- [<span data-ttu-id="c9313-118">Оператор .</span><span class="sxs-lookup"><span data-stu-id="c9313-118">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="c9313-119">Псевдоним extern</span><span class="sxs-lookup"><span data-stu-id="c9313-119">extern alias</span></span>](../keywords/extern-alias.md)
