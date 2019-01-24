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
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333711"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fb7ae-102">Справочник по C#. Оператор ^</span><span class="sxs-lookup"><span data-stu-id="fb7ae-102">^ operator (C# Reference)</span></span>

<span data-ttu-id="fb7ae-103">Бинарные операторы `^` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="fb7ae-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="fb7ae-104">Для целочисленных типов оператор `^` выполняет побитовую операцию исключающего ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="fb7ae-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="fb7ae-105">Для операндов типа `bool` оператор `^` выполняет логическую операцию исключающего ИЛИ для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда только один из операндов имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="fb7ae-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb7ae-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb7ae-106">Remarks</span></span>

<span data-ttu-id="fb7ae-107">Определяемые пользователем типы могут вызвать перегрузку оператора `^` (см. раздел [operator](../keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="fb7ae-107">User-defined types can overload the `^` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="fb7ae-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="fb7ae-108">Operations on integral types are generally allowed on enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="fb7ae-109">Пример</span><span class="sxs-lookup"><span data-stu-id="fb7ae-109">Example</span></span>

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

<span data-ttu-id="fb7ae-110">При вычислении выражения `0xf8 ^ 0x3f` в предыдущем примере выполняется побитовая операция исключающего ИЛИ со следующими двумя двоичными значениями, которые соответствуют шестнадцатеричным значениям F8 и 3F:</span><span class="sxs-lookup"><span data-stu-id="fb7ae-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>

`1111 1000`

`0011 1111`

<span data-ttu-id="fb7ae-111">В результате выполнения операции исключающего ИЛИ получается значение `1100 0111` или C7 в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="fb7ae-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb7ae-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fb7ae-112">See Also</span></span>

- [<span data-ttu-id="fb7ae-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fb7ae-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fb7ae-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fb7ae-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fb7ae-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="fb7ae-115">C# operators</span></span>](index.md)
