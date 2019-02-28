---
title: Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: c7510147e2abdcfbb71cf79412a9125724776685
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977556"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="da6b9-102">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da6b9-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="da6b9-103">Объект *свойство по умолчанию* — это свойство класса или структуры, которое ваш код может получить доступ без указания его.</span><span class="sxs-lookup"><span data-stu-id="da6b9-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="da6b9-104">Если вызывающий код задает класс или структуру, но не свойство и контекст разрешает доступ к свойству, Visual Basic разрешает доступ для этого класса или структуры свойство по умолчанию, если он существует.</span><span class="sxs-lookup"><span data-stu-id="da6b9-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="da6b9-105">Класс или структура может иметь не более одного свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da6b9-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="da6b9-106">Тем не менее можно перегружать свойство по умолчанию и иметь более одной версии.</span><span class="sxs-lookup"><span data-stu-id="da6b9-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="da6b9-107">Дополнительные сведения см. в разделе [по умолчанию](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="da6b9-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="da6b9-108">Чтобы объявить свойство по умолчанию</span><span class="sxs-lookup"><span data-stu-id="da6b9-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="da6b9-109">Объявите свойство обычным способом.</span><span class="sxs-lookup"><span data-stu-id="da6b9-109">Declare the property in the normal way.</span></span> <span data-ttu-id="da6b9-110">Не указывайте `Shared` или `Private` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="da6b9-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="da6b9-111">Включить `Default` ключевое слово в объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="da6b9-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="da6b9-112">Укажите хотя бы один параметр для свойства.</span><span class="sxs-lookup"><span data-stu-id="da6b9-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="da6b9-113">Нельзя определить свойство по умолчанию, которая не принимает хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="da6b9-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="da6b9-114">Чтобы вызвать свойство по умолчанию</span><span class="sxs-lookup"><span data-stu-id="da6b9-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="da6b9-115">Объявите переменную типа содержащего класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="da6b9-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2.  <span data-ttu-id="da6b9-116">Используйте имя переменной отдельно в выражении, где вы обычно содержит имя свойства.</span><span class="sxs-lookup"><span data-stu-id="da6b9-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3.  <span data-ttu-id="da6b9-117">После имени переменной список аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="da6b9-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="da6b9-118">Свойство по умолчанию необходимо выполнить хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="da6b9-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4.  <span data-ttu-id="da6b9-119">Чтобы получить значение свойства по умолчанию, используйте имя переменной, списку аргументов в выражении или после равенства (`=`) войдите в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="da6b9-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5.  <span data-ttu-id="da6b9-120">Чтобы задать значение свойства по умолчанию, используйте имя переменной со списком аргументов, в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="da6b9-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6.  <span data-ttu-id="da6b9-121">Всегда можно указать имя свойства по умолчанию, а также имя переменной, так же, как это делается для доступа к любому другому свойству.</span><span class="sxs-lookup"><span data-stu-id="da6b9-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="da6b9-122">Пример</span><span class="sxs-lookup"><span data-stu-id="da6b9-122">Example</span></span>  
 <span data-ttu-id="da6b9-123">В следующем примере объявляется свойство по умолчанию для класса.</span><span class="sxs-lookup"><span data-stu-id="da6b9-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="da6b9-124">Пример</span><span class="sxs-lookup"><span data-stu-id="da6b9-124">Example</span></span>  
 <span data-ttu-id="da6b9-125">Следующий пример демонстрирует вызов свойства по умолчанию `myProperty` класса `class1`.</span><span class="sxs-lookup"><span data-stu-id="da6b9-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="da6b9-126">Три оператора присваивания сохраняют значения в `myProperty`и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов считывает значения.</span><span class="sxs-lookup"><span data-stu-id="da6b9-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="da6b9-127">Наиболее распространенное использование свойства по умолчанию является <xref:Microsoft.VisualBasic.Collection.Item%2A> свойство для различных классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="da6b9-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="da6b9-128">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="da6b9-128">Robust Programming</span></span>  
 <span data-ttu-id="da6b9-129">Свойства по умолчанию может привести к небольшому сокращению символы исходного кода, но они могут сделать код более трудным для чтения.</span><span class="sxs-lookup"><span data-stu-id="da6b9-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="da6b9-130">Если вызывающий код не знакомы с класса или структуры, когда он ссылается на имя класса или структуры, он не может быть определенные ли такая ссылка обращается к классу или структуре или свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da6b9-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="da6b9-131">Это может привести к ошибкам компилятора или ошибки слабая логики времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="da6b9-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="da6b9-132">Отчасти можно уменьшить вероятность возникновения ошибки свойства по умолчанию, используя [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) тип компилятора, проверки для `On`.</span><span class="sxs-lookup"><span data-stu-id="da6b9-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="da6b9-133">Если вы планируете использовать предварительно определенный класс или структура в коде, необходимо определить, имеет ли он свойство по умолчанию и если да, что ее имя —.</span><span class="sxs-lookup"><span data-stu-id="da6b9-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="da6b9-134">Из-за эти недостатки можно не определять свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da6b9-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="da6b9-135">Для удобства чтения кода следует также учитывать всегда относятся ко всем свойствам явным образом, даже свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da6b9-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6b9-136">См. также</span><span class="sxs-lookup"><span data-stu-id="da6b9-136">See also</span></span>
- [<span data-ttu-id="da6b9-137">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="da6b9-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="da6b9-138">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="da6b9-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="da6b9-139">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="da6b9-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="da6b9-140">Default</span><span class="sxs-lookup"><span data-stu-id="da6b9-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="da6b9-141">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da6b9-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="da6b9-142">Практическое руководство. Создать свойство</span><span class="sxs-lookup"><span data-stu-id="da6b9-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="da6b9-143">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="da6b9-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="da6b9-144">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="da6b9-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="da6b9-145">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="da6b9-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="da6b9-146">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="da6b9-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
