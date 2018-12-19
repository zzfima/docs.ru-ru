---
title: '* Оператор. Справочник по C#'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 24ac4a99c48f1e8204b821bfbf5f7fbc0a2b2f1d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237354"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d6a7b-102">Оператор \* (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d6a7b-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="d6a7b-103">Оператор умножения (`*`) вычисляет произведение операндов.</span><span class="sxs-lookup"><span data-stu-id="d6a7b-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="d6a7b-104">Все числовые типы имеют предопределенные операторы умножения.</span><span class="sxs-lookup"><span data-stu-id="d6a7b-104">All numeric types have predefined multiplication operators.</span></span>  

<span data-ttu-id="d6a7b-105">Кроме того, `*` служит оператором разыменования, позволяющим выполнять чтение указателя и запись в него.</span><span class="sxs-lookup"><span data-stu-id="d6a7b-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d6a7b-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6a7b-106">Remarks</span></span>  
 <span data-ttu-id="d6a7b-107">Оператор `*` также используется для объявления типов указателей и для разыменования указателей.</span><span class="sxs-lookup"><span data-stu-id="d6a7b-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="d6a7b-108">Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../../../csharp/language-reference/keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d6a7b-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="d6a7b-109">Оператор разыменования также известен как оператор косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="d6a7b-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="d6a7b-110">Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="d6a7b-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="d6a7b-111">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="d6a7b-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6a7b-112">Пример</span><span class="sxs-lookup"><span data-stu-id="d6a7b-112">Example</span></span>  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d6a7b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d6a7b-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d6a7b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d6a7b-114">See Also</span></span>

- [<span data-ttu-id="d6a7b-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d6a7b-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d6a7b-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d6a7b-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d6a7b-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="d6a7b-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="d6a7b-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="d6a7b-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
