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
ms.openlocfilehash: 0b456ed3ce9965ef389d8ce40167afa4ac33da18
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422526"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bca6e-102">Справочник по C#. Оператор ::</span><span class="sxs-lookup"><span data-stu-id="bca6e-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="bca6e-103">Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="bca6e-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="bca6e-104">Он всегда размещается между двумя идентификаторами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bca6e-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="bca6e-105">Оператор `::` также может использоваться с *директивой псевдонима using*:</span><span class="sxs-lookup"><span data-stu-id="bca6e-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="bca6e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="bca6e-106">Remarks</span></span>

<span data-ttu-id="bca6e-107">Квалификатор псевдонима пространства имен может быть `global`.</span><span class="sxs-lookup"><span data-stu-id="bca6e-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="bca6e-108">Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="bca6e-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="bca6e-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bca6e-109">For more information</span></span>

<span data-ttu-id="bca6e-110">Пример использования оператора `::` см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="bca6e-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="bca6e-111">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="bca6e-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="bca6e-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bca6e-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bca6e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bca6e-113">See also</span></span>

- [<span data-ttu-id="bca6e-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bca6e-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bca6e-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bca6e-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bca6e-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="bca6e-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="bca6e-117">Оператор .</span><span class="sxs-lookup"><span data-stu-id="bca6e-117">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="bca6e-118">Псевдоним extern</span><span class="sxs-lookup"><span data-stu-id="bca6e-118">extern alias</span></span>](../keywords/extern-alias.md)
