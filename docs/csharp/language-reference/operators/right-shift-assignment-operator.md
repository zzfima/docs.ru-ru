---
title: '>>Оператор = — справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278984"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1d262-102">Оператор >>= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1d262-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="1d262-103">Оператор присваивания сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="1d262-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d262-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d262-104">Remarks</span></span>

<span data-ttu-id="1d262-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="1d262-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="1d262-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="1d262-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="1d262-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="1d262-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="1d262-108">[Оператор >>](right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.</span><span class="sxs-lookup"><span data-stu-id="1d262-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="1d262-109">Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](right-shift-operator.md) (см. [оператор](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="1d262-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="1d262-110">Пример</span><span class="sxs-lookup"><span data-stu-id="1d262-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="1d262-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1d262-111">See also</span></span>

- [<span data-ttu-id="1d262-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1d262-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1d262-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1d262-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1d262-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1d262-114">C# operators</span></span>](index.md)