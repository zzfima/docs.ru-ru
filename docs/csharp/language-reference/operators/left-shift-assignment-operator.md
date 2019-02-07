---
title: Оператор <<= — справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 0a005efa19be24f9adbf9031f562a30f9c1b0e34
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258738"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8ba20-102">Справочник по C#. Оператор \<\<=</span><span class="sxs-lookup"><span data-stu-id="8ba20-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="8ba20-103">Оператор присваивания сдвига влево.</span><span class="sxs-lookup"><span data-stu-id="8ba20-103">The left-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ba20-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ba20-104">Remarks</span></span>

<span data-ttu-id="8ba20-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="8ba20-105">An expression of the form</span></span>

```csharp
x <<= y
```

<span data-ttu-id="8ba20-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="8ba20-106">is evaluated as</span></span>

```csharp
x = x << y
```

<span data-ttu-id="8ba20-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="8ba20-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8ba20-108">[Оператор <<](left-shift-operator.md) сдвигает `x` влево на число битов, заданное в `y`.</span><span class="sxs-lookup"><span data-stu-id="8ba20-108">The [<< operator](left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>

<span data-ttu-id="8ba20-109">Оператор `<<=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор <<](left-shift-operator.md) (см. [оператор](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8ba20-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](left-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="8ba20-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8ba20-110">Example</span></span>

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a><span data-ttu-id="8ba20-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8ba20-111">See also</span></span>

- [<span data-ttu-id="8ba20-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8ba20-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8ba20-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8ba20-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8ba20-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="8ba20-114">C# Operators</span></span>](index.md)
