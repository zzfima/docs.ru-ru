---
title: "Процедуры свойств (Visual Basic) | Документы Microsoft"
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
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6ba662a8cf9748b719bfbd7205ce65989e79d05a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="1afaa-102">Процедуры свойств (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1afaa-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="1afaa-103">Процедура свойства — это последовательность [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] операторы, которые управляют пользовательских свойств для модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="1afaa-103">A property procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="1afaa-104">Процедуры свойств также называются *свойствам*.</span><span class="sxs-lookup"><span data-stu-id="1afaa-104">Property procedures are also known as *property accessors*.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1afaa-105">предоставляет следующие процедуры свойств.</span><span class="sxs-lookup"><span data-stu-id="1afaa-105"> provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="1afaa-106">A `Get` процедура возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="1afaa-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="1afaa-107">Он вызывается при доступе к свойству в выражении.</span><span class="sxs-lookup"><span data-stu-id="1afaa-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="1afaa-108">A `Set` процедуры свойству присваивается значение, включая ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="1afaa-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="1afaa-109">Вызывается, когда значение присваивается свойству.</span><span class="sxs-lookup"><span data-stu-id="1afaa-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="1afaa-110">Обычно процедуры свойств определяются парами с помощью `Get` и `Set` инструкций, но можно определить и одиночную процедуру, если свойство доступно только для чтения ([оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)) или только для записи ([инструкция Set](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="1afaa-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="1afaa-111">Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="1afaa-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="1afaa-112">Дополнительные сведения см. в разделе [Auto-Implemented свойства](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1afaa-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="1afaa-113">Можно определить свойства в классах, структурах и модули.</span><span class="sxs-lookup"><span data-stu-id="1afaa-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="1afaa-114">Свойства, `Public` по умолчанию, что означает их можно вызывать из любого места в приложении, можно получить доступ к контейнеру свойства.</span><span class="sxs-lookup"><span data-stu-id="1afaa-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="1afaa-115">Сравнение свойств и переменных см. в разделе [различия между свойства и переменные в Visual Basic](./differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="1afaa-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="1afaa-116">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="1afaa-116">Declaration Syntax</span></span>  
 <span data-ttu-id="1afaa-117">Само свойство определяется с помощью блока кода, заключенного в [оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="1afaa-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="1afaa-118">Внутри этого блока каждая процедура свойства отображается в виде внутреннего блока, заключенного в операторе объявления (`Get` или `Set`) и соответствующим `End` объявления.</span><span class="sxs-lookup"><span data-stu-id="1afaa-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="1afaa-119">Синтаксис объявления свойства и его процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1afaa-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="1afaa-120">`Modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение, а также является ли свойство только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="1afaa-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="1afaa-121">`AccessLevel` На `Get` или `Set` процедура может быть любого уровня, являющегося более строгим, чем уровень доступа, указанный для самого свойства.</span><span class="sxs-lookup"><span data-stu-id="1afaa-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="1afaa-122">Дополнительные сведения см. в разделе [инструкции свойство](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1afaa-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="1afaa-123">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1afaa-123">Data Type</span></span>  
 <span data-ttu-id="1afaa-124">Тип данных свойства и уровень доступа определяются в `Property` инструкции, а не в процедурах свойства.</span><span class="sxs-lookup"><span data-stu-id="1afaa-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="1afaa-125">Свойство может иметь только один тип данных.</span><span class="sxs-lookup"><span data-stu-id="1afaa-125">A property can have only one data type.</span></span> <span data-ttu-id="1afaa-126">Например, невозможно определить свойство для хранения `Decimal` значения, но получить `Double` значение.</span><span class="sxs-lookup"><span data-stu-id="1afaa-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="1afaa-127">Уровень доступа</span><span class="sxs-lookup"><span data-stu-id="1afaa-127">Access Level</span></span>  
 <span data-ttu-id="1afaa-128">Тем не менее можно определить уровень доступа для свойства и ограничить уровень доступа в одной из его процедур.</span><span class="sxs-lookup"><span data-stu-id="1afaa-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="1afaa-129">Например, можно определить `Public` свойства, а затем определите `Private Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="1afaa-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="1afaa-130">`Get` Процедуры остается `Public`.</span><span class="sxs-lookup"><span data-stu-id="1afaa-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="1afaa-131">Можно изменить уровень доступа в одной из процедур свойств и можно сделать его более строгим, чем основной уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="1afaa-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="1afaa-132">Дополнительные сведения см. в разделе [как: объявление свойства со смешанной уровни доступа](./how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1afaa-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="1afaa-133">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="1afaa-133">Parameter Declaration</span></span>  
 <span data-ttu-id="1afaa-134">Каждый параметр объявляется так же, как для [Sub-процедуры](./sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="1afaa-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="1afaa-135">Синтаксис для каждого параметра в списке параметров выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1afaa-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="1afaa-136">Если аргумент является необязательным, необходимо также указать значение по умолчанию как часть его объявления.</span><span class="sxs-lookup"><span data-stu-id="1afaa-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="1afaa-137">Синтаксис для указания значения по умолчанию выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1afaa-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="1afaa-138">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="1afaa-138">Property Value</span></span>  
 <span data-ttu-id="1afaa-139">В `Get` процедура, возвращаемое значение передается в вызывающее выражение в качестве значения свойства.</span><span class="sxs-lookup"><span data-stu-id="1afaa-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="1afaa-140">В `Set` процедура, новое значение свойства передается параметру `Set` инструкции.</span><span class="sxs-lookup"><span data-stu-id="1afaa-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="1afaa-141">Если параметр объявлен явным образом, необходимо объявить его с тем же типом данных, как свойство.</span><span class="sxs-lookup"><span data-stu-id="1afaa-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="1afaa-142">Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления новое значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="1afaa-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="1afaa-143">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="1afaa-143">Calling Syntax</span></span>  
 <span data-ttu-id="1afaa-144">Процедура свойства вызывается неявно путем создания ссылки на свойство.</span><span class="sxs-lookup"><span data-stu-id="1afaa-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="1afaa-145">Используется имя свойства так же, как имя переменной, за исключением того, что необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="1afaa-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="1afaa-146">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="1afaa-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="1afaa-147">Синтаксис для неявного вызова функции `Set` используется следующая процедура:</span><span class="sxs-lookup"><span data-stu-id="1afaa-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="1afaa-148">Синтаксис для неявного вызова функции `Get` используется следующая процедура:</span><span class="sxs-lookup"><span data-stu-id="1afaa-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="1afaa-149">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="1afaa-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="1afaa-150">Следующее свойство сохраняет полное имя как два составных имени, имени и фамилии.</span><span class="sxs-lookup"><span data-stu-id="1afaa-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="1afaa-151">Когда вызывающий код считывает `fullName`, `Get` процедура объединяет два составных имени и возвращает полное имя.</span><span class="sxs-lookup"><span data-stu-id="1afaa-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="1afaa-152">Когда вызывающий код присваивает новое полное имя `Set` процедура пытается разделить его на два составных имени.</span><span class="sxs-lookup"><span data-stu-id="1afaa-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="1afaa-153">Если не удается найти пробел, он сохраняет их все как имя.</span><span class="sxs-lookup"><span data-stu-id="1afaa-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 <span data-ttu-id="1afaa-154">[!code-vb[VbVbcnProcedures №&8;](./codesnippet/VisualBasic/property-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1afaa-154">[!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="1afaa-155">В следующем примере показаны вызовы процедур свойств из `fullName`.</span><span class="sxs-lookup"><span data-stu-id="1afaa-155">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 <span data-ttu-id="1afaa-156">[!code-vb[VbVbcnProcedures №&9;](./codesnippet/VisualBasic/property-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1afaa-156">[!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1afaa-157">См. также</span><span class="sxs-lookup"><span data-stu-id="1afaa-157">See Also</span></span>  
 <span data-ttu-id="1afaa-158">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-158">[Procedures](./index.md) </span></span>  
<span data-ttu-id="1afaa-159"> [Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-159"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="1afaa-160"> [Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-160"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="1afaa-161"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-161"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="1afaa-162"> [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-162"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="1afaa-163"> [Практическое руководство: создание свойства](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-163"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="1afaa-164"> [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-164"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="1afaa-165"> [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-165"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="1afaa-166"> [Практическое руководство: поместить значение в свойстве](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="1afaa-166"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="1afaa-167"> [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="1afaa-167"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
