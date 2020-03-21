---
title: Удаленное управление
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266889"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="1c08e-102">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c08e-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="1c08e-103">Когда два элемента программирования имеют одно и то же имя, один из них может скрыть, или *тень*, другой.</span><span class="sxs-lookup"><span data-stu-id="1c08e-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="1c08e-104">В такой ситуации затененный элемент недоступен для справки; вместо этого, когда код использует имя элемента, компилятор Visual Basic разрешает его элементу оттенения.</span><span class="sxs-lookup"><span data-stu-id="1c08e-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="1c08e-105">Назначение</span><span class="sxs-lookup"><span data-stu-id="1c08e-105">Purpose</span></span>  
 <span data-ttu-id="1c08e-106">Основная цель слежки — защитить определение членов класса.</span><span class="sxs-lookup"><span data-stu-id="1c08e-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="1c08e-107">Базовый класс может подвергнуться изменению, которое создает элемент с тем же именем, что и тот, который вы уже определили.</span><span class="sxs-lookup"><span data-stu-id="1c08e-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="1c08e-108">В этом случае `Shadows` модификатор заставляет ссылки через ваш класс, чтобы быть решенным к определенному элементу, а не к новому элементу базового класса.</span><span class="sxs-lookup"><span data-stu-id="1c08e-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="1c08e-109">Типы теней</span><span class="sxs-lookup"><span data-stu-id="1c08e-109">Types of Shadowing</span></span>  
 <span data-ttu-id="1c08e-110">Элемент может затмевать другой элемент двумя различными способами.</span><span class="sxs-lookup"><span data-stu-id="1c08e-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="1c08e-111">Элемент тени может быть объявлен внутри субрегиона региона, содержащего затененный элемент, и в этом случае затенение осуществляется *через область.*</span><span class="sxs-lookup"><span data-stu-id="1c08e-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="1c08e-112">Или производное класс может переопределить члена базового класса, и в этом случае слежка осуществляется *через наследство.*</span><span class="sxs-lookup"><span data-stu-id="1c08e-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="1c08e-113">Тень через область</span><span class="sxs-lookup"><span data-stu-id="1c08e-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="1c08e-114">Элементы программирования в одном модуле, классе или структуре могут иметь одно и то же имя, но разные области.</span><span class="sxs-lookup"><span data-stu-id="1c08e-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="1c08e-115">Когда два элемента объявляются таким образом и код относится к имени, которое они разделяют, элемент с более узким объемом тени другого элемента (область блока является самой узкой).</span><span class="sxs-lookup"><span data-stu-id="1c08e-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="1c08e-116">Например, модуль может `Public` определить `temp`переменную, названную, а процедура в `temp`модуле может объявить местную переменную, также названную.</span><span class="sxs-lookup"><span data-stu-id="1c08e-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="1c08e-117">Ссылки `temp` на из нутри процедуры имеют доступ `temp` к локальной переменной, в то время как ссылки на из-за пределов процедуры имеют доступ к переменной. `Public`</span><span class="sxs-lookup"><span data-stu-id="1c08e-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="1c08e-118">В этом случае переменная `temp` процедуры `temp`затеняет переменную модуля.</span><span class="sxs-lookup"><span data-stu-id="1c08e-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="1c08e-119">На следующей иллюстрации показаны `temp`две переменные, обе названы .</span><span class="sxs-lookup"><span data-stu-id="1c08e-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="1c08e-120">Локальная `temp` переменная тени `temp` переменной члена при доступе из своей собственной процедуры. `p`</span><span class="sxs-lookup"><span data-stu-id="1c08e-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="1c08e-121">Однако `MyClass` ключевое слово обходит тень и получает доступ к переменной члена.</span><span class="sxs-lookup"><span data-stu-id="1c08e-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Графика, которая показывает, оттеядая через область.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="1c08e-123">Для примера оттепования через область, [см. Как: Скрыть переменную с тем же именем, как ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="1c08e-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="1c08e-124">Тень через наследство</span><span class="sxs-lookup"><span data-stu-id="1c08e-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="1c08e-125">Если полученный класс переопределяет элемент программирования, унаследованный от базового класса, элемент переосмысления затеняет исходный элемент.</span><span class="sxs-lookup"><span data-stu-id="1c08e-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="1c08e-126">Вы можете затенить любой тип заявленного элемента или набор перегруженных элементов любым другим типом.</span><span class="sxs-lookup"><span data-stu-id="1c08e-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="1c08e-127">Например, `Integer` переменная может `Function` затмить процедуру.</span><span class="sxs-lookup"><span data-stu-id="1c08e-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="1c08e-128">Если вы затеняете процедуру другой процедурой, можно использовать другой список параметров и другой тип возврата.</span><span class="sxs-lookup"><span data-stu-id="1c08e-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="1c08e-129">На следующей иллюстрации `b` показан базовый `d` класс и `b`производный класс, который наследует от .</span><span class="sxs-lookup"><span data-stu-id="1c08e-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="1c08e-130">Базовый класс определяет процедуру, названную, `proc`и полученный класс затеняет ее другой процедурой с тем же названием.</span><span class="sxs-lookup"><span data-stu-id="1c08e-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="1c08e-131">Первое `Call` утверждение получает доступ `proc` к теневому выводу в производном классе.</span><span class="sxs-lookup"><span data-stu-id="1c08e-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="1c08e-132">Однако `MyBase` ключевое слово обходит тени и получает доступ к затененных процедурам в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="1c08e-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![График схемы затемнения посредством наследования](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="1c08e-134">Для примера тени через наследство, [см. Как: Скрыть переменную с тем же именем, как ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: Скрыть унаследованные переменные](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="1c08e-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="1c08e-135">Уровень тени и доступа</span><span class="sxs-lookup"><span data-stu-id="1c08e-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="1c08e-136">Элемент оттенения не всегда доступен из кода с использованием произветядного класса.</span><span class="sxs-lookup"><span data-stu-id="1c08e-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="1c08e-137">Например, он может `Private`быть объявлен .</span><span class="sxs-lookup"><span data-stu-id="1c08e-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="1c08e-138">В таком случае, тень побеждена, и компилятор разрешает любую ссылку на тот же элемент, который он имел бы, если бы не было тени.</span><span class="sxs-lookup"><span data-stu-id="1c08e-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="1c08e-139">Этот элемент является доступным элементом наименьшего производним шагов назад от теневого класса.</span><span class="sxs-lookup"><span data-stu-id="1c08e-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="1c08e-140">Если затененный элемент является процедурой, разрешение находится в ближайшей доступной версии с тем же именем, списком параметров и типом возврата.</span><span class="sxs-lookup"><span data-stu-id="1c08e-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="1c08e-141">В следующем примере показана иерархия наследования трех классов.</span><span class="sxs-lookup"><span data-stu-id="1c08e-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="1c08e-142">Каждый класс `Sub` определяет `display`процедуру, и каждый `display` выведенный класс затеняет процедуру в своем базовом классе.</span><span class="sxs-lookup"><span data-stu-id="1c08e-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1c08e-143">В предыдущем примере выведенный `secondClass` класс `display` тени `Private` с процедурой.</span><span class="sxs-lookup"><span data-stu-id="1c08e-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="1c08e-144">При `callDisplay` `display` вызове `secondClass`модуля код `secondClass` вызова находится за `display` пределами и поэтому не может получить доступ к частной процедуре.</span><span class="sxs-lookup"><span data-stu-id="1c08e-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="1c08e-145">Тень побеждена, и компилятор разрешает ссылку `display` на процедуру базового класса.</span><span class="sxs-lookup"><span data-stu-id="1c08e-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="1c08e-146">Тем не менее, `thirdClass` дальнейший `display` `Public`класс объявляется `callDisplay` как, так что код может получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="1c08e-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="1c08e-147">Тень и переопределение</span><span class="sxs-lookup"><span data-stu-id="1c08e-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="1c08e-148">Не путайте затенение с переопределением.</span><span class="sxs-lookup"><span data-stu-id="1c08e-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="1c08e-149">Оба используются, когда полученный класс наследует из базового класса, и оба переопределяют один объявленный элемент с другим.</span><span class="sxs-lookup"><span data-stu-id="1c08e-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="1c08e-150">Но между ними существуют существенные различия.</span><span class="sxs-lookup"><span data-stu-id="1c08e-150">But there are significant differences between the two.</span></span> <span data-ttu-id="1c08e-151">Для сравнения, [см.](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)</span><span class="sxs-lookup"><span data-stu-id="1c08e-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="1c08e-152">Тень и перегрузка</span><span class="sxs-lookup"><span data-stu-id="1c08e-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="1c08e-153">Если вы затеняете один и тот же элемент базового класса с более чем одним элементом в вашем производном классе, элементы оттенения становятся перегруженными версиями этого элемента.</span><span class="sxs-lookup"><span data-stu-id="1c08e-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="1c08e-154">Дополнительные сведения см. в разделе [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="1c08e-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="1c08e-155">Доступ к элементу затенения</span><span class="sxs-lookup"><span data-stu-id="1c08e-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="1c08e-156">При доступе к элементу из производного класса обычно это происходит через текущий экземпляр этого `Me` производного класса, квалифицируя имя элемента с помощью ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="1c08e-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="1c08e-157">Если ваш производный класс затеняет элемент в базовом классе, вы `MyBase` можете получить доступ к элементу базового класса, квалифицируя его с помощью ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="1c08e-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="1c08e-158">Для примера доступа к затененный элемент, [см. Как: Доступ к переменной скрытые производные класса](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="1c08e-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="1c08e-159">Декларация переменной объекта</span><span class="sxs-lookup"><span data-stu-id="1c08e-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="1c08e-160">Способ создания переменной объекта может также повлиять на то, получает сярвый класс к элементу теней или элементу затенения.</span><span class="sxs-lookup"><span data-stu-id="1c08e-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="1c08e-161">Следующий пример создает два объекта из производного класса, но один объект объявляется базовым классом, а другой – производным классом.</span><span class="sxs-lookup"><span data-stu-id="1c08e-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1c08e-162">В предыдущем примере `basObj` переменная объявляется базовым классом.</span><span class="sxs-lookup"><span data-stu-id="1c08e-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="1c08e-163">Назначение `dervCls` объекта ему представляет собой расширение преобразования и поэтому является действительным.</span><span class="sxs-lookup"><span data-stu-id="1c08e-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="1c08e-164">Однако базовый класс не может получить `z` доступ к теневой версии переменной `basObj.z` в производной группе, поэтому компилятор решает исходное значение базового класса.</span><span class="sxs-lookup"><span data-stu-id="1c08e-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c08e-165">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c08e-165">See also</span></span>

- [<span data-ttu-id="1c08e-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="1c08e-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="1c08e-167">Область видимости в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c08e-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="1c08e-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="1c08e-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="1c08e-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="1c08e-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="1c08e-170">Переопределения</span><span class="sxs-lookup"><span data-stu-id="1c08e-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="1c08e-171">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="1c08e-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="1c08e-172">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="1c08e-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
