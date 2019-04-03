---
title: Сокрытие в Visual Basic
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
ms.openlocfilehash: 9ad992a53618fa2f410e0b0fb23886c30136384f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839396"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="d3567-102">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3567-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="d3567-103">Если два программных элемента имеют одинаковые имена, один из них может скрыть, или *тени*, другой.</span><span class="sxs-lookup"><span data-stu-id="d3567-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="d3567-104">В таком случае затененный элемент недоступен для обращения. Вместо этого когда код использует имя элемента, компилятор Visual Basic разрешает его скрывающий элемент.</span><span class="sxs-lookup"><span data-stu-id="d3567-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="d3567-105">Цель</span><span class="sxs-lookup"><span data-stu-id="d3567-105">Purpose</span></span>  
 <span data-ttu-id="d3567-106">Основная цель затенение является защита определения членов класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="d3567-107">Базовый класс может претерпеть изменения, создается элемент с тем же именем, как один, которые вы уже определили.</span><span class="sxs-lookup"><span data-stu-id="d3567-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="d3567-108">В этом случае `Shadows` применении модификатора ссылается в классе быть член определенный, а не к новому элементу базового класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="d3567-109">Типы затенения</span><span class="sxs-lookup"><span data-stu-id="d3567-109">Types of Shadowing</span></span>  
 <span data-ttu-id="d3567-110">Элемент может затенить другой двумя разными способами.</span><span class="sxs-lookup"><span data-stu-id="d3567-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="d3567-111">Скрывающий элемент может быть объявлен внутри входит в область, содержащую скрытый элемент, в котором выполняется тогда затенение *через область*.</span><span class="sxs-lookup"><span data-stu-id="d3567-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="d3567-112">Или производный класс может переопределить член базового класса, в котором выполняется тогда затенение *через наследование*.</span><span class="sxs-lookup"><span data-stu-id="d3567-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="d3567-113">Затемнения посредством области</span><span class="sxs-lookup"><span data-stu-id="d3567-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="d3567-114">Вполне возможно программных элементов, в модуле, классе или структуре могут иметь тем же именем, но разными областями действия.</span><span class="sxs-lookup"><span data-stu-id="d3567-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="d3567-115">Если код ссылается на имя, они совместно используют два элемента объявляются таким образом, элемент с более узкой областью действия затеняет второй элемент (узкая — область видимости блока).</span><span class="sxs-lookup"><span data-stu-id="d3567-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="d3567-116">Например, модуль может определить `Public` переменную с именем `temp`, и процедура в модуле можно объявить локальную переменную также `temp`.</span><span class="sxs-lookup"><span data-stu-id="d3567-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="d3567-117">Ссылки на `temp` изнутри процедура доступа к локальной переменной, а ссылки на `temp` из процедуры доступа извне `Public` переменной.</span><span class="sxs-lookup"><span data-stu-id="d3567-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="d3567-118">В данном случае переменная процедуры `temp` затеняет переменную модуля `temp`.</span><span class="sxs-lookup"><span data-stu-id="d3567-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="d3567-119">На следующем рисунке показаны две переменные, обе с именем `temp`.</span><span class="sxs-lookup"><span data-stu-id="d3567-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="d3567-120">Локальная переменная `temp` скрывает переменную-член `temp` при доступе из своей собственной процедуры `p`.</span><span class="sxs-lookup"><span data-stu-id="d3567-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="d3567-121">Тем не менее `MyClass` ключевое слово обходит затенение и обращается к переменной-члена.</span><span class="sxs-lookup"><span data-stu-id="d3567-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Рисунок, показывающий затемнения посредством области.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="d3567-123">Пример затемнения посредством области, см. в разделе [как: Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="d3567-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="d3567-124">Затемнения посредством наследования</span><span class="sxs-lookup"><span data-stu-id="d3567-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="d3567-125">Если производный класс переопределяет программный элемент, наследуемый от базового класса, переопределенный элемент затеняет исходным элементом.</span><span class="sxs-lookup"><span data-stu-id="d3567-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="d3567-126">С любой другой тип способен переобъявить любой тип, объявленный элемент или набор перегруженных элементов.</span><span class="sxs-lookup"><span data-stu-id="d3567-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="d3567-127">Например `Integer` переменной способен переобъявить `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="d3567-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="d3567-128">При скрытии процедуры другой можно использовать другой список параметров и другой тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d3567-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="d3567-129">На следующем рисунке показан базовый класс `b` и производный класс `d` , наследуемый от `b`.</span><span class="sxs-lookup"><span data-stu-id="d3567-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="d3567-130">Базовый класс определяет процедуру с именем `proc`, и его скрывает производного класса с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="d3567-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="d3567-131">Первый `Call` оператор обращается к затенение `proc` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d3567-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="d3567-132">Тем не менее `MyBase` ключевое слово обходит затенение и обращается к затененной процедуре в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="d3567-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![График схемы затемнения посредством наследования](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="d3567-134">Пример затемнения посредством наследования, см. в разделе [как: Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="d3567-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="d3567-135">Затенение и уровень доступа</span><span class="sxs-lookup"><span data-stu-id="d3567-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="d3567-136">Скрывающий элемент не всегда доступен из кода с помощью производного класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="d3567-137">Например, он может быть объявлен `Private`.</span><span class="sxs-lookup"><span data-stu-id="d3567-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="d3567-138">В таком случае Затенение нарушается, и компилятор разрешает все ссылки на один элемент, его длина будет Если был установлен затенения не.</span><span class="sxs-lookup"><span data-stu-id="d3567-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="d3567-139">Этот элемент является элемент, к наименьшем количестве последовательных шагов от переопределяющий класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="d3567-140">Если переопределяемый элемент является процедурой, разрешение является ближайший доступный с тем же именем, список параметров и тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d3567-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="d3567-141">В следующем примере показано иерархии наследования из трех классов.</span><span class="sxs-lookup"><span data-stu-id="d3567-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="d3567-142">Каждый класс определяет `Sub` процедуры `display`, и каждый производный класс затеняет `display` процедуры в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="d3567-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```  
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
  
 <span data-ttu-id="d3567-143">В приведенном выше примере производный класс `secondClass` shadows `display` с `Private` процедуры.</span><span class="sxs-lookup"><span data-stu-id="d3567-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="d3567-144">Когда модуль `callDisplay` вызовы `display` в `secondClass`, вызывающий код находится за пределами `secondClass` и поэтому недоступны для закрытого `display` процедуры.</span><span class="sxs-lookup"><span data-stu-id="d3567-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="d3567-145">Затенение нарушается, и компилятор разрешает ссылку на базовый класс `display` процедуры.</span><span class="sxs-lookup"><span data-stu-id="d3567-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="d3567-146">Тем не менее, дополнительный производный класс `thirdClass` объявляет `display` как `Public`, поэтому код в `callDisplay` доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="d3567-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="d3567-147">Сокрытием и переопределением</span><span class="sxs-lookup"><span data-stu-id="d3567-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="d3567-148">Не следует путать затенение с переопределением.</span><span class="sxs-lookup"><span data-stu-id="d3567-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="d3567-149">Оба используются, когда производный класс наследует от базового класса, и другое замещает один элемент, объявленный с другим.</span><span class="sxs-lookup"><span data-stu-id="d3567-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="d3567-150">Но существуют значительные различия между ними.</span><span class="sxs-lookup"><span data-stu-id="d3567-150">But there are significant differences between the two.</span></span> <span data-ttu-id="d3567-151">Сравнение, см. в разделе [различия между сокрытием и подмена](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="d3567-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="d3567-152">Затенение и перегрузка</span><span class="sxs-lookup"><span data-stu-id="d3567-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="d3567-153">При скрытии же элемент с более чем одним элементом базового класса в производный класс, переопределяющий элементы становятся перегруженные версии этого элемента.</span><span class="sxs-lookup"><span data-stu-id="d3567-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="d3567-154">Дополнительные сведения см. в разделе [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="d3567-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="d3567-155">Доступ к скрытый элемент</span><span class="sxs-lookup"><span data-stu-id="d3567-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="d3567-156">Для доступа к элементу из производного класса, обычно происходит через текущий экземпляр этого класса, путем указания имени элемента с `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d3567-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="d3567-157">Если производный класс скрывает элемент базового класса, можно получить доступ к элементу базового класса путем определения ее с `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d3567-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="d3567-158">Пример доступа к скрытый элемент, см. в разделе [как: Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="d3567-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="d3567-159">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="d3567-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="d3567-160">Как создать переменную объекта можно также влияет на производном классе получает доступ к скрывающий элемент или переопределяемый элемент.</span><span class="sxs-lookup"><span data-stu-id="d3567-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="d3567-161">В следующем примере создается два объекта производного класса, но один объект объявляется как базовый класс, а другой — как производного класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```  
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
  
 <span data-ttu-id="d3567-162">В приведенном выше примере переменная `basObj` объявляется в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="d3567-163">Назначение `dervCls` объекта он реализует расширяющее преобразование и, соответственно, допустимо.</span><span class="sxs-lookup"><span data-stu-id="d3567-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="d3567-164">Тем не менее, базовый класс недоступен скрывающий версии переменной `z` в производном классе, поэтому компилятор разрешает `basObj.z` к исходному значению базового класса.</span><span class="sxs-lookup"><span data-stu-id="d3567-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3567-165">См. также</span><span class="sxs-lookup"><span data-stu-id="d3567-165">See also</span></span>

- [<span data-ttu-id="d3567-166">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="d3567-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="d3567-167">Область, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3567-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="d3567-168">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="d3567-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="d3567-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="d3567-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="d3567-170">Переопределения</span><span class="sxs-lookup"><span data-stu-id="d3567-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="d3567-171">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="d3567-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="d3567-172">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="d3567-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
