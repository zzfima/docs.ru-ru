---
title: "Сокрытие в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbfce3edc122ca875552b2d41ba876fe5cfcfc4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="21f5e-102">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21f5e-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="21f5e-103">Если два программных элемента имеют то же имя, один из них может скрыть, или *тени*, другой.</span><span class="sxs-lookup"><span data-stu-id="21f5e-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="21f5e-104">В таком случае скрытый элемент недоступен для обращения. Вместо этого в том случае, когда ваш код использует имя элемента [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятор разрешает его скрывающий элемент.</span><span class="sxs-lookup"><span data-stu-id="21f5e-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="21f5e-105">Назначение</span><span class="sxs-lookup"><span data-stu-id="21f5e-105">Purpose</span></span>  
 <span data-ttu-id="21f5e-106">Основным предназначением затенения является защита определения членов класса.</span><span class="sxs-lookup"><span data-stu-id="21f5e-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="21f5e-107">Базовый класс может претерпеть изменения, создается элемент с тем же именем, как один, которые уже определены.</span><span class="sxs-lookup"><span data-stu-id="21f5e-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="21f5e-108">В этом случае `Shadows` применении модификатора ссылается в классе член быть определенный, а не новый элемент базового класса.</span><span class="sxs-lookup"><span data-stu-id="21f5e-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="21f5e-109">Типы затенения</span><span class="sxs-lookup"><span data-stu-id="21f5e-109">Types of Shadowing</span></span>  
 <span data-ttu-id="21f5e-110">Элемент можно скрывать другой элемент двумя различными способами.</span><span class="sxs-lookup"><span data-stu-id="21f5e-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="21f5e-111">Переопределяющий элемент может быть объявлен внутри подобласти содержит скрытый элемент, в котором выполняется тогда затенение *посредством области*.</span><span class="sxs-lookup"><span data-stu-id="21f5e-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="21f5e-112">Или производный класс может переопределить член базового класса, в котором происходит тогда затенение *через наследование*.</span><span class="sxs-lookup"><span data-stu-id="21f5e-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="21f5e-113">Затемнения посредством области</span><span class="sxs-lookup"><span data-stu-id="21f5e-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="21f5e-114">Это программные элементы в модуле, классе или структуре могут иметь таким же именем, но разными областями действия.</span><span class="sxs-lookup"><span data-stu-id="21f5e-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="21f5e-115">Если код ссылается на имя, они совместно используют два элемента объявляются таким образом, элемент с более узкой областью действия затеняет второй элемент (узкая — область видимости блока).</span><span class="sxs-lookup"><span data-stu-id="21f5e-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="21f5e-116">Например, модуль может определить `Public` переменную с именем `temp`, и процедура в модуле может объявить локальную переменную, которая также называется `temp`.</span><span class="sxs-lookup"><span data-stu-id="21f5e-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="21f5e-117">Ссылки на `temp` внутри процедуры доступа к локальной переменной, а ссылки на `temp` из вне процедуры — к `Public` переменной.</span><span class="sxs-lookup"><span data-stu-id="21f5e-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="21f5e-118">В данном случае переменная процедуры `temp` затеняет переменную модуля `temp`.</span><span class="sxs-lookup"><span data-stu-id="21f5e-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="21f5e-119">На следующем рисунке показано две переменные, обе с именем `temp`.</span><span class="sxs-lookup"><span data-stu-id="21f5e-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="21f5e-120">Локальная переменная `temp` затеняет переменную-член `temp` при доступе из своей собственной процедуры `p`.</span><span class="sxs-lookup"><span data-stu-id="21f5e-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="21f5e-121">Однако `MyClass` ключевое слово обходит затенение и обращается к переменной-члена.</span><span class="sxs-lookup"><span data-stu-id="21f5e-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 <span data-ttu-id="21f5e-122">![График схемы затемнения посредством области](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span><span class="sxs-lookup"><span data-stu-id="21f5e-122">![Graphic diagram of shadowing through scope](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span></span>  
<span data-ttu-id="21f5e-123">Затемнения посредством области</span><span class="sxs-lookup"><span data-stu-id="21f5e-123">Shadowing through scope</span></span>  
  
 <span data-ttu-id="21f5e-124">Пример затемнения посредством области см. в разделе [как: сокрытие переменной с тем же именем, как к переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="21f5e-124">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="21f5e-125">Затемнения посредством наследования</span><span class="sxs-lookup"><span data-stu-id="21f5e-125">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="21f5e-126">Если производный класс переопределяет программный элемент, наследуемый от базового класса, переопределенный элемент затеняет исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="21f5e-126">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="21f5e-127">Можно скрыть любой тип объявленного элемента, или набор перегруженных элементов с любым другим типом.</span><span class="sxs-lookup"><span data-stu-id="21f5e-127">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="21f5e-128">Например `Integer` переменной можно скрыть `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="21f5e-128">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="21f5e-129">При скрытии процедуры другой можно использовать другой список параметров и другой тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="21f5e-129">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="21f5e-130">На следующем рисунке показан базовый класс `b` и производный класс `d` , наследуемый от `b`.</span><span class="sxs-lookup"><span data-stu-id="21f5e-130">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="21f5e-131">Базовый класс определяет процедуру с именем `proc`, и его скрывает производного класса с помощью другой процедуры с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="21f5e-131">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="21f5e-132">Первый `Call` оператор обращается к затенение `proc` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="21f5e-132">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="21f5e-133">Однако `MyBase` ключевое слово обходит затенение и обращается к затененной процедуре в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="21f5e-133">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 <span data-ttu-id="21f5e-134">![График схемы затемнения посредством наследования](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span><span class="sxs-lookup"><span data-stu-id="21f5e-134">![Graphic diagram of shadowing through inheritance](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span></span>  
<span data-ttu-id="21f5e-135">Затемнения посредством наследования</span><span class="sxs-lookup"><span data-stu-id="21f5e-135">Shadowing through inheritance</span></span>  
  
 <span data-ttu-id="21f5e-136">Пример затемнения посредством наследования см. в разделе [как: сокрытие переменной с тем же именем, как к переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: скрывать унаследованные переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="21f5e-136">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="21f5e-137">Затенение и уровень доступа</span><span class="sxs-lookup"><span data-stu-id="21f5e-137">Shadowing and Access Level</span></span>  
 <span data-ttu-id="21f5e-138">Переопределяющий элемент не всегда доступен из кода с помощью производного класса.</span><span class="sxs-lookup"><span data-stu-id="21f5e-138">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="21f5e-139">Например, он может быть объявлен `Private`.</span><span class="sxs-lookup"><span data-stu-id="21f5e-139">For example, it might be declared `Private`.</span></span> <span data-ttu-id="21f5e-140">В таком случае Затенение нарушается, и компилятор разрешает все ссылки на один элемент, который бы, если бы была затенения не.</span><span class="sxs-lookup"><span data-stu-id="21f5e-140">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="21f5e-141">Этот элемент является наименьшем количестве последовательных шагов от переопределяющий класс доступного элемента.</span><span class="sxs-lookup"><span data-stu-id="21f5e-141">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="21f5e-142">Если переопределяемый элемент является процедурой, разрешения является ближайший доступный с тем же именем, список параметров и тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="21f5e-142">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="21f5e-143">В следующем примере показано иерархии наследования из трех классов.</span><span class="sxs-lookup"><span data-stu-id="21f5e-143">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="21f5e-144">Каждый класс определяет `Sub` процедура `display`, и каждый производный класс затеняет `display` процедуры в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="21f5e-144">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="21f5e-145">В предыдущем примере производный класс `secondClass` shadows `display` с `Private` процедуры.</span><span class="sxs-lookup"><span data-stu-id="21f5e-145">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="21f5e-146">Если модуль `callDisplay` вызовы `display` в `secondClass`, вызывающий код находится за пределами `secondClass` и поэтому невозможно получить доступ к закрытым `display` процедуры.</span><span class="sxs-lookup"><span data-stu-id="21f5e-146">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="21f5e-147">Затенение нарушается, и компилятор разрешает ссылку на базовый класс `display` процедуры.</span><span class="sxs-lookup"><span data-stu-id="21f5e-147">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="21f5e-148">Однако дополнительный производный класс `thirdClass` объявляет `display` как `Public`, поэтому код в `callDisplay` к нему возможен доступ.</span><span class="sxs-lookup"><span data-stu-id="21f5e-148">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="21f5e-149">Сокрытием и переопределением</span><span class="sxs-lookup"><span data-stu-id="21f5e-149">Shadowing and Overriding</span></span>  
 <span data-ttu-id="21f5e-150">Не следует путать затенение с переопределением.</span><span class="sxs-lookup"><span data-stu-id="21f5e-150">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="21f5e-151">Оба метода используются, когда производный класс наследует от базового класса, и другое замещает один объявленный элемент другим.</span><span class="sxs-lookup"><span data-stu-id="21f5e-151">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="21f5e-152">Но существуют значительные различия между ними.</span><span class="sxs-lookup"><span data-stu-id="21f5e-152">But there are significant differences between the two.</span></span> <span data-ttu-id="21f5e-153">Сравнение см. в разделе [различия между сокрытием и переопределение](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="21f5e-153">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="21f5e-154">Затенение и перегрузка</span><span class="sxs-lookup"><span data-stu-id="21f5e-154">Shadowing and Overloading</span></span>  
 <span data-ttu-id="21f5e-155">При скрытии же элемент с более чем одного элемента базового класса в производный класс, переопределяющий элементы становятся перегруженные версии этого элемента.</span><span class="sxs-lookup"><span data-stu-id="21f5e-155">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="21f5e-156">Дополнительные сведения см. в разделе [перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="21f5e-156">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="21f5e-157">Доступ к скрытый элемент</span><span class="sxs-lookup"><span data-stu-id="21f5e-157">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="21f5e-158">Обращение к элементу производного класса обычно происходит через текущий экземпляр этого класса путем указания имени элемента `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="21f5e-158">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="21f5e-159">Если производный класс скрывает элемент базового класса, можно получить доступ к элемент базового класса путем определения ее с `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="21f5e-159">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="21f5e-160">Пример доступа к скрытый элемент, в разделе [как: доступ к переменной скрыто, класса, производного от](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="21f5e-160">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="21f5e-161">Объявление переменной объекта</span><span class="sxs-lookup"><span data-stu-id="21f5e-161">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="21f5e-162">Как создать переменную объекта могут также влиять на ли производный класс обращается к скрывающий элемент или переопределяемый элемент.</span><span class="sxs-lookup"><span data-stu-id="21f5e-162">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="21f5e-163">В следующем примере создается два объекта производного класса, но один объект объявлен как базовый класс, а другой — как производного класса.</span><span class="sxs-lookup"><span data-stu-id="21f5e-163">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="21f5e-164">В предыдущем примере переменной `basObj` объявлен в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="21f5e-164">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="21f5e-165">Назначение `dervCls` объекта он реализует расширяющее преобразование и, соответственно, допустимо.</span><span class="sxs-lookup"><span data-stu-id="21f5e-165">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="21f5e-166">Однако базовый класс не может получить доступ к скрывающий версии переменной `z` в производном классе, поэтому компилятор разрешает `basObj.z` к исходному значению базового класса.</span><span class="sxs-lookup"><span data-stu-id="21f5e-166">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f5e-167">См. также</span><span class="sxs-lookup"><span data-stu-id="21f5e-167">See Also</span></span>  
 [<span data-ttu-id="21f5e-168">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="21f5e-168">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="21f5e-169">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21f5e-169">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="21f5e-170">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="21f5e-170">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="21f5e-171">Shadows</span><span class="sxs-lookup"><span data-stu-id="21f5e-171">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="21f5e-172">Переопределения</span><span class="sxs-lookup"><span data-stu-id="21f5e-172">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="21f5e-173">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="21f5e-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="21f5e-174">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="21f5e-174">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
