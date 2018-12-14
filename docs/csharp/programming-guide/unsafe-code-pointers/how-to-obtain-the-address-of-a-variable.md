---
title: Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: bb752306bcdb630d652d331e95a765aee6afac3d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150944"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="29fcf-102">Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="29fcf-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="29fcf-103">Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of `&`:</span><span class="sxs-lookup"><span data-stu-id="29fcf-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="29fcf-104">Оператор address-of применяется только к переменным.</span><span class="sxs-lookup"><span data-stu-id="29fcf-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="29fcf-105">Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.</span><span class="sxs-lookup"><span data-stu-id="29fcf-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="29fcf-106">Вам необходимо самостоятельно обеспечить проверку инициализации переменной.</span><span class="sxs-lookup"><span data-stu-id="29fcf-106">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="29fcf-107">Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="29fcf-107">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="29fcf-108">Получить адрес константы или значения нельзя.</span><span class="sxs-lookup"><span data-stu-id="29fcf-108">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29fcf-109">Пример</span><span class="sxs-lookup"><span data-stu-id="29fcf-109">Example</span></span>  
 <span data-ttu-id="29fcf-110">В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`.</span><span class="sxs-lookup"><span data-stu-id="29fcf-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="29fcf-111">Переменная `number` инициализируется в результате назначения `*p`.</span><span class="sxs-lookup"><span data-stu-id="29fcf-111">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="29fcf-112">Если закомментировать этот оператор назначения, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет.</span><span class="sxs-lookup"><span data-stu-id="29fcf-112">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="29fcf-113">Скомпилируйте этот пример с использованием параметра компилятора [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="29fcf-113">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="29fcf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="29fcf-114">See Also</span></span>

- [<span data-ttu-id="29fcf-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="29fcf-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="29fcf-116">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="29fcf-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="29fcf-117">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="29fcf-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="29fcf-118">Типы</span><span class="sxs-lookup"><span data-stu-id="29fcf-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="29fcf-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="29fcf-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="29fcf-120">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="29fcf-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="29fcf-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="29fcf-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
