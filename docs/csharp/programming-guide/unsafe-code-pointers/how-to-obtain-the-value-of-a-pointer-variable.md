---
title: Как выполнить Руководство по программированию на C#. Получение значения переменной указателя
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 5fbc925b6770bc951a0d7ec856898f62c265462e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577158"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="c58a6-102">Как выполнить Руководство по программированию на C#. Получение значения переменной указателя</span><span class="sxs-lookup"><span data-stu-id="c58a6-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="c58a6-103">Оператор косвенного обращения к указателю позволяет получить переменную в расположении, на которое указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="c58a6-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="c58a6-104">Выражение имеет следующую форму, где `p` — это тип указателя:</span><span class="sxs-lookup"><span data-stu-id="c58a6-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="c58a6-105">Унарный оператор косвенного обращения можно использовать только по отношению к выражениям с типом указателя.</span><span class="sxs-lookup"><span data-stu-id="c58a6-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="c58a6-106">Кроме того, его нельзя применять к указателю [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="c58a6-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="c58a6-107">Если оператор косвенного обращения применяется к указателю [NULL](../../../csharp/language-reference/keywords/null.md), результат будет зависеть от особенностей реализации.</span><span class="sxs-lookup"><span data-stu-id="c58a6-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c58a6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c58a6-108">Example</span></span>  
 <span data-ttu-id="c58a6-109">В следующем примере доступ к переменной типа `char` осуществляется с использованием указателей разных типов.</span><span class="sxs-lookup"><span data-stu-id="c58a6-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="c58a6-110">Обратите внимание, что адрес `theChar` может изменяться с каждым запуском из-за изменения физического адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="c58a6-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
<span data-ttu-id="c58a6-111">**Значение theChar = Z**
**Адрес theChar = 12F718**
**Значение pChar = Z**
**Значение pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="c58a6-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span></span>

## <a name="see-also"></a><span data-ttu-id="c58a6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c58a6-112">See also</span></span>

- [<span data-ttu-id="c58a6-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c58a6-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c58a6-114">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="c58a6-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="c58a6-115">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="c58a6-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="c58a6-116">Типы</span><span class="sxs-lookup"><span data-stu-id="c58a6-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="c58a6-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="c58a6-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="c58a6-118">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="c58a6-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="c58a6-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="c58a6-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
