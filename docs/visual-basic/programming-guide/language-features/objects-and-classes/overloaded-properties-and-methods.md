---
title: Перегруженные свойства и методы (Visual Basic)
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
ms.openlocfilehash: 8d7341370d9770d2e57f786ac7c68277e66a9bbd
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677400"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="9a995-102">Перегруженные свойства и методы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a995-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="9a995-103">Перегрузка — это создание более чем одной процедуры, конструктор экземпляра или свойства в классе с тем же именем, но разные типы аргументов.</span><span class="sxs-lookup"><span data-stu-id="9a995-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="9a995-104">Использование перегрузки</span><span class="sxs-lookup"><span data-stu-id="9a995-104">Overloading usage</span></span>

<span data-ttu-id="9a995-105">Перегрузка особенно полезна при объектную модель определяет, что нужно использовать одинаковые имена процедур, работающих на различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="9a995-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="9a995-106">Например, класс, который может отображать несколько различных типов данных может иметь `Display` процедуры, которые выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a995-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="9a995-107">Без перегрузки, вам потребовалось бы создать уникальные имена для каждой процедуры, несмотря на то, что они делают одно и то же самое, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="9a995-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="9a995-108">Перегрузка облегчает использование свойств или методов, так как она позволяет выбрать из типов данных, которые могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="9a995-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="9a995-109">Например, перегруженных `Display` способов, описанных ранее может вызываться с любым из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="9a995-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="9a995-110">Во время выполнения Visual Basic вызывает правильную процедуру, на основе типов данных параметров, указанную вами.</span><span class="sxs-lookup"><span data-stu-id="9a995-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="9a995-111">Правила перегрузки</span><span class="sxs-lookup"><span data-stu-id="9a995-111">Overloading rules</span></span>

 <span data-ttu-id="9a995-112">Создание перегруженного члена класса путем добавления двух или более свойств или методов с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="9a995-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="9a995-113">За исключением перегруженных унаследованных членов все перегруженные члены должны иметь разные списки параметров и не может использоваться как средство отличительный перечисленные ниже при перегрузке свойство или процедура:</span><span class="sxs-lookup"><span data-stu-id="9a995-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="9a995-114">Модификаторы, такие как `ByVal` или `ByRef`, которые применяются к элементу, или параметрам элемента.</span><span class="sxs-lookup"><span data-stu-id="9a995-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="9a995-115">Имена параметров</span><span class="sxs-lookup"><span data-stu-id="9a995-115">Names of parameters</span></span>

- <span data-ttu-id="9a995-116">Типы возвращаемого значения процедуры</span><span class="sxs-lookup"><span data-stu-id="9a995-116">Return types of procedures</span></span>

<span data-ttu-id="9a995-117">`Overloads` Ключевое слово является необязательным при перегрузке, но если некоторый перегруженный элемент использует `Overloads` ключевое слово, то все остальные перегруженные члены с тем же именем необходимо также указать это ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="9a995-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="9a995-118">Производные классы могут перегружать унаследованные члены с членами, имеющими одинаковые параметры и типы параметров, этот процесс называется *перекрытие по имени и подписи*.</span><span class="sxs-lookup"><span data-stu-id="9a995-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="9a995-119">Если `Overloads` при перекрытие по имени и подписи, реализацию члена производного класса будет использоваться вместо реализации в базовом классе, и все другие перегрузки этого элемента будут доступны для экземпляров, используется ключевое слово производный класс.</span><span class="sxs-lookup"><span data-stu-id="9a995-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="9a995-120">Если `Overloads` слово опущено, при перегрузке унаследованный член с членом, имеющим одинаковые параметры и типы параметров, а затем перегрузка называется *перекрытие по имени*.</span><span class="sxs-lookup"><span data-stu-id="9a995-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="9a995-121">Перекрытие по имени заменяет унаследованной реализации члена, и делает все остальные перегрузки недоступными для экземпляров производного класса и его потомков.</span><span class="sxs-lookup"><span data-stu-id="9a995-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="9a995-122">`Overloads` И `Shadows` модификаторы не могут использоваться одновременно с одним свойством или методом.</span><span class="sxs-lookup"><span data-stu-id="9a995-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="9a995-123">Пример</span><span class="sxs-lookup"><span data-stu-id="9a995-123">Example</span></span>

<span data-ttu-id="9a995-124">В следующем примере создается перегруженные методы, поддерживающие `String` или `Decimal` представление суммы в долларах и возвращающие строку, содержащую налог с продаж.</span><span class="sxs-lookup"><span data-stu-id="9a995-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="9a995-125">Чтобы использовать этот пример для создания перегруженного метода</span><span class="sxs-lookup"><span data-stu-id="9a995-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="9a995-126">Откройте новый проект и добавьте класс с именем `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="9a995-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="9a995-127">Добавьте следующий код в класс `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="9a995-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="9a995-128">Добавьте следующую процедуру в форму.</span><span class="sxs-lookup"><span data-stu-id="9a995-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="9a995-129">Добавьте кнопку в форму и вызовите `ShowTax` процедуры из `Button1_Click` события кнопки.</span><span class="sxs-lookup"><span data-stu-id="9a995-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="9a995-130">Запустите проект и нажмите кнопку на форме, чтобы проверить перегруженных `ShowTax` процедуры.</span><span class="sxs-lookup"><span data-stu-id="9a995-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="9a995-131">Во время выполнения компилятор выбирает соответствующий перегруженной функции, который соответствует параметрам, используемым.</span><span class="sxs-lookup"><span data-stu-id="9a995-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="9a995-132">При нажатии кнопки, перегруженный метод сначала вызывается с `Price` параметр, который является строкой и сообщение, «цена is a String.</span><span class="sxs-lookup"><span data-stu-id="9a995-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="9a995-133">Налог — $5,12" отображается.</span><span class="sxs-lookup"><span data-stu-id="9a995-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="9a995-134">`TaxAmount` вызывается с `Decimal` значение во второй раз и сообщение, «цена — десятичное число.</span><span class="sxs-lookup"><span data-stu-id="9a995-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="9a995-135">Налог — $5,12" отображается.</span><span class="sxs-lookup"><span data-stu-id="9a995-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a995-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9a995-136">See also</span></span>

- [<span data-ttu-id="9a995-137">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="9a995-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="9a995-138">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a995-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="9a995-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="9a995-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9a995-140">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="9a995-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="9a995-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="9a995-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="9a995-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="9a995-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="9a995-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="9a995-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="9a995-144">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="9a995-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="9a995-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="9a995-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
