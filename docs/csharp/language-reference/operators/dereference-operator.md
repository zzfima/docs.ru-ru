---
title: Оператор -> — справочник по C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: be74f02a85aa05cdab32768ed38222fc4d9289b1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255371"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="d32d3-102">Оператор -> (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d32d3-102">-> Operator (C# Reference)</span></span>

<span data-ttu-id="d32d3-103">Оператор доступа `->` к элементу с использованием указателя объединяет косвенное обращение к указателю и доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="d32d3-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="d32d3-104">Если `x` — это указатель типа `T*`, `y` — доступный элемент `T`, выражение формы будет</span><span class="sxs-lookup"><span data-stu-id="d32d3-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="d32d3-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="d32d3-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="d32d3-106">Для оператора `->` требуется [небезопасный](../keywords/unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="d32d3-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="d32d3-107">Дополнительные сведения см. в [практическом руководстве по получению доступа к элементу с использованием указателя](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="d32d3-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d32d3-108">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="d32d3-108">Operator overloadability</span></span>

<span data-ttu-id="d32d3-109">Оператор `->` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="d32d3-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d32d3-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d32d3-110">C# language specification</span></span>

<span data-ttu-id="d32d3-111">Дополнительные сведения см. в разделе о [получении доступа к элементу](~/_csharplang/spec/unsafe-code.md#pointer-member-access) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d32d3-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d32d3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d32d3-112">See also</span></span>

- [<span data-ttu-id="d32d3-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d32d3-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d32d3-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d32d3-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d32d3-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="d32d3-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d32d3-116">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="d32d3-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
