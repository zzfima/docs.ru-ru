---
title: Справочник по C#. Оператор ^=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333555"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3fc37-102">Справочник по C#. Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="3fc37-102">^= operator (C# Reference)</span></span>

<span data-ttu-id="3fc37-103">Оператор присваивания исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="3fc37-103">The exclusive-OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fc37-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fc37-104">Remarks</span></span>

<span data-ttu-id="3fc37-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="3fc37-105">An expression of the form</span></span>

```csharp
x ^= y
```

<span data-ttu-id="3fc37-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="3fc37-106">is evaluated as</span></span>

```csharp
x = x ^ y
```

<span data-ttu-id="3fc37-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="3fc37-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="3fc37-108">[Оператор ^](xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="3fc37-108">The [^ operator](xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="3fc37-109">Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](xor-operator.md) (см. [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3fc37-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](xor-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="3fc37-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3fc37-110">Example</span></span>

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a><span data-ttu-id="3fc37-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3fc37-111">See also</span></span>

- [<span data-ttu-id="3fc37-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3fc37-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3fc37-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3fc37-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3fc37-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="3fc37-114">C# operators</span></span>](index.md)