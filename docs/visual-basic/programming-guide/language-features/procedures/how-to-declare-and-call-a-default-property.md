---
title: Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c4f471eba42e47d6bef45a4d38abc0cbd2d32bc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="f315c-102">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f315c-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="f315c-103">Объект *свойство по умолчанию* свойство класса или структуры, ваш код может получить доступ без указания ее.</span><span class="sxs-lookup"><span data-stu-id="f315c-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="f315c-104">Если вызывающий код задает класс или структуру, но не свойство и контекст разрешает доступ к свойству, Visual Basic разрешает доступ к этого класса или структуры свойство по умолчанию, если он существует.</span><span class="sxs-lookup"><span data-stu-id="f315c-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="f315c-105">Класс или структура может иметь не более одного свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f315c-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="f315c-106">Тем не менее можно перегружать свойство по умолчанию и иметь более одной версии.</span><span class="sxs-lookup"><span data-stu-id="f315c-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="f315c-107">Дополнительные сведения см. в разделе [по умолчанию](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="f315c-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="f315c-108">Чтобы объявить свойство по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f315c-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="f315c-109">Объявите свойство обычным способом.</span><span class="sxs-lookup"><span data-stu-id="f315c-109">Declare the property in the normal way.</span></span> <span data-ttu-id="f315c-110">Не указывайте `Shared` или `Private` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="f315c-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="f315c-111">Включить `Default` ключевое слово в объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="f315c-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="f315c-112">Укажите по крайней мере один параметр для свойства.</span><span class="sxs-lookup"><span data-stu-id="f315c-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="f315c-113">Нельзя определить свойство по умолчанию, который не принимает хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="f315c-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="f315c-114">Вызов свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f315c-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="f315c-115">Объявите переменную типа содержащего класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="f315c-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  <span data-ttu-id="f315c-116">Используйте имя переменной отдельно в выражении, где обычно содержит имя свойства.</span><span class="sxs-lookup"><span data-stu-id="f315c-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  <span data-ttu-id="f315c-117">После имени переменной со списком аргументов в скобки.</span><span class="sxs-lookup"><span data-stu-id="f315c-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="f315c-118">Свойство по умолчанию должна принимать хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="f315c-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  <span data-ttu-id="f315c-119">Чтобы получить значение свойства по умолчанию, используется имя переменной со списком аргументов в выражении или после равенства (`=`) войти в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="f315c-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  <span data-ttu-id="f315c-120">Чтобы задать значение свойства по умолчанию, используется имя переменной со списком аргументов в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="f315c-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  <span data-ttu-id="f315c-121">Всегда можно указать имя свойства по умолчанию вместе с именем переменной, так же, как это делается для доступа к любым другим свойством.</span><span class="sxs-lookup"><span data-stu-id="f315c-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="f315c-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f315c-122">Example</span></span>  
 <span data-ttu-id="f315c-123">В следующем примере объявляется свойство по умолчанию для класса.</span><span class="sxs-lookup"><span data-stu-id="f315c-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a><span data-ttu-id="f315c-124">Пример</span><span class="sxs-lookup"><span data-stu-id="f315c-124">Example</span></span>  
 <span data-ttu-id="f315c-125">Следующий пример демонстрирует вызов свойства по умолчанию `myProperty` класса `class1`.</span><span class="sxs-lookup"><span data-stu-id="f315c-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="f315c-126">Три оператора присваивания сохраняют значения в `myProperty`и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов считывает значения.</span><span class="sxs-lookup"><span data-stu-id="f315c-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 <span data-ttu-id="f315c-127">Чаще всего используют свойство по умолчанию <xref:Microsoft.VisualBasic.Collection.Item%2A> свойство для различных классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="f315c-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f315c-128">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f315c-128">Robust Programming</span></span>  
 <span data-ttu-id="f315c-129">Свойства по умолчанию может привести к небольшому сокращению символы исходного кода, но они могут сделать код более сложным для восприятия.</span><span class="sxs-lookup"><span data-stu-id="f315c-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="f315c-130">Если вызывающий код не знаком с класса или структуры, когда он ссылается на имя класса или структуры, его невозможно точно определить ли такая ссылка обращается к классу или структуре или свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f315c-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="f315c-131">Это может привести к ошибкам компилятора или ошибки слабая логики времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f315c-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="f315c-132">Можно частично уменьшить вероятность ошибок, связанных с свойство по умолчанию с помощью всегда [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) для компилятора тип проверки `On`.</span><span class="sxs-lookup"><span data-stu-id="f315c-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="f315c-133">Если вы планируете использовать предварительно определенный класс или структуру в коде, необходимо определить, имеет ли он свойство по умолчанию и если да, то, что ее имя —.</span><span class="sxs-lookup"><span data-stu-id="f315c-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="f315c-134">Из-за эти недостатки можно не определять свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f315c-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="f315c-135">Для удобства чтения кода следует также учитывать всегда ссылается на все свойства явным образом, даже свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f315c-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f315c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f315c-136">See Also</span></span>  
 [<span data-ttu-id="f315c-137">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="f315c-137">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="f315c-138">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="f315c-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f315c-139">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="f315c-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="f315c-140">Default</span><span class="sxs-lookup"><span data-stu-id="f315c-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)  
 [<span data-ttu-id="f315c-141">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f315c-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="f315c-142">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="f315c-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="f315c-143">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="f315c-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="f315c-144">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="f315c-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="f315c-145">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="f315c-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="f315c-146">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="f315c-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
