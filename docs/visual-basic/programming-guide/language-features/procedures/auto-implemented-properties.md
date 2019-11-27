---
title: Автоматически реализуемые свойства
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: b322bd2215c95298be0a33ace1f3590a63878e24
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350388"
---
# <a name="auto-implemented-properties-visual-basic"></a><span data-ttu-id="50310-102">Автоматически реализуемые свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50310-102">Auto-Implemented Properties (Visual Basic)</span></span>
<span data-ttu-id="50310-103">*Автоматические реализованные свойства* позволяют быстро указывать свойство класса без необходимости написания кода для `Get` и `Set` свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-103">*Auto-implemented properties* enable you to quickly specify a property of a class without having to write code to `Get` and `Set` the property.</span></span> <span data-ttu-id="50310-104">При написании кода для автоматически реализуемого свойства компилятор Visual Basic автоматически создает закрытое поле для хранения переменной свойства, в дополнение к созданию связанных процедур `Get` и `Set`.</span><span class="sxs-lookup"><span data-stu-id="50310-104">When you write code for an auto-implemented property, the Visual Basic compiler automatically creates a private field to store the property variable in addition to creating the associated `Get` and `Set` procedures.</span></span>  
  
 <span data-ttu-id="50310-105">С помощью автоматически реализуемых свойств вы сможете объявлять свойства, включая значение по умолчанию, в одной строке.</span><span class="sxs-lookup"><span data-stu-id="50310-105">With auto-implemented properties, a property, including a default value, can be declared in a single line.</span></span> <span data-ttu-id="50310-106">В следующем примере показано три объявления свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-106">The following example shows three property declarations.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 <span data-ttu-id="50310-107">Автоматически реализуемые свойства эквивалентны свойствам, значения которых хранятся в закрытом поле.</span><span class="sxs-lookup"><span data-stu-id="50310-107">An auto-implemented property is equivalent to a property for which the property value is stored in a private field.</span></span> <span data-ttu-id="50310-108">В следующем примере кода показано автоматически реализуемое свойство.</span><span class="sxs-lookup"><span data-stu-id="50310-108">The following code example shows an auto-implemented property.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 <span data-ttu-id="50310-109">В следующем примере кода показан эквивалентный код для предыдущего примера автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-109">The following code example shows the equivalent code for the previous auto-implemented property example.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 <span data-ttu-id="50310-110">В следующем примере кода показана реализация свойств только для чтения:</span><span class="sxs-lookup"><span data-stu-id="50310-110">The following code show implementing readonly properties:</span></span>  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="50310-111">Вы можете назначить свойству выражения инициализации, как показано в примере, или можно присвоить значения свойствам в конструкторе этого типа.</span><span class="sxs-lookup"><span data-stu-id="50310-111">You can assign to the property with initialization expressions as shown in the example, or you can assign to the properties in the containing type’s constructor.</span></span>  <span data-ttu-id="50310-112">Резервные поля свойств только для чтения можно назначить в любое время.</span><span class="sxs-lookup"><span data-stu-id="50310-112">You can assign to the backing fields of readonly properties at any time.</span></span>  
  
## <a name="backing-field"></a><span data-ttu-id="50310-113">Резервное поле</span><span class="sxs-lookup"><span data-stu-id="50310-113">Backing Field</span></span>  
 <span data-ttu-id="50310-114">При объявлении автоматически реализуемого свойства Visual Basic автоматически создает скрытое закрытое поле, называемое *резервным полем* , которое содержит значение свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-114">When you declare an auto-implemented property, Visual Basic automatically creates a hidden private field called the *backing field* to contain the property value.</span></span> <span data-ttu-id="50310-115">Имя резервного поля — это имя автоматически реализуемого свойства, с добавленным в начало знаком подчеркивания (_).</span><span class="sxs-lookup"><span data-stu-id="50310-115">The backing field name is the auto-implemented property name preceded by an underscore (_).</span></span> <span data-ttu-id="50310-116">Например, при объявлении автоматически реализуемого свойства с именем `ID` именем резервного поля будет `_ID`.</span><span class="sxs-lookup"><span data-stu-id="50310-116">For example, if you declare an auto-implemented property named `ID`, the backing field is named `_ID`.</span></span> <span data-ttu-id="50310-117">Если добавить элемент класса также с именем `_ID`, возникнет конфликт имен, и Visual Basic сообщает об ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="50310-117">If you include a member of your class that is also named `_ID`, you produce a naming conflict and Visual Basic reports a compiler error.</span></span>  
  
 <span data-ttu-id="50310-118">Резервное поле также имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="50310-118">The backing field also has the following characteristics:</span></span>  
  
- <span data-ttu-id="50310-119">модификатор доступа для резервного поля — всегда `Private`, даже если само свойство имеет другой уровень доступа, например `Public`;</span><span class="sxs-lookup"><span data-stu-id="50310-119">The access modifier for the backing field is always `Private`, even when the property itself has a different access level, such as `Public`.</span></span>  
  
- <span data-ttu-id="50310-120">если свойство помечено как `Shared`, резервное поле также будет общим;</span><span class="sxs-lookup"><span data-stu-id="50310-120">If the property is marked as `Shared`, the backing field also is shared.</span></span>  
  
- <span data-ttu-id="50310-121">атрибуты, указанные для свойства, не применяются к резервному полю;</span><span class="sxs-lookup"><span data-stu-id="50310-121">Attributes specified for the property do not apply to the backing field.</span></span>  
  
- <span data-ttu-id="50310-122">доступ к резервному полю можно получить из кода внутри класса и из средств отладки, например окна контрольных значений.</span><span class="sxs-lookup"><span data-stu-id="50310-122">The backing field can be accessed from code within the class and from debugging tools such as the Watch window.</span></span> <span data-ttu-id="50310-123">Однако резервное поле не отображается в списке предложений IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="50310-123">However, the backing field does not show in an IntelliSense word completion list.</span></span>  
  
## <a name="initializing-an-auto-implemented-property"></a><span data-ttu-id="50310-124">Инициализация автоматически реализуемого свойства</span><span class="sxs-lookup"><span data-stu-id="50310-124">Initializing an Auto-Implemented Property</span></span>  
 <span data-ttu-id="50310-125">Любое выражение, которое может использоваться для инициализации поля, можно применять для инициализации автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-125">Any expression that can be used to initialize a field is valid for initializing an auto-implemented property.</span></span> <span data-ttu-id="50310-126">При инициализации автоматически реализуемого свойства выражение анализируется и передается процедуре `Set` для свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-126">When you initialize an auto-implemented property, the expression is evaluated and passed to the `Set` procedure for the property.</span></span> <span data-ttu-id="50310-127">В следующих примерах кода показаны некоторые автоматически реализуемые свойства с начальными значениями.</span><span class="sxs-lookup"><span data-stu-id="50310-127">The following code examples show some auto-implemented properties that include initial values.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 <span data-ttu-id="50310-128">Невозможно инициализировать автоматически реализуемое свойство, которое является элементом `Interface` или помечено как `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="50310-128">You cannot initialize an auto-implemented property that is a member of an `Interface`, or one that is marked `MustOverride`.</span></span>  
  
 <span data-ttu-id="50310-129">При объявлении автоматически реализуемого свойства как элемента `Structure` его можно инициализировать, только если оно помечено как `Shared`.</span><span class="sxs-lookup"><span data-stu-id="50310-129">When you declare an auto-implemented property as a member of a `Structure`, you can only initialize the auto-implemented property if it is marked as `Shared`.</span></span>  
  
 <span data-ttu-id="50310-130">При объявлении автоматически реализуемого свойства как массива невозможно указать явные границы массива.</span><span class="sxs-lookup"><span data-stu-id="50310-130">When you declare an auto-implemented property as an array, you cannot specify explicit array bounds.</span></span> <span data-ttu-id="50310-131">Однако можно задать значение с помощью инициализатора массива, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="50310-131">However, you can supply a value by using an array initializer, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a><span data-ttu-id="50310-132">Определения свойств, для которых требуется стандартный синтаксис</span><span class="sxs-lookup"><span data-stu-id="50310-132">Property Definitions That Require Standard Syntax</span></span>  
 <span data-ttu-id="50310-133">Автоматически реализуемые свойства удобны и поддерживают множество сценариев программирования.</span><span class="sxs-lookup"><span data-stu-id="50310-133">Auto-implemented properties are convenient and support many programming scenarios.</span></span> <span data-ttu-id="50310-134">Однако существуют ситуации, в которых нельзя использовать автоматическое реализуемое свойство и вместо этого использовать стандартный или *Расширенный*синтаксис свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-134">However, there are situations in which you cannot use an auto-implemented property and must instead use standard, or *expanded*, property syntax.</span></span>  
  
 <span data-ttu-id="50310-135">Расширенный синтаксис определения свойства необходимо использовать, если вам нужно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="50310-135">You have to use expanded property-definition syntax if you want to do any one of the following:</span></span>  
  
- <span data-ttu-id="50310-136">Добавить код для процедуры `Get` или `Set` свойства, например для проверки входящих значений в процедуре `Set`.</span><span class="sxs-lookup"><span data-stu-id="50310-136">Add code to the `Get` or `Set` procedure of a property, such as code to validate incoming values in the `Set` procedure.</span></span> <span data-ttu-id="50310-137">Например, вам требуется убедиться, что строка, представляющая номер телефона, содержит необходимое количество цифр перед заданием значения свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-137">For example, you might want to verify that a string that represents a telephone number contains the required number of numerals before setting the property value.</span></span>  
  
- <span data-ttu-id="50310-138">Указать другой уровень доступа для процедуры `Get` и `Set`.</span><span class="sxs-lookup"><span data-stu-id="50310-138">Specify different accessibility for the `Get` and `Set` procedure.</span></span> <span data-ttu-id="50310-139">Например, вам может потребоваться сделать процедуру `Set``Private`, а процедуру `Get` — `Public`.</span><span class="sxs-lookup"><span data-stu-id="50310-139">For example, you might want to make the `Set` procedure `Private` and the `Get` procedure `Public`.</span></span>  
  
- <span data-ttu-id="50310-140">Создать свойства типа `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="50310-140">Create properties that are `WriteOnly`.</span></span>  
  
- <span data-ttu-id="50310-141">Использовать параметризованные свойства (включая `Default`).</span><span class="sxs-lookup"><span data-stu-id="50310-141">Use parameterized properties (including `Default` properties).</span></span> <span data-ttu-id="50310-142">Чтобы задать параметр для свойства или указать дополнительные параметры, требуется объявить развернутое свойство процедуры `Set`.</span><span class="sxs-lookup"><span data-stu-id="50310-142">You must declare an expanded property in order to specify a parameter for the property, or to specify additional parameters for the `Set` procedure.</span></span>  
  
- <span data-ttu-id="50310-143">Добавить атрибут в резервное поле или изменить уровень доступа резервного поля.</span><span class="sxs-lookup"><span data-stu-id="50310-143">Place an attribute on the backing field, or change the access level of the backing field.</span></span>  
  
- <span data-ttu-id="50310-144">Добавить XML-комментарии для резервного поля.</span><span class="sxs-lookup"><span data-stu-id="50310-144">Provide XML comments for the backing field.</span></span>  
  
## <a name="expanding-an-auto-implemented-property"></a><span data-ttu-id="50310-145">Расширение автоматически реализуемого свойства</span><span class="sxs-lookup"><span data-stu-id="50310-145">Expanding an Auto-Implemented Property</span></span>  
 <span data-ttu-id="50310-146">Если вам требуется преобразовать автоматически реализуемое свойство в расширенное свойство, которое содержит процедуру `Get` или `Set`, редактор кода Visual Basic может автоматически создать процедуры `Get` и `Set` и оператор `End Property` для свойства.</span><span class="sxs-lookup"><span data-stu-id="50310-146">If you have to convert an auto-implemented property to an expanded property that contains a `Get` or `Set` procedure, the Visual Basic Code Editor can automatically generate the `Get` and `Set` procedures and `End Property` statement for the property.</span></span> <span data-ttu-id="50310-147">Код создается при помещении курсора на пустую строку после оператора `Property` введите `G` (для `Get`) или `S` (для `Set`) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="50310-147">The code is generated if you put the cursor on a blank line following the `Property` statement, type a `G` (for `Get`) or an `S` (for `Set`) and press ENTER.</span></span> <span data-ttu-id="50310-148">Редактор кода Visual Basic автоматически создает процедуру `Get` или `Set` для свойств только для чтения и только для записи при нажатии клавиши ВВОД после оператора `Property`.</span><span class="sxs-lookup"><span data-stu-id="50310-148">The Visual Basic Code Editor automatically generates the `Get` or `Set` procedure for read-only and write-only properties when you press ENTER at the end of a `Property` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50310-149">См. также</span><span class="sxs-lookup"><span data-stu-id="50310-149">See also</span></span>

- [<span data-ttu-id="50310-150">Инструкции. объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50310-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="50310-151">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="50310-151">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="50310-152">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="50310-152">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="50310-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="50310-153">ReadOnly</span></span>](../../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="50310-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="50310-154">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="50310-155">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="50310-155">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
