---
title: Справочник по C#. Оператор ^
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 16419342fec9d6c9845e19e434787c5e4f5a5b12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632258"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5e576-102">Справочник по C#. Оператор ^</span><span class="sxs-lookup"><span data-stu-id="5e576-102">^ operator (C# Reference)</span></span>

<span data-ttu-id="5e576-103">Бинарные операторы `^` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="5e576-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="5e576-104">Для целочисленных типов оператор `^` выполняет побитовую операцию исключающего ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="5e576-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="5e576-105">Для операндов типа `bool` оператор `^` выполняет логическую операцию исключающего ИЛИ для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда только один из операндов имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5e576-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e576-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e576-106">Remarks</span></span>

<span data-ttu-id="5e576-107">Определяемые пользователем типы могут вызвать перегрузку оператора `^` (см. раздел [operator](../keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="5e576-107">User-defined types can overload the `^` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="5e576-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="5e576-108">Operations on integral types are generally allowed on enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="5e576-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5e576-109">Example</span></span>

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

<span data-ttu-id="5e576-110">При вычислении выражения `0xf8 ^ 0x3f` в предыдущем примере выполняется побитовая операция исключающего ИЛИ со следующими двумя двоичными значениями, которые соответствуют шестнадцатеричным значениям F8 и 3F:</span><span class="sxs-lookup"><span data-stu-id="5e576-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>

`1111 1000`

`0011 1111`

<span data-ttu-id="5e576-111">В результате выполнения операции исключающего ИЛИ получается значение `1100 0111` или C7 в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="5e576-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e576-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5e576-112">See also</span></span>

- [<span data-ttu-id="5e576-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5e576-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5e576-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5e576-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5e576-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="5e576-115">C# operators</span></span>](index.md)
