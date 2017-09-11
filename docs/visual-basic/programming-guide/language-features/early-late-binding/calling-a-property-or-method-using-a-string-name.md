---
title: "Вызов свойства или метода с помощью строкового имени (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6de5e655b3d4d42283b81507d7f08e0eb0b9424d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="cb75f-102">Вызов свойства или метода с помощью строкового имени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb75f-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="cb75f-103">В большинстве случаев доступ к свойствам и методам объекта во время разработки и писать код для их обработки.</span><span class="sxs-lookup"><span data-stu-id="cb75f-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="cb75f-104">Однако в некоторых случаях может не известно, какие свойства и методы объекта заранее или необходима гибкость конечному пользователю для указания свойств или выполнения методов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cb75f-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="cb75f-105">CallByName-функция</span><span class="sxs-lookup"><span data-stu-id="cb75f-105">CallByName Function</span></span>  
 <span data-ttu-id="cb75f-106">Рассмотрим, например, клиентское приложение, которое вычисляет выражения, введенные пользователем с помощью передачи оператора COM-компонент.</span><span class="sxs-lookup"><span data-stu-id="cb75f-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="cb75f-107">Предположим, что постоянно добавляются новые функции для компонентов, которым необходимы новые операторы.</span><span class="sxs-lookup"><span data-stu-id="cb75f-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="cb75f-108">При использовании методов доступа к объекту standard, необходимо перекомпилировать и переустановке клиентского приложения, прежде чем его можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="cb75f-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="cb75f-109">Чтобы избежать этого, можно использовать `CallByName` функции для передачи новых операторов в виде строк без изменения приложения.</span><span class="sxs-lookup"><span data-stu-id="cb75f-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="cb75f-110">`CallByName` Функция позволяет использовать строку для указания свойства или метода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cb75f-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="cb75f-111">Сигнатура для `CallByName` выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb75f-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="cb75f-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="cb75f-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="cb75f-113">Первый аргумент, *объекта*, принимает имя объекта, нужно действовать.</span><span class="sxs-lookup"><span data-stu-id="cb75f-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="cb75f-114">*ProcedureName* аргумент принимает строку, содержащую имя метода или свойства вызываемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb75f-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="cb75f-115">*CallType* аргумент принимает константу, представляющую тип процедуры для вызова: метод (`Microsoft.VisualBasic.CallType.Method`), чтение свойства (`Microsoft.VisualBasic.CallType.Get`), или свойства (`Microsoft.VisualBasic.CallType.Set`).</span><span class="sxs-lookup"><span data-stu-id="cb75f-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="cb75f-116">*Аргументы* аргумент, который является необязательным, принимает массив объектов типа `Object` , содержащий любые аргументы для процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb75f-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="cb75f-117">Можно использовать `CallByName` с классами в текущем решении, но чаще всего используется для доступа к объектам COM или объектам из [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки.</span><span class="sxs-lookup"><span data-stu-id="cb75f-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="cb75f-118">Предположим, добавьте ссылку на сборку, содержащую класс с именем `MathClass`, который имеет новую функцию с именем `SquareRoot`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="cb75f-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 <span data-ttu-id="cb75f-119">[!code-vb[VbVbalrOOP&#53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb75f-119">[!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span></span>  
  
 <span data-ttu-id="cb75f-120">Приложение может использовать текстовые поля для элемента управления, какой метод будет вызван и ее аргументов.</span><span class="sxs-lookup"><span data-stu-id="cb75f-120">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="cb75f-121">Например если `TextBox1` содержит выражение для вычисления, и `TextBox2` — используется для ввода имени функции, можно использовать следующий код для вызова `SquareRoot` выражения в `TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="cb75f-121">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 <span data-ttu-id="cb75f-122">[!code-vb[VbVbalrOOP&#54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb75f-122">[!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span></span>  
  
 <span data-ttu-id="cb75f-123">Если ввести «64» в `TextBox1`, «SquareRoot» в `TextBox2`и затем вызвать `CallMath` процедура, квадратный корень числа в `TextBox1` вычисляется.</span><span class="sxs-lookup"><span data-stu-id="cb75f-123">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="cb75f-124">Код в примере вызывает `SquareRoot` функции (которая принимает строку, содержащую выражение, проверяемое как обязательный аргумент) и возвращает «8» в `TextBox1` (квадратный корень из 64).</span><span class="sxs-lookup"><span data-stu-id="cb75f-124">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="cb75f-125">Конечно, если пользователь введет недопустимую строку в `TextBox2`, если строка содержит имя свойства вместо метода или если метод имеет дополнительный аргумент, то во время выполнения возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="cb75f-125">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="cb75f-126">Необходимо добавить надлежащий код обработки ошибок при использовании `CallByName` чтобы реагировать на эти или другие ошибки.</span><span class="sxs-lookup"><span data-stu-id="cb75f-126">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb75f-127">Хотя `CallByName` функция может быть полезной в некоторых случаях, необходимо учитывать ее влияние на производительность — использование `CallByName` для вызова процедуры немного медленнее, чем вызов с поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="cb75f-127">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="cb75f-128">Если вы вызываете функцию, которая вызывается несколько раз, например в цикле, `CallByName` может иметь существенно повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="cb75f-128">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb75f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="cb75f-129">See Also</span></span>  
 <span data-ttu-id="cb75f-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span><span class="sxs-lookup"><span data-stu-id="cb75f-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span></span>   
<span data-ttu-id="cb75f-131"> [Определение типа объекта](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span><span class="sxs-lookup"><span data-stu-id="cb75f-131"> [Determining Object Type](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span></span>
