---
title: "Оператор fixed (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
dev_langs:
- CSharp
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4e1f810f6e6cfaef3a65c7391f074b414ef18b5a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="d194b-102">Оператор fixed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d194b-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="d194b-103">Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную.</span><span class="sxs-lookup"><span data-stu-id="d194b-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="d194b-104">Оператор `fixed` допускается только в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="d194b-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="d194b-105">`Fixed` также можно использовать для создания [буферов фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="d194b-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="d194b-106">Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора.</span><span class="sxs-lookup"><span data-stu-id="d194b-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="d194b-107">Без `fixed` указатели на перемещаемые управляемые переменные были бы мало полезны, так как при сборке мусора переменные переносились бы непредсказуемым образом.</span><span class="sxs-lookup"><span data-stu-id="d194b-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="d194b-108">Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.</span><span class="sxs-lookup"><span data-stu-id="d194b-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 <span data-ttu-id="d194b-109">[!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d194b-109">[!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]</span></span>  
  
 <span data-ttu-id="d194b-110">Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной.</span><span class="sxs-lookup"><span data-stu-id="d194b-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="d194b-111">В приведенном ниже примере демонстрируется использование переменных адресов, массивов и строк.</span><span class="sxs-lookup"><span data-stu-id="d194b-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="d194b-112">Дополнительные сведения о буферах фиксированного размера см. в разделе [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="d194b-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="d194b-113">[!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d194b-113">[!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]</span></span>  
  
 <span data-ttu-id="d194b-114">Можно инициализировать несколько указателей одного типа.</span><span class="sxs-lookup"><span data-stu-id="d194b-114">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="d194b-115">Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="d194b-115">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 <span data-ttu-id="d194b-116">[!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d194b-116">[!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]</span></span>  
  
 <span data-ttu-id="d194b-117">После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="d194b-117">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="d194b-118">Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`.</span><span class="sxs-lookup"><span data-stu-id="d194b-118">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d194b-119">Указатели, инициализированные в фиксированных операторах, изменять нельзя.</span><span class="sxs-lookup"><span data-stu-id="d194b-119">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="d194b-120">В небезопасном режиме вы можете выделить память в стеке, где сборка мусора не производится и, соответственно, закрепление не требуется.</span><span class="sxs-lookup"><span data-stu-id="d194b-120">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="d194b-121">Дополнительные сведения см. в разделе [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="d194b-121">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d194b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="d194b-122">Example</span></span>  
 <span data-ttu-id="d194b-123">[!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d194b-123">[!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d194b-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d194b-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d194b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d194b-125">See Also</span></span>  
 <span data-ttu-id="d194b-126">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d194b-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d194b-127">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d194b-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d194b-128">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d194b-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d194b-129">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="d194b-129">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="d194b-130">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="d194b-130">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

