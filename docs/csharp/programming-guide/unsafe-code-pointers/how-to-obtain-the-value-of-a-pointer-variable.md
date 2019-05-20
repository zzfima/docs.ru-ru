---
title: Практическое руководство по программированию на C#. Получение значения переменной указателя
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 9a10bcc809f3ecbc9a0fa9b917940b8e030fab8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635102"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="82a25-102">Практическое руководство по программированию на C#. Получение значения переменной указателя</span><span class="sxs-lookup"><span data-stu-id="82a25-102">How to: obtain the value of a pointer variable (C# Programming Guide)</span></span>

<span data-ttu-id="82a25-103">Оператор косвенного обращения к указателю позволяет получить переменную в расположении, на которое указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="82a25-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="82a25-104">Выражение имеет следующую форму, где `p` — это тип указателя:</span><span class="sxs-lookup"><span data-stu-id="82a25-104">The expression takes the following form, where `p` is a pointer type:</span></span>  

```csharp
*p;  
```

<span data-ttu-id="82a25-105">Унарный оператор косвенного обращения можно использовать только по отношению к выражениям с типом указателя.</span><span class="sxs-lookup"><span data-stu-id="82a25-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="82a25-106">Кроме того, его нельзя применять к указателю [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="82a25-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  

<span data-ttu-id="82a25-107">Если оператор косвенного обращения применяется к указателю [NULL](../../../csharp/language-reference/keywords/null.md), результат будет зависеть от особенностей реализации.</span><span class="sxs-lookup"><span data-stu-id="82a25-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  

## <a name="example"></a><span data-ttu-id="82a25-108">Пример</span><span class="sxs-lookup"><span data-stu-id="82a25-108">Example</span></span>

<span data-ttu-id="82a25-109">В следующем примере доступ к переменной типа `char` осуществляется с использованием указателей разных типов.</span><span class="sxs-lookup"><span data-stu-id="82a25-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="82a25-110">Обратите внимание, что адрес `theChar` может изменяться с каждым запуском из-за изменения физического адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="82a25-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
<span data-ttu-id="82a25-111">**Значение theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="82a25-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="82a25-112">**Адрес theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="82a25-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="82a25-113">**Значение pChar = Z**</span><span class="sxs-lookup"><span data-stu-id="82a25-113">**Value of pChar = Z**</span></span>  
<span data-ttu-id="82a25-114">**Значение pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="82a25-114">**Value of pInt = 90**</span></span>  

## <a name="see-also"></a><span data-ttu-id="82a25-115">См. также</span><span class="sxs-lookup"><span data-stu-id="82a25-115">See also</span></span>

- [<span data-ttu-id="82a25-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="82a25-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="82a25-117">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="82a25-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="82a25-118">Типы</span><span class="sxs-lookup"><span data-stu-id="82a25-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="82a25-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="82a25-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="82a25-120">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="82a25-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="82a25-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="82a25-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
