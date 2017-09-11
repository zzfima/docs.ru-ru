---
title: "Практическое руководство: определение параметра для процедуры (Visual Basic) | Документы Microsoft"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 5a29bab1c18920d293c51d83d4d8cffdcefe936c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="1796b-102">Практическое руководство. Объявление параметра для процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1796b-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="1796b-103">Объект *параметр* позволяет вызывающему коду передать значение в вызываемую процедуру при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="1796b-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="1796b-104">Каждый параметр процедуры объявляется так же, как объявить переменную, указав его имя и тип данных.</span><span class="sxs-lookup"><span data-stu-id="1796b-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="1796b-105">Можно также указать механизм передачи, и параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1796b-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="1796b-106">Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="1796b-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="1796b-107">Определение параметра процедуры</span><span class="sxs-lookup"><span data-stu-id="1796b-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="1796b-108">В объявлении процедуры добавьте имя параметра в список параметров процедуры, отделив его от других параметров запятыми.</span><span class="sxs-lookup"><span data-stu-id="1796b-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="1796b-109">Выберите тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="1796b-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="1796b-110">После имени параметра `As` предложение, чтобы указать тип данных.</span><span class="sxs-lookup"><span data-stu-id="1796b-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="1796b-111">Определите механизм передачи для параметра.</span><span class="sxs-lookup"><span data-stu-id="1796b-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="1796b-112">Обычно необходимо передавать параметр по значению, если не требуется, чтобы иметь возможность изменить его значение в вызывающем коде процедуры.</span><span class="sxs-lookup"><span data-stu-id="1796b-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="1796b-113">Перед именем параметра с [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для указания механизм передачи.</span><span class="sxs-lookup"><span data-stu-id="1796b-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="1796b-114">Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="1796b-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="1796b-115">Если аргумент является необязательным, укажите перед механизмом передачи [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) и соответствовать типу данных параметра со знака равенства (`=`) и значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1796b-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="1796b-116">В следующем примере определяется структура `Sub` процедуры с тремя параметрами.</span><span class="sxs-lookup"><span data-stu-id="1796b-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="1796b-117">Первые два являются обязательными, а третий — необязательным.</span><span class="sxs-lookup"><span data-stu-id="1796b-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="1796b-118">Объявления параметров в списке параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="1796b-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     <span data-ttu-id="1796b-119">[!code-vb[VbVbcnProcedures&#33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1796b-119">[!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="1796b-120">Первый параметр принимает `customer` объекта, и `updateCustomer` может непосредственно обновлять переменную, передаваемую в `c` , так как аргумент передается [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="1796b-120">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="1796b-121">Процедура не может изменить значения последних двух аргументов, поскольку они передаются [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="1796b-121">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="1796b-122">Если вызывающий код не предоставляет значение для `level` параметр [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] устанавливает его значение по умолчанию 0.</span><span class="sxs-lookup"><span data-stu-id="1796b-122">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="1796b-123">Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `Off`, `As` предложение необязательно при определении параметров.</span><span class="sxs-lookup"><span data-stu-id="1796b-123">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="1796b-124">Однако если любой из параметров использует `As` предложение, их необходимо его использование.</span><span class="sxs-lookup"><span data-stu-id="1796b-124">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="1796b-125">Если переключатель проверки типов имеет `On`, `As` предложение является обязательным для каждого определения параметра.</span><span class="sxs-lookup"><span data-stu-id="1796b-125">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="1796b-126">Задание типов данных для всех элементов программирования называется *строгой типизации*.</span><span class="sxs-lookup"><span data-stu-id="1796b-126">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="1796b-127">При задании `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обеспечивает строгую типизацию.</span><span class="sxs-lookup"><span data-stu-id="1796b-127">When you set `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforces strong typing.</span></span> <span data-ttu-id="1796b-128">Это настоятельно рекомендуется, по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="1796b-128">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="1796b-129">Он обеспечивает поддержку IntelliSense для переменных и параметров.</span><span class="sxs-lookup"><span data-stu-id="1796b-129">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="1796b-130">Это позволяет видеть их свойства и другие члены, при вводе в коде.</span><span class="sxs-lookup"><span data-stu-id="1796b-130">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="1796b-131">Это позволяет компилятору выполнять проверку типов.</span><span class="sxs-lookup"><span data-stu-id="1796b-131">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="1796b-132">Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение.</span><span class="sxs-lookup"><span data-stu-id="1796b-132">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="1796b-133">Обнаруживаются также вызовы методов для объектов, которые не поддерживают их.</span><span class="sxs-lookup"><span data-stu-id="1796b-133">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="1796b-134">Обеспечивается более быстрое выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="1796b-134">It results in faster execution of your code.</span></span> <span data-ttu-id="1796b-135">Одна из причин для этого является, если не указать тип данных для элемента программирования [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор присваивает его `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="1796b-135">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="1796b-136">Скомпилированному коду может потребоваться преобразовать вперед и назад между `Object` и других типов данных, что снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="1796b-136">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1796b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="1796b-137">See Also</span></span>  
 <span data-ttu-id="1796b-138">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-138">[Procedures](./index.md) </span></span>  
<span data-ttu-id="1796b-139"> [Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-139"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="1796b-140"> [Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-140"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="1796b-141"> [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-141"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="1796b-142"> [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-142"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="1796b-143"> [Рекурсивные процедуры](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-143"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="1796b-144"> [Перегрузка процедур](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-144"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="1796b-145"> [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="1796b-145"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="1796b-146"> [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="1796b-146"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
