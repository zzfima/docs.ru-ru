---
title: Оператор -&gt; (справочник по C#)
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 178724ede105d809bd812461121a38d5a0e90517
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144134"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="fe383-102">Оператор -&gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fe383-102">-&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="fe383-103">Оператор доступа `->` к элементу с использованием указателя объединяет косвенное обращение к указателю и доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="fe383-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="fe383-104">Если `x` — это указатель типа `T*`, `y` — доступный элемент `T`, выражение формы будет</span><span class="sxs-lookup"><span data-stu-id="fe383-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="fe383-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="fe383-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="fe383-106">Для оператора `->` требуется [небезопасный](../keywords/unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="fe383-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="fe383-107">Дополнительные сведения см. в [практическом руководстве по получению доступа к элементу с использованием указателя](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="fe383-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="fe383-108">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="fe383-108">Operator overloadability</span></span>

<span data-ttu-id="fe383-109">Оператор `->` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="fe383-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fe383-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fe383-110">C# language specification</span></span>

<span data-ttu-id="fe383-111">Дополнительные сведения см. в разделе о [получении доступа к элементу](~/_csharplang/spec/unsafe-code.md#pointer-member-access) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="fe383-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe383-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fe383-112">See also</span></span>

- [<span data-ttu-id="fe383-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fe383-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fe383-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fe383-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fe383-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="fe383-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="fe383-116">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="fe383-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
