---
title: Generic Procedures in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e019ca32277f93f798e99e996a3670c8302ba9b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="4653e-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4653e-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="4653e-103">Объект *универсальной процедуры*, который также называется *универсальный метод*, — это процедура, определенная с помощью по крайней мере один тип параметра.</span><span class="sxs-lookup"><span data-stu-id="4653e-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="4653e-104">Это позволяет вызывающий код, чтобы адаптировать типы данных к его требованиям при каждом вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="4653e-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="4653e-105">Процедура не является универсальным просто посредством она определена внутри универсального класса или структурой универсального типа.</span><span class="sxs-lookup"><span data-stu-id="4653e-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="4653e-106">Чтобы быть универсальной, процедура должна принимать хотя бы один параметр типа, в дополнение к обычным параметрам, которые может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="4653e-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="4653e-107">Универсальный класс или структура может содержать неуниверсальные процедуры, а неуниверсальные класс, структура, или модуль может содержать универсальные процедуры.</span><span class="sxs-lookup"><span data-stu-id="4653e-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="4653e-108">Универсальную процедуру можно использовать его параметров типа в обычном списке параметров, в возвращаемом типе, если он имеет один и процедуру его код.</span><span class="sxs-lookup"><span data-stu-id="4653e-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="4653e-109">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="4653e-109">Type Inference</span></span>  
 <span data-ttu-id="4653e-110">Универсальная процедура можно вызвать без указания аргументов типа вообще.</span><span class="sxs-lookup"><span data-stu-id="4653e-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="4653e-111">При ее вызове таким образом, компилятор пытается определить соответствующий тип данных для передачи аргументов в процедуру типа.</span><span class="sxs-lookup"><span data-stu-id="4653e-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="4653e-112">Это называется *вывод типа*.</span><span class="sxs-lookup"><span data-stu-id="4653e-112">This is called *type inference*.</span></span> <span data-ttu-id="4653e-113">В следующем коде показан вызов в котором компилятор выводит, что ему следует передать тип `String` в параметр типа `t`.</span><span class="sxs-lookup"><span data-stu-id="4653e-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 <span data-ttu-id="4653e-114">Если компилятор не может вывести аргументы типа из контекста вызова, он сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4653e-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="4653e-115">Одной из возможных причин такой ошибки является несоответствие ранга массива.</span><span class="sxs-lookup"><span data-stu-id="4653e-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="4653e-116">Например предположим, что определили обычные параметры в виде байтового массива параметром типа.</span><span class="sxs-lookup"><span data-stu-id="4653e-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="4653e-117">При вызове универсальной процедуры предоставив массив различных ранг (число измерений), несоответствие вызывает сбой вывода типа.</span><span class="sxs-lookup"><span data-stu-id="4653e-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="4653e-118">В следующем коде показан вызов в двумерный массив передаваемый в процедуру, ожидающую одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="4653e-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 <span data-ttu-id="4653e-119">Определения типов можно вызвать только путем пропуска все аргументы типа.</span><span class="sxs-lookup"><span data-stu-id="4653e-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="4653e-120">Если указывается один аргумент типа, необходимо указать их все.</span><span class="sxs-lookup"><span data-stu-id="4653e-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="4653e-121">Вывод типа поддерживается только для универсальных процедур.</span><span class="sxs-lookup"><span data-stu-id="4653e-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="4653e-122">Невозможно вызвать вывод типа на универсальные классы, структуры, интерфейсы и делегаты.</span><span class="sxs-lookup"><span data-stu-id="4653e-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4653e-123">Пример</span><span class="sxs-lookup"><span data-stu-id="4653e-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="4653e-124">Описание</span><span class="sxs-lookup"><span data-stu-id="4653e-124">Description</span></span>  
 <span data-ttu-id="4653e-125">В следующем примере определяется универсальный `Function` процедуру для поиска конкретного элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="4653e-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="4653e-126">Он определяет один параметр типа и использует его для создания двух параметров в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="4653e-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4653e-127">Код</span><span class="sxs-lookup"><span data-stu-id="4653e-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="4653e-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4653e-128">Comments</span></span>  
 <span data-ttu-id="4653e-129">В предыдущем примере требуется возможность сравнения `searchValue` с каждым элементом `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="4653e-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="4653e-130">Чтобы обеспечить эту возможность, параметр типа ограничен `T` для реализации <xref:System.IComparable%601> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4653e-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="4653e-131">Код использует <xref:System.IComparable%601.CompareTo%2A> вместо метода `=` оператор, так как нет никакой гарантии, что аргумент типа, предоставляемый для `T` поддерживает `=` оператор.</span><span class="sxs-lookup"><span data-stu-id="4653e-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="4653e-132">Можно проверить `findElement` процедуры следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="4653e-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 <span data-ttu-id="4653e-133">Предыдущие вызовы `MsgBox` отображают «0», «1» и «-1"соответственно.</span><span class="sxs-lookup"><span data-stu-id="4653e-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4653e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4653e-134">See Also</span></span>  
 [<span data-ttu-id="4653e-135">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4653e-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="4653e-136">Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных</span><span class="sxs-lookup"><span data-stu-id="4653e-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="4653e-137">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="4653e-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="4653e-138">Процедуры</span><span class="sxs-lookup"><span data-stu-id="4653e-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="4653e-139">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="4653e-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="4653e-140">Список типов</span><span class="sxs-lookup"><span data-stu-id="4653e-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="4653e-141">Список параметров</span><span class="sxs-lookup"><span data-stu-id="4653e-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
