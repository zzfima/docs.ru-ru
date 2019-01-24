---
title: Справочник по C#. Оператор *=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333438"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ce7c5-102">Оператор \*= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ce7c5-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="ce7c5-103">Бинарный оператор присваивания умножения.</span><span class="sxs-lookup"><span data-stu-id="ce7c5-103">The binary multiplication assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce7c5-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce7c5-104">Remarks</span></span>

<span data-ttu-id="ce7c5-105">Выражение, использующее оператор присваивания `*=`, такое как</span><span class="sxs-lookup"><span data-stu-id="ce7c5-105">An expression using the `*=` assignment operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="ce7c5-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="ce7c5-106">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="ce7c5-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="ce7c5-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ce7c5-108">В числовых типах [оператор \*](multiplication-operator.md) используется для выполнения операций умножения.</span><span class="sxs-lookup"><span data-stu-id="ce7c5-108">The [\* operator](multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>

<span data-ttu-id="ce7c5-109">Оператор `*=` нельзя перегружать напрямую, но пользовательские типы могут перегружать [оператор \*](multiplication-operator.md) (см. [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ce7c5-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](multiplication-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="ce7c5-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ce7c5-110">Example</span></span>

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a><span data-ttu-id="ce7c5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ce7c5-111">See also</span></span>

- [<span data-ttu-id="ce7c5-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ce7c5-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ce7c5-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ce7c5-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ce7c5-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ce7c5-114">C# Operators</span></span>](index.md)
