---
title: Объявление переменных объектов
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351814"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="4b07f-102">Объявление переменных объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b07f-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="4b07f-103">Для объявления объектной переменной используется стандартный оператор объявления.</span><span class="sxs-lookup"><span data-stu-id="4b07f-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="4b07f-104">Для типа данных указывается либо `Object` (то есть [тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)), либо более конкретный класс, из которого будет создан объект.</span><span class="sxs-lookup"><span data-stu-id="4b07f-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="4b07f-105">Объявление переменной как `Object` аналогично объявлению ее как <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b07f-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4b07f-106">При объявлении переменной с конкретным классом объектов он может получить доступ ко всем методам и свойствам, предоставляемым этим классом, и классами, от которых он наследуется.</span><span class="sxs-lookup"><span data-stu-id="4b07f-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="4b07f-107">Если переменная объявляется с помощью <xref:System.Object>, она может обращаться только к членам класса <xref:System.Object>, если только вы не включите `Option Strict Off`, чтобы разрешить позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="4b07f-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="4b07f-108">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="4b07f-108">Declaration Syntax</span></span>  
 <span data-ttu-id="4b07f-109">Для объявления объектной переменной используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4b07f-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="4b07f-110">В объявлении также можно указать [открытые](../../../../visual-basic/language-reference/modifiers/public.md), [защищенные](../../../../visual-basic/language-reference/modifiers/protected.md), [дружественные](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)или [static](../../../../visual-basic/language-reference/modifiers/static.md) .</span><span class="sxs-lookup"><span data-stu-id="4b07f-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="4b07f-111">Допустимы следующие примеры объявлений:</span><span class="sxs-lookup"><span data-stu-id="4b07f-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="4b07f-112">Позднее связывание и раннее связывание</span><span class="sxs-lookup"><span data-stu-id="4b07f-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="4b07f-113">Иногда конкретный класс неизвестен, пока не будет запущен код.</span><span class="sxs-lookup"><span data-stu-id="4b07f-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="4b07f-114">В этом случае необходимо объявить объектную переменную с типом данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="4b07f-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="4b07f-115">При этом создается общая ссылка на объект любого типа, а конкретный класс назначается во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b07f-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="4b07f-116">Это называется *поздним связыванием*.</span><span class="sxs-lookup"><span data-stu-id="4b07f-116">This is called *late binding*.</span></span> <span data-ttu-id="4b07f-117">Позднее связывание требует дополнительного времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b07f-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="4b07f-118">Он также ограничивает ваш код методами и свойствами класса, назначенного ему последним.</span><span class="sxs-lookup"><span data-stu-id="4b07f-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="4b07f-119">Это может вызвать ошибки времени выполнения, если код пытается получить доступ к членам другого класса.</span><span class="sxs-lookup"><span data-stu-id="4b07f-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="4b07f-120">Когда вы узнаете конкретный класс во время компиляции, следует объявить переменную объекта для этого класса.</span><span class="sxs-lookup"><span data-stu-id="4b07f-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="4b07f-121">Этот принцип называется *раннее связывание*.</span><span class="sxs-lookup"><span data-stu-id="4b07f-121">This is called *early binding*.</span></span> <span data-ttu-id="4b07f-122">Раннее связывание повышает производительность и гарантирует доступ кода ко всем методам и свойствам конкретного класса.</span><span class="sxs-lookup"><span data-stu-id="4b07f-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="4b07f-123">В приведенных выше примерах объявления, если переменная `objA` использует только объекты класса <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, в его объявлении следует указать `As System.Windows.Forms.Label`.</span><span class="sxs-lookup"><span data-stu-id="4b07f-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="4b07f-124">Преимущества раннего связывания</span><span class="sxs-lookup"><span data-stu-id="4b07f-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="4b07f-125">Объявление объектной переменной в качестве конкретного класса дает несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="4b07f-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="4b07f-126">Автоматическая проверка типов</span><span class="sxs-lookup"><span data-stu-id="4b07f-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="4b07f-127">Гарантированный доступ ко всем членам указанного класса</span><span class="sxs-lookup"><span data-stu-id="4b07f-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="4b07f-128">Поддержка Microsoft IntelliSense в редакторе кода</span><span class="sxs-lookup"><span data-stu-id="4b07f-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="4b07f-129">Улучшенная удобочитаемость кода</span><span class="sxs-lookup"><span data-stu-id="4b07f-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="4b07f-130">Меньше ошибок в коде</span><span class="sxs-lookup"><span data-stu-id="4b07f-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="4b07f-131">Ошибки, перехваченные во время компиляции, а не во время выполнения</span><span class="sxs-lookup"><span data-stu-id="4b07f-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="4b07f-132">Ускорение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="4b07f-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="4b07f-133">Доступ к членам переменных объектов</span><span class="sxs-lookup"><span data-stu-id="4b07f-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="4b07f-134">Когда `Option Strict` включается `On`, переменная объекта может обращаться только к методам и свойствам класса, с которым он объявлен.</span><span class="sxs-lookup"><span data-stu-id="4b07f-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="4b07f-135">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b07f-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="4b07f-136">В этом примере `p` может использовать только члены класса <xref:System.Object> без свойства `Left` .</span><span class="sxs-lookup"><span data-stu-id="4b07f-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="4b07f-137">С другой стороны, `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому он может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms> .</span><span class="sxs-lookup"><span data-stu-id="4b07f-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="4b07f-138">Гибкость объектных переменных</span><span class="sxs-lookup"><span data-stu-id="4b07f-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="4b07f-139">При работе с объектами в иерархии наследования можно выбрать, какой класс использовать для объявления переменных объекта.</span><span class="sxs-lookup"><span data-stu-id="4b07f-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="4b07f-140">При выборе этого варианта необходимо сбалансировать гибкость назначения объектов для доступа к членам класса.</span><span class="sxs-lookup"><span data-stu-id="4b07f-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="4b07f-141">Например, рассмотрим иерархию наследования, которая ведет к классу <xref:System.Windows.Forms.Form?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="4b07f-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="4b07f-142">Предположим, что приложение определяет класс формы с именем `specialForm`, который наследуется от класса <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="4b07f-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="4b07f-143">Можно объявить переменную объекта, которая ссылается на `specialForm`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b07f-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="4b07f-144">Объявление в предыдущем примере ограничивает переменную `nextForm` объектами класса `specialForm`, но также делает все методы и свойства `specialForm` доступными для `nextForm`, а также всех членов всех классов, из которых наследуется `specialForm`.</span><span class="sxs-lookup"><span data-stu-id="4b07f-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="4b07f-145">Можно сделать переменную объекта более общей, объявив ее как тип <xref:System.Windows.Forms.Form>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b07f-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="4b07f-146">Объявление в предыдущем примере позволяет назначить любую форму в приложении для `anyForm`.</span><span class="sxs-lookup"><span data-stu-id="4b07f-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="4b07f-147">Однако несмотря на то, что `anyForm` имеет доступ ко всем членам класса <xref:System.Windows.Forms.Form>, он не может использовать дополнительные методы или свойства, определенные для конкретных форм, таких как `specialForm`.</span><span class="sxs-lookup"><span data-stu-id="4b07f-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="4b07f-148">Все члены базового класса доступны для производных классов, но дополнительные члены производного класса недоступны для базового класса.</span><span class="sxs-lookup"><span data-stu-id="4b07f-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b07f-149">См. также</span><span class="sxs-lookup"><span data-stu-id="4b07f-149">See also</span></span>

- [<span data-ttu-id="4b07f-150">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="4b07f-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="4b07f-151">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="4b07f-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="4b07f-152">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="4b07f-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="4b07f-153">Инструкции. Объявление объектной переменной и назначение ей объекта в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b07f-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="4b07f-154">Практическое руководство. Доступ к членам объекта</span><span class="sxs-lookup"><span data-stu-id="4b07f-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="4b07f-155">Оператор New</span><span class="sxs-lookup"><span data-stu-id="4b07f-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="4b07f-156">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="4b07f-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4b07f-157">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="4b07f-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
