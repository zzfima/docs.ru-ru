---
title: Процедуры свойств (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 118c9e776813f303ed921946f4cf6f1236ac02e3
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040977"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="a9ad7-102">Процедуры свойств (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9ad7-102">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="a9ad7-103">Процедура свойства — это серия Visual Basic инструкций, которые управляют пользовательским свойством модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="a9ad7-104">Процедуры свойств также называются свойствами *доступа к свойствам*.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-104">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="a9ad7-105">Visual Basic предоставляет следующие процедуры свойств.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-105">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="a9ad7-106">`Get` процедура возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="a9ad7-107">Он вызывается при доступе к свойству в выражении.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-107">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="a9ad7-108">`Set` процедура задает для свойства значение, включая ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="a9ad7-109">Он вызывается при присвоении значения свойству.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-109">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="a9ad7-110">Обычно процедуры свойств определяются парами, с помощью инструкций `Get` и `Set`, но можно определить только одну процедуру, если свойство доступно только для чтения ([Инструкция Get](../../../../visual-basic/language-reference/statements/get-statement.md)) или только для записи ([инструкция SET](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="a9ad7-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="a9ad7-111">При использовании автоматического реализуемого свойства можно опустить `Get` и `Set` процедуру.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="a9ad7-112">Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a9ad7-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="a9ad7-113">Свойства можно определить в классах, структурах и модулях.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="a9ad7-114">По умолчанию свойства являются `Public`. Это означает, что их можно вызывать из любого места в приложении, которое может получить доступ к контейнеру свойства.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="a9ad7-115">Сравнение свойств и переменных см. [в разделе различия между свойствами и переменными в Visual Basic](differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="a9ad7-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="a9ad7-116">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="a9ad7-116">Declaration syntax</span></span>

<span data-ttu-id="a9ad7-117">Само свойство определяется блоком кода, заключенным в [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) , и оператор `End Property`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="a9ad7-118">Внутри этого блока каждая процедура свойства отображается как внутренний блок, заключенный в оператор объявления (`Get` или `Set`) и соответствующее объявление `End`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="a9ad7-119">Синтаксис объявления свойства и его процедур выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9ad7-119">The syntax for declaring a property and its procedures is as follows:</span></span>

```vb
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
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

<span data-ttu-id="a9ad7-120">`Modifiers` может указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении, а также о том, доступно ли свойство только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="a9ad7-121">`AccessLevel` в процедуре `Get` или `Set` может быть любым уровнем, более четким, чем уровень доступа, заданный для самого свойства.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="a9ad7-122">Дополнительные сведения см. в разделе [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9ad7-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="a9ad7-123">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a9ad7-123">Data Type</span></span>

<span data-ttu-id="a9ad7-124">Тип данных свойства и основной уровень доступа определяются в операторе `Property`, а не в процедурах свойств.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="a9ad7-125">Свойство может иметь только один тип данных.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-125">A property can have only one data type.</span></span> <span data-ttu-id="a9ad7-126">Например, нельзя определить свойство для хранения `Decimal` значения, но получить значение `Double`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="a9ad7-127">Уровень доступа</span><span class="sxs-lookup"><span data-stu-id="a9ad7-127">Access Level</span></span>

<span data-ttu-id="a9ad7-128">Однако можно определить основной уровень доступа для свойства и дополнительно ограничить уровень доступа в одной из его процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="a9ad7-129">Например, можно определить `Public` свойство, а затем определить `Private Set` процедуру.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="a9ad7-130">Процедура `Get` остается `Public`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="a9ad7-131">Уровень доступа можно изменить только в одной из процедур свойства, и его можно сделать более узким, чем основной уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="a9ad7-132">Дополнительные сведения см. [в разделе инструкции. объявление свойства со смешанными уровнями доступа](how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a9ad7-132">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="a9ad7-133">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="a9ad7-133">Parameter declaration</span></span>

<span data-ttu-id="a9ad7-134">Каждый параметр объявляется так же, как и для [процедур подразделов](sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-134">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="a9ad7-135">Для каждого параметра в списке параметров используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a9ad7-135">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="a9ad7-136">Если параметр является необязательным, необходимо также указать значение по умолчанию в составе объявления.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="a9ad7-137">Для указания значения по умолчанию используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a9ad7-137">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="a9ad7-138">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="a9ad7-138">Property value</span></span>

<span data-ttu-id="a9ad7-139">В `Get` процедуре возвращаемое значение предоставляется вызывающему выражению как значение свойства.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="a9ad7-140">В `Set` процедуре новое значение свойства передается в параметр инструкции `Set`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="a9ad7-141">При явном объявлении параметра необходимо объявить его с тем же типом данных, что и свойство.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="a9ad7-142">Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления нового значения, присваиваемого свойству.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="a9ad7-143">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="a9ad7-143">Calling syntax</span></span>

<span data-ttu-id="a9ad7-144">Процедура свойства вызывается неявно путем создания ссылки на свойство.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="a9ad7-145">Имя свойства используется так же, как имя переменной, за исключением того, что необходимо указать значения для всех аргументов, которые не являются необязательными, а список аргументов необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="a9ad7-146">Если аргументы не указаны, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="a9ad7-147">Синтаксис неявного вызова `Set` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9ad7-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="a9ad7-148">Синтаксис неявного вызова `Get` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9ad7-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="a9ad7-149">Иллюстрация объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="a9ad7-149">Illustration of declaration and call</span></span>

<span data-ttu-id="a9ad7-150">Следующее свойство сохраняет полное имя как два составных имени: имя и фамилия.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="a9ad7-151">Когда вызывающий код считывает `fullName`, `Get` процедура объединяет два составных имени и возвращает полное имя.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="a9ad7-152">Когда вызывающий код присваивает новое полное имя, процедура `Set` пытается разбить ее на два составных имени.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="a9ad7-153">Если не удается найти пробел, он сохраняется как первое имя.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-153">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="a9ad7-154">В следующем примере показаны типичные вызовы процедур свойств `fullName`.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-154">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="a9ad7-155">См. также</span><span class="sxs-lookup"><span data-stu-id="a9ad7-155">See also</span></span>

- [<span data-ttu-id="a9ad7-156">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a9ad7-156">Procedures</span></span>](index.md)
- [<span data-ttu-id="a9ad7-157">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="a9ad7-157">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="a9ad7-158">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="a9ad7-158">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="a9ad7-159">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="a9ad7-159">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a9ad7-160">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9ad7-160">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="a9ad7-161">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="a9ad7-161">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="a9ad7-162">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="a9ad7-162">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="a9ad7-163">Инструкции. объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9ad7-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="a9ad7-164">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="a9ad7-164">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="a9ad7-165">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="a9ad7-165">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
