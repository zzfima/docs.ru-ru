---
title: "Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic | Документы Microsoft"
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
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: 7cfd476def67ccf46e524da7943680f9e34b6a26
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="f0b62-102">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0b62-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="f0b62-103">Объект *по умолчанию свойство* является свойством класса или структуры, созданный код имеет доступ без его указания.</span><span class="sxs-lookup"><span data-stu-id="f0b62-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="f0b62-104">Если вызывающий код задает класс или структуру, но не со свойством, а контекст разрешает доступ к свойству [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] разрешает доступ к этого класса или структуры свойство по умолчанию, если он существует.</span><span class="sxs-lookup"><span data-stu-id="f0b62-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="f0b62-105">Класс или структура может иметь не более одного свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0b62-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="f0b62-106">Тем не менее можно перегружать свойство по умолчанию и иметь более одной версии.</span><span class="sxs-lookup"><span data-stu-id="f0b62-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="f0b62-107">Дополнительные сведения см. в разделе [по умолчанию](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="f0b62-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="f0b62-108">Для объявления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f0b62-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="f0b62-109">Объявите свойство обычным способом.</span><span class="sxs-lookup"><span data-stu-id="f0b62-109">Declare the property in the normal way.</span></span> <span data-ttu-id="f0b62-110">Не указывайте `Shared` или `Private` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="f0b62-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="f0b62-111">Включить `Default` ключевое слово в объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="f0b62-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="f0b62-112">Укажите хотя бы один параметр свойства.</span><span class="sxs-lookup"><span data-stu-id="f0b62-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="f0b62-113">Нельзя определить свойство по умолчанию, которая не принимает хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="f0b62-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     <span data-ttu-id="f0b62-114">[!code-vb[VbVbcnProcedures&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-114">[!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span></span>  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="f0b62-115">Для вызова свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f0b62-115">To call a default property</span></span>  
  
1.  <span data-ttu-id="f0b62-116">Объявите переменную типа содержащего класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="f0b62-116">Declare a variable of the containing class or structure type.</span></span>  
  
     <span data-ttu-id="f0b62-117">[!code-vb[VbVbcnProcedures №&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-117">[!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span></span>  
  
2.  <span data-ttu-id="f0b62-118">Используйте имя переменной отдельно в выражении, где вы обычно содержит имя свойства.</span><span class="sxs-lookup"><span data-stu-id="f0b62-118">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     <span data-ttu-id="f0b62-119">[!code-vb[VbVbcnProcedures&#21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-119">[!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span></span>  
  
3.  <span data-ttu-id="f0b62-120">После имени переменной список аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="f0b62-120">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="f0b62-121">Свойство по умолчанию должна принимать хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="f0b62-121">A default property must take at least one argument.</span></span>  
  
     <span data-ttu-id="f0b62-122">[!code-vb[VbVbcnProcedures&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-122">[!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span></span>  
  
4.  <span data-ttu-id="f0b62-123">Чтобы получить значение свойства по умолчанию, используйте имя переменной со списком аргументов в выражении или после равенства (`=`) входа в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="f0b62-123">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="f0b62-124">[!code-vb[VbVbcnProcedures&#15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-124">[!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span></span>  
  
5.  <span data-ttu-id="f0b62-125">Чтобы задать значение свойства по умолчанию, используйте имя переменной со списком аргументов слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="f0b62-125">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="f0b62-126">[!code-vb[VbVbcnProcedures&#14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-126">[!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span></span>  
  
6.  <span data-ttu-id="f0b62-127">Всегда можно указать имя свойства по умолчанию вместе с именем переменной, так же, как это делается для доступа к любым другим свойством.</span><span class="sxs-lookup"><span data-stu-id="f0b62-127">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     <span data-ttu-id="f0b62-128">[!code-vb[VbVbcnProcedures&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-128">[!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0b62-129">Пример</span><span class="sxs-lookup"><span data-stu-id="f0b62-129">Example</span></span>  
 <span data-ttu-id="f0b62-130">В следующем примере объявляется свойство по умолчанию для класса.</span><span class="sxs-lookup"><span data-stu-id="f0b62-130">The following example declares a default property on a class.</span></span>  
  
 <span data-ttu-id="f0b62-131">[!code-vb[VbVbcnProcedures&#12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-131">[!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0b62-132">Пример</span><span class="sxs-lookup"><span data-stu-id="f0b62-132">Example</span></span>  
 <span data-ttu-id="f0b62-133">Следующий пример демонстрирует вызов свойства по умолчанию `myProperty` класса `class1`.</span><span class="sxs-lookup"><span data-stu-id="f0b62-133">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="f0b62-134">Три оператора присваивания сохраняют значения в `myProperty`и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>вызов считывает значения.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="f0b62-134">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 <span data-ttu-id="f0b62-135">[!code-vb[VbVbcnProcedures&#13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0b62-135">[!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span></span>  
  
 <span data-ttu-id="f0b62-136">Наиболее распространенное использование свойства по умолчанию является <xref:Microsoft.VisualBasic.Collection.Item%2A>Свойства для различных классов коллекций.</xref:Microsoft.VisualBasic.Collection.Item%2A></span><span class="sxs-lookup"><span data-stu-id="f0b62-136">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f0b62-137">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f0b62-137">Robust Programming</span></span>  
 <span data-ttu-id="f0b62-138">Свойства по умолчанию может привести к небольшому сокращению знаки исходного кода, но они могут сделать ваш код более сложным для чтения.</span><span class="sxs-lookup"><span data-stu-id="f0b62-138">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="f0b62-139">Если вызывающий код не знаком с классом или структурой, когда он ссылается на имя класса или структуры, ее нельзя быть уверенным ли эта ссылка обращается к классу или структуре или свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0b62-139">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="f0b62-140">Это может привести к ошибкам компилятора или ошибки слабая логики времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0b62-140">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="f0b62-141">Можно частично уменьшить вероятность ошибок, связанных с свойство по умолчанию с помощью всегда [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Чтобы задать тип проверки компилятором `On`.</span><span class="sxs-lookup"><span data-stu-id="f0b62-141">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="f0b62-142">Если вы планируете использовать предварительно определенный класс или структуру в коде, необходимо определить, имеет ли он свойство по умолчанию и если да, то, что ее имя —.</span><span class="sxs-lookup"><span data-stu-id="f0b62-142">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="f0b62-143">Из-за этих недостатков можно не определять свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0b62-143">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="f0b62-144">Для удобства чтения кода следует также учитывать всегда ссылке на все свойства явным образом, даже свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0b62-144">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b62-145">См. также</span><span class="sxs-lookup"><span data-stu-id="f0b62-145">See Also</span></span>  
 <span data-ttu-id="f0b62-146">[Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-146">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="f0b62-147"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-147"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="f0b62-148"> [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-148"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="f0b62-149"> [По умолчанию](../../../../visual-basic/language-reference/modifiers/default.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-149"> [Default](../../../../visual-basic/language-reference/modifiers/default.md) </span></span>  
<span data-ttu-id="f0b62-150"> [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-150"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="f0b62-151"> [Практическое руководство: создание свойства](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-151"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="f0b62-152"> [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-152"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="f0b62-153"> [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-153"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="f0b62-154"> [Практическое руководство: поместить значение в свойстве](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="f0b62-154"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="f0b62-155"> [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="f0b62-155"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
