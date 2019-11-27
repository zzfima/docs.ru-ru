---
title: Перегруженные свойства и методы
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: a5017d371f8a01436020443b2e3466c78fc35d21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346093"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="54184-102">Перегруженные свойства и методы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54184-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="54184-103">Перегрузка — это создание более чем одной процедуры, конструктора экземпляра или свойства в классе с тем же именем, но разными типами аргументов.</span><span class="sxs-lookup"><span data-stu-id="54184-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="54184-104">Перегрузка использования</span><span class="sxs-lookup"><span data-stu-id="54184-104">Overloading usage</span></span>

<span data-ttu-id="54184-105">Перегрузка особенно полезна, когда объектная модель определяет, что для процедур, которые работают с различными типами данных, используются одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="54184-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="54184-106">Например, класс, который может отображать несколько разных типов данных, может иметь `Display` процедуры, которые выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="54184-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="54184-107">Без перегрузки необходимо создать разные имена для каждой процедуры, даже если они выполняют одно и то же действие, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="54184-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="54184-108">Перегрузка упрощает использование свойств или методов, поскольку она предоставляет возможность выбора типов данных, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="54184-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="54184-109">Например, перегруженный метод `Display`, описанный ранее, можно вызвать с помощью любой из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="54184-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="54184-110">Во время выполнения Visual Basic вызывает правильную процедуру на основе типов данных указанных параметров.</span><span class="sxs-lookup"><span data-stu-id="54184-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="54184-111">Перегрузка правил</span><span class="sxs-lookup"><span data-stu-id="54184-111">Overloading rules</span></span>

 <span data-ttu-id="54184-112">Перегруженный член класса создается путем добавления двух или более свойств или методов с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="54184-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="54184-113">За исключением перегруженных производных членов, каждый перегруженный член должен иметь разные списки параметров, и следующие элементы нельзя использовать в качестве отличительной функции при перегрузке свойства или процедуры:</span><span class="sxs-lookup"><span data-stu-id="54184-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="54184-114">Модификаторы, такие как `ByVal` или `ByRef`, которые применяются к элементу или параметрам элемента.</span><span class="sxs-lookup"><span data-stu-id="54184-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="54184-115">Имена параметров</span><span class="sxs-lookup"><span data-stu-id="54184-115">Names of parameters</span></span>

- <span data-ttu-id="54184-116">Типы возвращаемых процедур</span><span class="sxs-lookup"><span data-stu-id="54184-116">Return types of procedures</span></span>

<span data-ttu-id="54184-117">Ключевое слово `Overloads` является необязательным при перегрузке, но если какой-либо перегруженный член использует ключевое слово `Overloads`, то все другие перегруженные члены с тем же именем также должны указывать это ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="54184-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="54184-118">Производные классы могут перегружать унаследованные члены с элементами, которые имеют одинаковые параметры и типы параметров, процесс, называемый *теневым именем и сигнатурой*.</span><span class="sxs-lookup"><span data-stu-id="54184-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="54184-119">Если ключевое слово `Overloads` используется при затенении по имени и сигнатуре, реализация члена в производном классе будет использоваться вместо реализации в базовом классе, а все другие перегрузки для этого члена будут доступны экземплярам производного класса.</span><span class="sxs-lookup"><span data-stu-id="54184-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="54184-120">Если при перегрузке унаследованного элемента с членом, имеющим идентичные параметры и типы параметров, пропущено ключевое слово `Overloads`, перегрузка называется *тенью по имени*.</span><span class="sxs-lookup"><span data-stu-id="54184-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="54184-121">Затенение по имени заменяет унаследованную реализацию члена и делает все другие перегрузки недоступными для экземпляров производного класса и его децедентс.</span><span class="sxs-lookup"><span data-stu-id="54184-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="54184-122">Модификаторы `Overloads` и `Shadows` не могут использоваться одновременно с одним свойством или методом.</span><span class="sxs-lookup"><span data-stu-id="54184-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="54184-123">Пример</span><span class="sxs-lookup"><span data-stu-id="54184-123">Example</span></span>

<span data-ttu-id="54184-124">В следующем примере создаются перегруженные методы, которые принимают либо `String`, либо `Decimal` представление денежной суммы и возвращают строку, содержащую налог на продажу.</span><span class="sxs-lookup"><span data-stu-id="54184-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="54184-125">Использование этого примера для создания перегруженного метода</span><span class="sxs-lookup"><span data-stu-id="54184-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="54184-126">Откройте новый проект и добавьте класс с именем `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="54184-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="54184-127">Добавьте следующий код в класс `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="54184-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="54184-128">Добавьте следующую процедуру в форму.</span><span class="sxs-lookup"><span data-stu-id="54184-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="54184-129">Добавьте в форму кнопку и вызовите процедуру `ShowTax` из события `Button1_Click` кнопки.</span><span class="sxs-lookup"><span data-stu-id="54184-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="54184-130">Запустите проект и нажмите кнопку в форме, чтобы проверить перегруженную `ShowTax` процедуру.</span><span class="sxs-lookup"><span data-stu-id="54184-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="54184-131">Во время выполнения компилятор выбирает подходящую перегруженную функцию, которая соответствует используемым параметрам.</span><span class="sxs-lookup"><span data-stu-id="54184-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="54184-132">При нажатии кнопки перегруженный метод вызывается сначала с параметром `Price`, который является строкой, и сообщением «Price — это строка.</span><span class="sxs-lookup"><span data-stu-id="54184-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="54184-133">Налог — $5,12 ".</span><span class="sxs-lookup"><span data-stu-id="54184-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="54184-134">`TaxAmount` вызывается со значением `Decimal` второй раз и сообщением "Price-Decimal.</span><span class="sxs-lookup"><span data-stu-id="54184-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="54184-135">Налог — $5,12 ".</span><span class="sxs-lookup"><span data-stu-id="54184-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="54184-136">См. также</span><span class="sxs-lookup"><span data-stu-id="54184-136">See also</span></span>

- [<span data-ttu-id="54184-137">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="54184-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="54184-138">Затенение в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54184-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="54184-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="54184-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="54184-140">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="54184-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="54184-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="54184-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="54184-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="54184-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="54184-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="54184-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="54184-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="54184-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="54184-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="54184-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
