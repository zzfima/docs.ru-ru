---
title: Объявление переменных объектов (Visual Basic)
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
ms.openlocfilehash: 96b1677e301d3e83df400472bfa06e921f991bd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544657"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="90ee9-102">Объявление переменных объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90ee9-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="90ee9-103">Используйте обычный оператор объявления для объявления переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="90ee9-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="90ee9-104">Для типа данных, либо указать `Object` (то есть [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) или более определенный класс, из которого будет создаваться объект.</span><span class="sxs-lookup"><span data-stu-id="90ee9-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="90ee9-105">Объявление переменной как `Object` совпадает со значением его объявление как <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90ee9-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="90ee9-106">При объявлении переменной с помощью конкретного объекта класса, он может получить доступ к все методы и свойства, предоставляемые этого класса и классов, от которых он наследует.</span><span class="sxs-lookup"><span data-stu-id="90ee9-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="90ee9-107">Если вы объявите переменную с <xref:System.Object>, он сможет использовать только члены из <xref:System.Object> класса, если не выключить `Option Strict Off` позволяет позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="90ee9-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="90ee9-108">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="90ee9-108">Declaration Syntax</span></span>  
 <span data-ttu-id="90ee9-109">Используйте следующий синтаксис для объявления переменной объекта:</span><span class="sxs-lookup"><span data-stu-id="90ee9-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="90ee9-110">Можно также указать [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [частного](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), или [статический](../../../../visual-basic/language-reference/modifiers/static.md) в объявлении.</span><span class="sxs-lookup"><span data-stu-id="90ee9-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="90ee9-111">Допустимы следующие варианты объявлений:</span><span class="sxs-lookup"><span data-stu-id="90ee9-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="90ee9-112">Раннее связывание и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="90ee9-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="90ee9-113">Иногда определенный класс неизвестно до выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="90ee9-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="90ee9-114">В этом случае необходимо объявить переменную объекта с `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="90ee9-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="90ee9-115">Это создает общую ссылку на объект любого типа, и определенный класс назначается во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="90ee9-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="90ee9-116">Это называется *позднее связывание*.</span><span class="sxs-lookup"><span data-stu-id="90ee9-116">This is called *late binding*.</span></span> <span data-ttu-id="90ee9-117">Позднее связывание требует дополнительного времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="90ee9-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="90ee9-118">Она также ограничивает кода к методам и свойствам класса, которые недавно были назначены на него.</span><span class="sxs-lookup"><span data-stu-id="90ee9-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="90ee9-119">Это может вызвать ошибки времени выполнения, если код пытается получить доступ к членам другого класса.</span><span class="sxs-lookup"><span data-stu-id="90ee9-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="90ee9-120">Если вы знаете определенного класса во время компиляции, следует объявить переменную объекта этого класса.</span><span class="sxs-lookup"><span data-stu-id="90ee9-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="90ee9-121">Этот принцип называется *раннее связывание*.</span><span class="sxs-lookup"><span data-stu-id="90ee9-121">This is called *early binding*.</span></span> <span data-ttu-id="90ee9-122">Раннее связывание позволяет повысить производительность и гарантирует доступ к методам и свойствам определенного класса.</span><span class="sxs-lookup"><span data-stu-id="90ee9-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="90ee9-123">В предыдущем примере объявлений, если переменная `objA` использует только объекты класса <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, следует указать `As System.Windows.Forms.Label` в его объявлении.</span><span class="sxs-lookup"><span data-stu-id="90ee9-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="90ee9-124">Преимущества раннего связывания</span><span class="sxs-lookup"><span data-stu-id="90ee9-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="90ee9-125">Объявление объектной переменной в определенном классе дает несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="90ee9-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
-   <span data-ttu-id="90ee9-126">Автоматическая проверка типа</span><span class="sxs-lookup"><span data-stu-id="90ee9-126">Automatic type checking</span></span>  
  
-   <span data-ttu-id="90ee9-127">Гарантированный доступ ко всем членам определенного класса</span><span class="sxs-lookup"><span data-stu-id="90ee9-127">Guaranteed access to all members of the specific class</span></span>  
  
-   <span data-ttu-id="90ee9-128">Поддержка Microsoft IntelliSense в редакторе кода</span><span class="sxs-lookup"><span data-stu-id="90ee9-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
-   <span data-ttu-id="90ee9-129">Улучшение читаемости кода</span><span class="sxs-lookup"><span data-stu-id="90ee9-129">Improved readability of your code</span></span>  
  
-   <span data-ttu-id="90ee9-130">Меньшее количество ошибок в коде</span><span class="sxs-lookup"><span data-stu-id="90ee9-130">Fewer errors in your code</span></span>  
  
-   <span data-ttu-id="90ee9-131">Обнаружение ошибок во время компиляции, а не время выполнения</span><span class="sxs-lookup"><span data-stu-id="90ee9-131">Errors caught at compile time rather than run time</span></span>  
  
-   <span data-ttu-id="90ee9-132">Более быстрое выполнение кода</span><span class="sxs-lookup"><span data-stu-id="90ee9-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="90ee9-133">Доступ к членам переменных объекта</span><span class="sxs-lookup"><span data-stu-id="90ee9-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="90ee9-134">Когда `Option Strict` включен `On`, переменная объекта может получить доступ к только методы и свойства класса, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="90ee9-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="90ee9-135">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="90ee9-135">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="90ee9-136">В этом примере `p` может использовать только члены класса <xref:System.Object> без свойства `Left` .</span><span class="sxs-lookup"><span data-stu-id="90ee9-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="90ee9-137">С другой стороны, `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому он может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms> .</span><span class="sxs-lookup"><span data-stu-id="90ee9-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="90ee9-138">Гибкость объектных переменных</span><span class="sxs-lookup"><span data-stu-id="90ee9-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="90ee9-139">При работе с объектами в иерархии наследования, у вас есть выбор класс, который будет использоваться при объявлении переменных объектов.</span><span class="sxs-lookup"><span data-stu-id="90ee9-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="90ee9-140">В этом соблюдать баланс между гибкостью присваивания объекта доступа к членам класса.</span><span class="sxs-lookup"><span data-stu-id="90ee9-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="90ee9-141">Например, рассмотрим иерархию наследования, которая приводит к <xref:System.Windows.Forms.Form?displayProperty=nameWithType> класса:</span><span class="sxs-lookup"><span data-stu-id="90ee9-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="90ee9-142">Предположим, что приложение определяет форму `specialForm`, который наследует от класса <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="90ee9-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="90ee9-143">Можно объявить переменную объекта, специально ссылается на `specialForm`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="90ee9-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="90ee9-144">Объявление в предыдущем примере ограничивает переменной `nextForm` к объектам класса `specialForm`, но оно также делает все методы и свойства `specialForm` для `nextForm`, а также все члены всех классов, от которых `specialForm` наследует.</span><span class="sxs-lookup"><span data-stu-id="90ee9-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="90ee9-145">Внесения более общими объектную переменную, объявив ее в типа <xref:System.Windows.Forms.Form>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="90ee9-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="90ee9-146">Объявление в предыдущем примере позволяет назначить любую форму в приложении `anyForm`.</span><span class="sxs-lookup"><span data-stu-id="90ee9-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="90ee9-147">Тем не менее несмотря на то что `anyForm` можно использовать все члены класса <xref:System.Windows.Forms.Form>, она не может использовать любой из дополнительных методов и свойств, определенных для конкретных форм, таких как `specialForm`.</span><span class="sxs-lookup"><span data-stu-id="90ee9-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="90ee9-148">Все члены базового класса доступны для производных классов, но дополнительные члены производного класса, недоступны для базового класса.</span><span class="sxs-lookup"><span data-stu-id="90ee9-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90ee9-149">См. также</span><span class="sxs-lookup"><span data-stu-id="90ee9-149">See also</span></span>
- [<span data-ttu-id="90ee9-150">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="90ee9-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="90ee9-151">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="90ee9-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="90ee9-152">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="90ee9-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="90ee9-153">Практическое руководство. Объявление объектной переменной и присвоение объекта в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90ee9-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="90ee9-154">Практическое руководство. Доступ к членам объекта</span><span class="sxs-lookup"><span data-stu-id="90ee9-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="90ee9-155">Оператор New</span><span class="sxs-lookup"><span data-stu-id="90ee9-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="90ee9-156">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="90ee9-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="90ee9-157">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="90ee9-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
