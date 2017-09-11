---
title: "Перегруженные свойства и методы (Visual Basic) | Документы Microsoft"
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
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
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
ms.openlocfilehash: 0b0040f78fd8e091027e32efae3a0f26c2a08622
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="72921-102">Перегруженные свойства и методы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72921-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="72921-103">Перегрузка — это создание более чем одной процедуры, конструктора экземпляра или свойства класса с одинаковыми именами, но различными типами аргументов.</span><span class="sxs-lookup"><span data-stu-id="72921-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="72921-104">Использование перегрузки</span><span class="sxs-lookup"><span data-stu-id="72921-104">Overloading Usage</span></span>  
 <span data-ttu-id="72921-105">Перегрузка особенно полезна при объектной модели определяет, что нужно использовать одинаковые имена процедур, работающих с разными типами данных.</span><span class="sxs-lookup"><span data-stu-id="72921-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="72921-106">Например, класс, который может отображать несколько разных типов данных может иметь `Display` процедуры, которые выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72921-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 <span data-ttu-id="72921-107">[!code-vb[VbVbalrOOP&#64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="72921-107">[!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="72921-108">Без использования перегрузки потребуются для создания уникальных имен для каждой процедуры, даже если они выполняют то же самое, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="72921-108">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 <span data-ttu-id="72921-109">[!code-vb[VbVbalrOOP&#65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="72921-109">[!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="72921-110">Перегрузка облегчает использование свойств или методов, поскольку позволяет выбирать типы данных, которые могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="72921-110">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="72921-111">Например, перегруженных `Display` способов, описанных ранее может вызываться с любым из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="72921-111">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 <span data-ttu-id="72921-112">[!code-vb[VbVbalrOOP&#66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="72921-112">[!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="72921-113">Во время выполнения [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызовы процедуры на основе типов данных параметров можно указать.</span><span class="sxs-lookup"><span data-stu-id="72921-113">At run time, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="72921-114">Правила перегрузки</span><span class="sxs-lookup"><span data-stu-id="72921-114">Overloading Rules</span></span>  
 <span data-ttu-id="72921-115">Создание перегруженного члена класса путем добавления двух или более свойств или методов с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="72921-115">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="72921-116">За исключением перегруженных унаследованных членов все перегруженные члены должны иметь разные списки параметров и не может использоваться как отличительный функция следующие элементы при перегрузке свойство или процедура:</span><span class="sxs-lookup"><span data-stu-id="72921-116">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="72921-117">Модификаторы, такие как `ByVal` или `ByRef`, которые применимы к элементу, или параметрам элемента.</span><span class="sxs-lookup"><span data-stu-id="72921-117">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="72921-118">Имена параметров</span><span class="sxs-lookup"><span data-stu-id="72921-118">Names of parameters</span></span>  
  
-   <span data-ttu-id="72921-119">Возвращаемые типы процедур</span><span class="sxs-lookup"><span data-stu-id="72921-119">Return types of procedures</span></span>  
  
 <span data-ttu-id="72921-120">`Overloads` Ключевое слово не обязательно при перегрузке, но если некоторый перегруженный элемент использует `Overloads` ключевое слово, то все остальные перегруженные члены с тем же именем необходимо также указать это ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="72921-120">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="72921-121">Производные классы могут перегружать унаследованные члены с членами, имеющими идентичные параметры и типы параметров, этот процесс называется *перекрытие по имени и подписи*.</span><span class="sxs-lookup"><span data-stu-id="72921-121">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="72921-122">Если `Overloads` при перекрытие по имени и подписи, реализация производного класса элемента будет использоваться вместо реализации в базовом классе, и все другие перегрузки этого элемента будут доступны для экземпляров производного класса используется ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="72921-122">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="72921-123">Если `Overloads` ключевое слово пропущено при перегрузке унаследованного элемента элементом, имеющим одинаковые параметры и типы параметров, а затем перегрузка называется *перекрытие по имени*.</span><span class="sxs-lookup"><span data-stu-id="72921-123">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="72921-124">Перекрытие по имени заменяет унаследованную реализацию элемента и делает все остальные перегрузки недоступными для экземпляров производного класса и его потомков.</span><span class="sxs-lookup"><span data-stu-id="72921-124">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="72921-125">`Overloads` И `Shadows` модификаторы не могут использоваться одновременно с одним свойством или методом.</span><span class="sxs-lookup"><span data-stu-id="72921-125">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="72921-126">Пример</span><span class="sxs-lookup"><span data-stu-id="72921-126">Example</span></span>  
 <span data-ttu-id="72921-127">В следующем примере создается перегруженные методы, поддерживающие `String` или `Decimal` представление суммы в долларах и возвращающие строку, содержащую налог с продаж.</span><span class="sxs-lookup"><span data-stu-id="72921-127">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="72921-128">Чтобы использовать этот пример для создания перегруженного метода</span><span class="sxs-lookup"><span data-stu-id="72921-128">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="72921-129">Откройте новый проект и добавьте класс с именем `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="72921-129">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="72921-130">Добавьте следующий код в класс `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="72921-130">Add the following code to the `TaxClass` class.</span></span>  
  
     <span data-ttu-id="72921-131">[!code-vb[VbVbalrOOP&#67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="72921-131">[!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span></span>  
  
3.  <span data-ttu-id="72921-132">Добавьте следующую процедуру в форму.</span><span class="sxs-lookup"><span data-stu-id="72921-132">Add the following procedure to your form.</span></span>  
  
     <span data-ttu-id="72921-133">[!code-vb[VbVbalrOOP&#68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="72921-133">[!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span></span>  
  
4.  <span data-ttu-id="72921-134">Добавьте кнопку в форму и вызовите `ShowTax` процедуру `Button1_Click` событие кнопки.</span><span class="sxs-lookup"><span data-stu-id="72921-134">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="72921-135">Запустите проект и нажмите кнопку на форме, чтобы проверить перегруженную `ShowTax` процедуры.</span><span class="sxs-lookup"><span data-stu-id="72921-135">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="72921-136">Во время выполнения компилятор выбирает подходящую перегруженную функцию, соответствующую параметрам, используемым.</span><span class="sxs-lookup"><span data-stu-id="72921-136">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="72921-137">При нажатии кнопки, перегруженный метод сначала вызывается с `Price` параметр, который является строкой и сообщение, «Price is a String.</span><span class="sxs-lookup"><span data-stu-id="72921-137">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="72921-138">Налог — $5,12" отображается.</span><span class="sxs-lookup"><span data-stu-id="72921-138">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="72921-139">`TaxAmount`вызывается с `Decimal` значением во второй раз и сообщение, «Price is Decimal.</span><span class="sxs-lookup"><span data-stu-id="72921-139">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="72921-140">Налог — $5,12" отображается.</span><span class="sxs-lookup"><span data-stu-id="72921-140">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72921-141">См. также</span><span class="sxs-lookup"><span data-stu-id="72921-141">See Also</span></span>  
 <span data-ttu-id="72921-142">[Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="72921-142">[Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="72921-143"> [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span><span class="sxs-lookup"><span data-stu-id="72921-143"> [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span></span>  
<span data-ttu-id="72921-144"> [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="72921-144"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="72921-145"> [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span><span class="sxs-lookup"><span data-stu-id="72921-145"> [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span></span>  
<span data-ttu-id="72921-146"> [Тени](../../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="72921-146"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="72921-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span><span class="sxs-lookup"><span data-stu-id="72921-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span></span>  
<span data-ttu-id="72921-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span><span class="sxs-lookup"><span data-stu-id="72921-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span></span>  
<span data-ttu-id="72921-149"> [Перегруженные методы](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="72921-149"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="72921-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span><span class="sxs-lookup"><span data-stu-id="72921-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span></span>
