---
title: Перегруженные свойства и методы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="c99c2-102">Перегруженные свойства и методы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c99c2-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="c99c2-103">Перегрузка — это создание более чем одной процедуры, конструктора экземпляра или свойства в классе с тем же именем, но различными типами аргументов.</span><span class="sxs-lookup"><span data-stu-id="c99c2-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="c99c2-104">Использование перегрузки</span><span class="sxs-lookup"><span data-stu-id="c99c2-104">Overloading usage</span></span>

 <span data-ttu-id="c99c2-105">Перегрузка особенно полезна при объектной модели определяет, что нужно использовать одинаковые имена процедур, работающих с разными типами данных.</span><span class="sxs-lookup"><span data-stu-id="c99c2-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="c99c2-106">Например, класс, который может отображать несколько различных типов данных может иметь `Display` процедуры, которые выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c99c2-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 <span data-ttu-id="c99c2-107">Без использования перегрузки потребуются для создания уникальных имен для каждой процедуры, даже если они выполняют то же самое, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="c99c2-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 <span data-ttu-id="c99c2-108">Перегрузка облегчает использование свойств или методов, так как она предоставляет на выбор типов данных, которые могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="c99c2-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="c99c2-109">Например, перегруженных `Display` способов, описанных ранее может вызываться с любым из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="c99c2-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 <span data-ttu-id="c99c2-110">Во время выполнения Visual Basic вызывает нужную процедуру, исходя из заданных пользователем параметров типов данных.</span><span class="sxs-lookup"><span data-stu-id="c99c2-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="c99c2-111">Правила перегрузки</span><span class="sxs-lookup"><span data-stu-id="c99c2-111">Overloading rules</span></span>

 <span data-ttu-id="c99c2-112">Создайте перегруженного члена класса путем добавления двух или более свойств или методов с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c99c2-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="c99c2-113">За исключением перегруженных унаследованных членов все перегруженные члены должны иметь разные списки параметров и не может использоваться как отличительный функция следующие элементы при перегрузке свойство или процедура:</span><span class="sxs-lookup"><span data-stu-id="c99c2-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="c99c2-114">Модификаторы, такие как `ByVal` или `ByRef`, применяемые к элементу или параметров вызываемого члена.</span><span class="sxs-lookup"><span data-stu-id="c99c2-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="c99c2-115">Имена параметров</span><span class="sxs-lookup"><span data-stu-id="c99c2-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="c99c2-116">Возвращаемые типы процедур</span><span class="sxs-lookup"><span data-stu-id="c99c2-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="c99c2-117">`Overloads` Ключевое слово не обязательно при перегрузке, но если некоторый перегруженный член использует `Overloads` ключевое слово, то все остальные перегруженные члены с тем же именем необходимо также указать это ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="c99c2-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="c99c2-118">Производные классы могут перегружать унаследованные члены с членами, имеющими одинаковые параметры и типы параметров, этот процесс называется *перекрытие по имени и подписи*.</span><span class="sxs-lookup"><span data-stu-id="c99c2-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="c99c2-119">Если `Overloads` при перекрытие по имени и подписи, реализация производного класса элемента будет использоваться вместо реализации в базовом классе, и все другие перегрузки этого элемента будут доступны для экземпляров используется ключевое слово производный класс.</span><span class="sxs-lookup"><span data-stu-id="c99c2-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="c99c2-120">Если `Overloads` ключевое слово пропущено при перегрузке унаследованного члена членом, имеющим одинаковые параметры и типы параметров, а затем перегрузка называется *перекрытие по имени*.</span><span class="sxs-lookup"><span data-stu-id="c99c2-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="c99c2-121">Перекрытие по имени заменяет унаследованную реализацию элемента и делает все остальные перегрузки недоступными для экземпляров производного класса и его потомков.</span><span class="sxs-lookup"><span data-stu-id="c99c2-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="c99c2-122">`Overloads` И `Shadows` модификаторы не могут использоваться одновременно с одним свойством или методом.</span><span class="sxs-lookup"><span data-stu-id="c99c2-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c99c2-123">Пример</span><span class="sxs-lookup"><span data-stu-id="c99c2-123">Example</span></span>

 <span data-ttu-id="c99c2-124">В следующем примере создается перегруженные методы, поддерживающие `String` или `Decimal` представление суммы в долларах и возвращающие строку, содержащую налог с продаж.</span><span class="sxs-lookup"><span data-stu-id="c99c2-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="c99c2-125">Чтобы использовать этот пример для создания перегруженного метода</span><span class="sxs-lookup"><span data-stu-id="c99c2-125">To use this example to create an overloaded method</span></span>
  
1.  <span data-ttu-id="c99c2-126">Откройте новый проект и добавьте класс с именем `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="c99c2-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="c99c2-127">Добавьте следующий код в класс `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="c99c2-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  <span data-ttu-id="c99c2-128">Добавьте следующую процедуру в форму.</span><span class="sxs-lookup"><span data-stu-id="c99c2-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  <span data-ttu-id="c99c2-129">Добавьте кнопку в форму и вызовите `ShowTax` процедуры из `Button1_Click` события кнопки.</span><span class="sxs-lookup"><span data-stu-id="c99c2-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="c99c2-130">Запустите проект и нажмите кнопку на форме, чтобы проверить перегруженных `ShowTax` процедуры.</span><span class="sxs-lookup"><span data-stu-id="c99c2-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="c99c2-131">Во время выполнения компилятор выбирает подходящую перегруженную функцию, который соответствует параметрам, используемым.</span><span class="sxs-lookup"><span data-stu-id="c99c2-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="c99c2-132">При нажатии кнопки, перегруженный метод сначала вызывается с `Price` параметр, который является строкой и сообщение «цена является строкой.</span><span class="sxs-lookup"><span data-stu-id="c99c2-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="c99c2-133">Налог — $5,12" отображается.</span><span class="sxs-lookup"><span data-stu-id="c99c2-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="c99c2-134">`TaxAmount` вызывается с `Decimal` значений во второй раз и сообщением, «цена — десятичное число.</span><span class="sxs-lookup"><span data-stu-id="c99c2-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="c99c2-135">Налог — $5,12" отображается.</span><span class="sxs-lookup"><span data-stu-id="c99c2-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99c2-136">См. также</span><span class="sxs-lookup"><span data-stu-id="c99c2-136">See also</span></span>

 [<span data-ttu-id="c99c2-137">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="c99c2-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="c99c2-138">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c99c2-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="c99c2-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="c99c2-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="c99c2-140">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="c99c2-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="c99c2-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="c99c2-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="c99c2-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="c99c2-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="c99c2-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="c99c2-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="c99c2-144">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="c99c2-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="c99c2-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="c99c2-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
