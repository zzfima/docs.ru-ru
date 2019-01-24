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
ms.openlocfilehash: 6ac973493b67fa15ca935f61bbb8e5c07bda1e0f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580867"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="ae1b6-102">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae1b6-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="ae1b6-103">Если два программных элемента имеют одинаковые имена, один из них может скрыть, или *тени*, другой.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="ae1b6-104">В таком случае затененный элемент недоступен для обращения. Вместо этого когда код использует имя элемента, компилятор Visual Basic разрешает его скрывающий элемент.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="ae1b6-105">Цель</span><span class="sxs-lookup"><span data-stu-id="ae1b6-105">Purpose</span></span>  
 <span data-ttu-id="ae1b6-106">Основная цель затенение является защита определения членов класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="ae1b6-107">Базовый класс может претерпеть изменения, создается элемент с тем же именем, как один, которые вы уже определили.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="ae1b6-108">В этом случае `Shadows` применении модификатора ссылается в классе быть член определенный, а не к новому элементу базового класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="ae1b6-109">Типы затенения</span><span class="sxs-lookup"><span data-stu-id="ae1b6-109">Types of Shadowing</span></span>  
 <span data-ttu-id="ae1b6-110">Элемент может затенить другой двумя разными способами.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="ae1b6-111">Скрывающий элемент может быть объявлен внутри входит в область, содержащую скрытый элемент, в котором выполняется тогда затенение *через область*.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="ae1b6-112">Или производный класс может переопределить член базового класса, в котором выполняется тогда затенение *через наследование*.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="ae1b6-113">Затемнения посредством области</span><span class="sxs-lookup"><span data-stu-id="ae1b6-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="ae1b6-114">Вполне возможно программных элементов, в модуле, классе или структуре могут иметь тем же именем, но разными областями действия.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="ae1b6-115">Если код ссылается на имя, они совместно используют два элемента объявляются таким образом, элемент с более узкой областью действия затеняет второй элемент (узкая — область видимости блока).</span><span class="sxs-lookup"><span data-stu-id="ae1b6-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="ae1b6-116">Например, модуль может определить `Public` переменную с именем `temp`, и процедура в модуле можно объявить локальную переменную также `temp`.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="ae1b6-117">Ссылки на `temp` изнутри процедура доступа к локальной переменной, а ссылки на `temp` из процедуры доступа извне `Public` переменной.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="ae1b6-118">В данном случае переменная процедуры `temp` затеняет переменную модуля `temp`.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="ae1b6-119">На следующем рисунке показаны две переменные, обе с именем `temp`.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="ae1b6-120">Локальная переменная `temp` скрывает переменную-член `temp` при доступе из своей собственной процедуры `p`.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="ae1b6-121">Тем не менее `MyClass` ключевое слово обходит затенение и обращается к переменной-члена.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 <span data-ttu-id="ae1b6-122">![График схемы затемнения посредством области](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span><span class="sxs-lookup"><span data-stu-id="ae1b6-122">![Graphic diagram of shadowing through scope](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span></span>  
<span data-ttu-id="ae1b6-123">Затемнения посредством области</span><span class="sxs-lookup"><span data-stu-id="ae1b6-123">Shadowing through scope</span></span>  
  
 <span data-ttu-id="ae1b6-124">Пример затемнения посредством области, см. в разделе [как: Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="ae1b6-124">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="ae1b6-125">Затемнения посредством наследования</span><span class="sxs-lookup"><span data-stu-id="ae1b6-125">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="ae1b6-126">Если производный класс переопределяет программный элемент, наследуемый от базового класса, переопределенный элемент затеняет исходным элементом.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-126">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="ae1b6-127">С любой другой тип способен переобъявить любой тип, объявленный элемент или набор перегруженных элементов.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-127">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="ae1b6-128">Например `Integer` переменной способен переобъявить `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-128">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="ae1b6-129">При скрытии процедуры другой можно использовать другой список параметров и другой тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-129">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="ae1b6-130">На следующем рисунке показан базовый класс `b` и производный класс `d` , наследуемый от `b`.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-130">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="ae1b6-131">Базовый класс определяет процедуру с именем `proc`, и его скрывает производного класса с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-131">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="ae1b6-132">Первый `Call` оператор обращается к затенение `proc` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-132">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="ae1b6-133">Тем не менее `MyBase` ключевое слово обходит затенение и обращается к затененной процедуре в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-133">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 <span data-ttu-id="ae1b6-134">![График схемы затемнения посредством наследования](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span><span class="sxs-lookup"><span data-stu-id="ae1b6-134">![Graphic diagram of shadowing through inheritance](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span></span>  
<span data-ttu-id="ae1b6-135">Затемнения посредством наследования</span><span class="sxs-lookup"><span data-stu-id="ae1b6-135">Shadowing through inheritance</span></span>  
  
 <span data-ttu-id="ae1b6-136">Пример затемнения посредством наследования, см. в разделе [как: Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="ae1b6-136">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="ae1b6-137">Затенение и уровень доступа</span><span class="sxs-lookup"><span data-stu-id="ae1b6-137">Shadowing and Access Level</span></span>  
 <span data-ttu-id="ae1b6-138">Скрывающий элемент не всегда доступен из кода с помощью производного класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-138">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="ae1b6-139">Например, он может быть объявлен `Private`.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-139">For example, it might be declared `Private`.</span></span> <span data-ttu-id="ae1b6-140">В таком случае Затенение нарушается, и компилятор разрешает все ссылки на один элемент, его длина будет Если был установлен затенения не.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-140">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="ae1b6-141">Этот элемент является элемент, к наименьшем количестве последовательных шагов от переопределяющий класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-141">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="ae1b6-142">Если переопределяемый элемент является процедурой, разрешение является ближайший доступный с тем же именем, список параметров и тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-142">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="ae1b6-143">В следующем примере показано иерархии наследования из трех классов.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-143">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="ae1b6-144">Каждый класс определяет `Sub` процедуры `display`, и каждый производный класс затеняет `display` процедуры в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-144">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="ae1b6-145">В приведенном выше примере производный класс `secondClass` shadows `display` с `Private` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-145">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="ae1b6-146">Когда модуль `callDisplay` вызовы `display` в `secondClass`, вызывающий код находится за пределами `secondClass` и поэтому недоступны для закрытого `display` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-146">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="ae1b6-147">Затенение нарушается, и компилятор разрешает ссылку на базовый класс `display` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-147">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="ae1b6-148">Тем не менее, дополнительный производный класс `thirdClass` объявляет `display` как `Public`, поэтому код в `callDisplay` доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-148">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="ae1b6-149">Сокрытием и переопределением</span><span class="sxs-lookup"><span data-stu-id="ae1b6-149">Shadowing and Overriding</span></span>  
 <span data-ttu-id="ae1b6-150">Не следует путать затенение с переопределением.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-150">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="ae1b6-151">Оба используются, когда производный класс наследует от базового класса, и другое замещает один элемент, объявленный с другим.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-151">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="ae1b6-152">Но существуют значительные различия между ними.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-152">But there are significant differences between the two.</span></span> <span data-ttu-id="ae1b6-153">Сравнение, см. в разделе [различия между сокрытием и подмена](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="ae1b6-153">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="ae1b6-154">Затенение и перегрузка</span><span class="sxs-lookup"><span data-stu-id="ae1b6-154">Shadowing and Overloading</span></span>  
 <span data-ttu-id="ae1b6-155">При скрытии же элемент с более чем одним элементом базового класса в производный класс, переопределяющий элементы становятся перегруженные версии этого элемента.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-155">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="ae1b6-156">Дополнительные сведения см. в разделе [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="ae1b6-156">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="ae1b6-157">Доступ к скрытый элемент</span><span class="sxs-lookup"><span data-stu-id="ae1b6-157">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="ae1b6-158">Для доступа к элементу из производного класса, обычно происходит через текущий экземпляр этого класса, путем указания имени элемента с `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-158">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="ae1b6-159">Если производный класс скрывает элемент базового класса, можно получить доступ к элементу базового класса путем определения ее с `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-159">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="ae1b6-160">Пример доступа к скрытый элемент, см. в разделе [как: Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="ae1b6-160">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="ae1b6-161">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="ae1b6-161">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="ae1b6-162">Как создать переменную объекта можно также влияет на производном классе получает доступ к скрывающий элемент или переопределяемый элемент.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-162">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="ae1b6-163">В следующем примере создается два объекта производного класса, но один объект объявляется как базовый класс, а другой — как производного класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-163">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="ae1b6-164">В приведенном выше примере переменная `basObj` объявляется в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-164">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="ae1b6-165">Назначение `dervCls` объекта он реализует расширяющее преобразование и, соответственно, допустимо.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-165">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="ae1b6-166">Тем не менее, базовый класс недоступен скрывающий версии переменной `z` в производном классе, поэтому компилятор разрешает `basObj.z` к исходному значению базового класса.</span><span class="sxs-lookup"><span data-stu-id="ae1b6-166">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1b6-167">См. также</span><span class="sxs-lookup"><span data-stu-id="ae1b6-167">See also</span></span>
- [<span data-ttu-id="ae1b6-168">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="ae1b6-168">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="ae1b6-169">Область, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae1b6-169">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="ae1b6-170">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="ae1b6-170">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="ae1b6-171">Shadows</span><span class="sxs-lookup"><span data-stu-id="ae1b6-171">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ae1b6-172">Переопределения</span><span class="sxs-lookup"><span data-stu-id="ae1b6-172">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ae1b6-173">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="ae1b6-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="ae1b6-174">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="ae1b6-174">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
