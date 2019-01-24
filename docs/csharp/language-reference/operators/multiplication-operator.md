---
title: '* Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333737"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d9a82-102">Справочник по C#. Оператор \*</span><span class="sxs-lookup"><span data-stu-id="d9a82-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="d9a82-103">Оператор умножения (`*`) вычисляет произведение операндов.</span><span class="sxs-lookup"><span data-stu-id="d9a82-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="d9a82-104">Все числовые типы имеют предопределенные операторы умножения.</span><span class="sxs-lookup"><span data-stu-id="d9a82-104">All numeric types have predefined multiplication operators.</span></span>

<span data-ttu-id="d9a82-105">Кроме того, `*` служит оператором разыменования, позволяющим выполнять чтение указателя и запись в него.</span><span class="sxs-lookup"><span data-stu-id="d9a82-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9a82-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9a82-106">Remarks</span></span>

<span data-ttu-id="d9a82-107">Оператор `*` также используется для объявления типов указателей и для разыменования указателей.</span><span class="sxs-lookup"><span data-stu-id="d9a82-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="d9a82-108">Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d9a82-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../keywords/unsafe.md) keyword, and requiring the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="d9a82-109">Оператор разыменования также известен как оператор косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="d9a82-109">The dereference operator is also known as the indirection operator.</span></span>

<span data-ttu-id="d9a82-110">Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="d9a82-110">User-defined types can overload the binary `*` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="d9a82-111">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="d9a82-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="d9a82-112">Пример</span><span class="sxs-lookup"><span data-stu-id="d9a82-112">Example</span></span>

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a><span data-ttu-id="d9a82-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d9a82-113">Example</span></span>

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a><span data-ttu-id="d9a82-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d9a82-114">See also</span></span>

- [<span data-ttu-id="d9a82-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d9a82-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d9a82-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d9a82-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d9a82-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="d9a82-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="d9a82-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="d9a82-118">C# Operators</span></span>](index.md)