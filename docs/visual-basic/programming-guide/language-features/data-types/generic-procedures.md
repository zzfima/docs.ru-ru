---
title: Универсальные процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 16a629e07cf711778b3d8d1863958ec7a6300649
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350087"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="55df4-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55df4-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="55df4-103">*Универсальная процедура*, также называемая *универсальным методом*, представляет собой процедуру, определенную по крайней мере с одним параметром типа.</span><span class="sxs-lookup"><span data-stu-id="55df4-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="55df4-104">Это позволяет вызывающему коду адаптировать типы данных к их требованиям при каждом вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="55df4-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="55df4-105">Процедура не является универсальной просто путем определения внутри универсального класса или универсальной структуры.</span><span class="sxs-lookup"><span data-stu-id="55df4-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="55df4-106">Как универсальное, процедура должна принимать по крайней мере один параметр типа в дополнение к обычным параметрам, которые он может принимать.</span><span class="sxs-lookup"><span data-stu-id="55df4-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="55df4-107">Универсальный класс или структура может содержать неуниверсальные процедуры, а неуниверсальный класс, структура или модуль могут содержать универсальные процедуры.</span><span class="sxs-lookup"><span data-stu-id="55df4-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="55df4-108">Универсальная процедура может использовать свои параметры-типы в его стандартном списке параметров, в его возвращаемом типе, если он есть, и в коде процедуры.</span><span class="sxs-lookup"><span data-stu-id="55df4-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="55df4-109">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="55df4-109">Type Inference</span></span>  
 <span data-ttu-id="55df4-110">Можно вызвать универсальную процедуру без указания каких-либо аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="55df4-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="55df4-111">При таком вызове компилятор пытается определить подходящие типы данных для передачи аргументам типа процедуры.</span><span class="sxs-lookup"><span data-stu-id="55df4-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="55df4-112">Это называется *выводом типа*.</span><span class="sxs-lookup"><span data-stu-id="55df4-112">This is called *type inference*.</span></span> <span data-ttu-id="55df4-113">В следующем коде показан вызов, в котором компилятор определяет, что ему следует передать тип `String` в параметр типа `t`.</span><span class="sxs-lookup"><span data-stu-id="55df4-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="55df4-114">Если компилятор не может вывести аргументы типа из контекста вызова, он сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="55df4-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="55df4-115">Одной из возможных причин такой ошибки является несоответствие ранга массива.</span><span class="sxs-lookup"><span data-stu-id="55df4-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="55df4-116">Например, предположим, что вы определили нормальный параметр в качестве массива параметра типа.</span><span class="sxs-lookup"><span data-stu-id="55df4-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="55df4-117">При вызове универсальной процедуры, предоставляющей массив другого ранга (число измерений), несоответствие приводит к сбою определения типа.</span><span class="sxs-lookup"><span data-stu-id="55df4-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="55df4-118">В следующем коде показан вызов, в котором двумерный массив передается в процедуру, которая принимает одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="55df4-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="55df4-119">Вывод типа можно вызвать только путем пропуска всех аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="55df4-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="55df4-120">При указании одного аргумента типа необходимо указать все эти аргументы.</span><span class="sxs-lookup"><span data-stu-id="55df4-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="55df4-121">Вывод типа поддерживается только для универсальных процедур.</span><span class="sxs-lookup"><span data-stu-id="55df4-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="55df4-122">Невозможно вызвать определение типа в универсальных классах, структурах, интерфейсах или делегатах.</span><span class="sxs-lookup"><span data-stu-id="55df4-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55df4-123">Пример</span><span class="sxs-lookup"><span data-stu-id="55df4-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="55df4-124">Описание</span><span class="sxs-lookup"><span data-stu-id="55df4-124">Description</span></span>  
 <span data-ttu-id="55df4-125">В следующем примере определяется универсальная процедура `Function` для поиска определенного элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="55df4-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="55df4-126">Он определяет один параметр типа и использует его для создания двух параметров в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="55df4-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="55df4-127">Код</span><span class="sxs-lookup"><span data-stu-id="55df4-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="55df4-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="55df4-128">Comments</span></span>  
 <span data-ttu-id="55df4-129">В предыдущем примере требуется возможность сравнения `searchValue` с каждым элементом `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="55df4-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="55df4-130">Чтобы гарантировать эту возможность, он ограничивает параметр типа `T` для реализации интерфейса <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="55df4-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="55df4-131">В коде используется метод <xref:System.IComparable%601.CompareTo%2A> вместо оператора `=`, поскольку нет гарантии, что аргумент типа, предоставляемый для `T`, поддерживает оператор `=`.</span><span class="sxs-lookup"><span data-stu-id="55df4-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="55df4-132">Процедуру `findElement` можно проверить с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="55df4-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="55df4-133">Предыдущие вызовы `MsgBox` отображают "0", "1" и "-1" соответственно.</span><span class="sxs-lookup"><span data-stu-id="55df4-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55df4-134">См. также</span><span class="sxs-lookup"><span data-stu-id="55df4-134">See also</span></span>

- [<span data-ttu-id="55df4-135">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55df4-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="55df4-136">Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных</span><span class="sxs-lookup"><span data-stu-id="55df4-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="55df4-137">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="55df4-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="55df4-138">Процедуры</span><span class="sxs-lookup"><span data-stu-id="55df4-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="55df4-139">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="55df4-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="55df4-140">Список типов</span><span class="sxs-lookup"><span data-stu-id="55df4-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="55df4-141">Список параметров</span><span class="sxs-lookup"><span data-stu-id="55df4-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
