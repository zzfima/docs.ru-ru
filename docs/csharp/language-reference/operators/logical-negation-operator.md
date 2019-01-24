---
title: '! Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 6b6d1796032f536aac0be49d4f101c1380b4e98f
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333230"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="99e97-103">!</span><span class="sxs-lookup"><span data-stu-id="99e97-103">!</span></span> <span data-ttu-id="99e97-104">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="99e97-104">operator (C# Reference)</span></span>

<span data-ttu-id="99e97-105">Оператор логического отрицания (`!`) представляет собой унарный оператор, который инвертирует свой операнд.</span><span class="sxs-lookup"><span data-stu-id="99e97-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="99e97-106">Он определяется для значения типа `bool` и возвращает `true` только в том случае, если операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="99e97-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="99e97-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="99e97-107">Remarks</span></span>

<span data-ttu-id="99e97-108">Определяемые пользователем типы могут вызвать перегрузку оператора `!` (см. раздел [operator](../keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="99e97-108">User-defined types can overload the `!` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="99e97-109">Пример</span><span class="sxs-lookup"><span data-stu-id="99e97-109">Example</span></span>

[!code-csharp[csRefOperators#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#7)]

## <a name="see-also"></a><span data-ttu-id="99e97-110">См. также</span><span class="sxs-lookup"><span data-stu-id="99e97-110">See also</span></span>

- [<span data-ttu-id="99e97-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="99e97-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="99e97-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="99e97-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="99e97-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="99e97-113">C# Operators</span></span>](index.md)