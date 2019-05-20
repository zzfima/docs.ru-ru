---
title: Руководство по программированию на C#. Получение адреса переменной
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: bc5776bc57096b88a71ff786915553ae9aa04b7b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635063"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="226d3-102">Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="226d3-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="226d3-103">Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of `&`:</span><span class="sxs-lookup"><span data-stu-id="226d3-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="226d3-104">Оператор address-of применяется только к переменным.</span><span class="sxs-lookup"><span data-stu-id="226d3-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="226d3-105">Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.</span><span class="sxs-lookup"><span data-stu-id="226d3-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span> <span data-ttu-id="226d3-106">Дополнительные сведения о перемещаемых переменных см. в разделе [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables) (Фиксированные и перемещаемые переменные).</span><span class="sxs-lookup"><span data-stu-id="226d3-106">For more information about moveable variables, see [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span></span> 
  
 <span data-ttu-id="226d3-107">Вам необходимо самостоятельно обеспечить проверку инициализации переменной.</span><span class="sxs-lookup"><span data-stu-id="226d3-107">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="226d3-108">Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="226d3-108">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="226d3-109">Получить адрес константы или значения нельзя.</span><span class="sxs-lookup"><span data-stu-id="226d3-109">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="226d3-110">Пример</span><span class="sxs-lookup"><span data-stu-id="226d3-110">Example</span></span>  
 <span data-ttu-id="226d3-111">В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`.</span><span class="sxs-lookup"><span data-stu-id="226d3-111">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="226d3-112">Переменная `number` инициализируется в результате назначения `*p`.</span><span class="sxs-lookup"><span data-stu-id="226d3-112">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="226d3-113">Если закомментировать этот оператор назначения, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет.</span><span class="sxs-lookup"><span data-stu-id="226d3-113">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="226d3-114">Скомпилируйте этот пример с использованием параметра компилятора [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="226d3-114">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="226d3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="226d3-115">See also</span></span>

- [<span data-ttu-id="226d3-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="226d3-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="226d3-117">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="226d3-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="226d3-118">Типы</span><span class="sxs-lookup"><span data-stu-id="226d3-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="226d3-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="226d3-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="226d3-120">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="226d3-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="226d3-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="226d3-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
