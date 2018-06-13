---
title: Основы наследования (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 9225e5fd9fa35ae06414018a109f66515f99363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655193"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="9c4b7-102">Основы наследования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c4b7-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="9c4b7-103">`Inherits` Оператор используется для объявления нового класса, называемого *производного класса*, основываясь на существующий класс, называемый *базового класса*.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="9c4b7-104">Производные классы наследуют и могут расширять свойства, методы, события, поля и константы, определенные в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="9c4b7-105">Далее описываются некоторые правила наследования и модификаторов, которые можно использовать, чтобы изменить способ классы наследуют или наследования:</span><span class="sxs-lookup"><span data-stu-id="9c4b7-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="9c4b7-106">По умолчанию все классы могут наследоваться в том случае, если они помечены как с `NotInheritable` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="9c4b7-107">Классы могут наследовать от других классов в проекте или из классов других сборок, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="9c4b7-108">В отличие от языков, которые позволяют множественное наследование Visual Basic позволяет только единичное наследование в классах; то есть производные классы могут иметь только один базовый класс.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="9c4b7-109">Несмотря на то, что не допускается множественное наследование в классах, классы могут реализовывать несколько интерфейсов, которые способны эффективно выполнять те же самые задачи.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="9c4b7-110">Чтобы предотвратить предоставление элементов с ограничениями в базовом классе, тип доступа производного класса должен быть больше или более строгим, чем ее базовый класс.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="9c4b7-111">Например `Public` класс не может наследовать `Friend` или `Private` класса и `Friend` класс не может наследовать `Private` класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="9c4b7-112">Модификаторы наследования</span><span class="sxs-lookup"><span data-stu-id="9c4b7-112">Inheritance Modifiers</span></span>  
 <span data-ttu-id="9c4b7-113">Visual Basic предоставляет следующие инструкции на уровне класса и модификаторы для поддержки наследования:</span><span class="sxs-lookup"><span data-stu-id="9c4b7-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="9c4b7-114">`Inherits` оператор — определяет базовый класс.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="9c4b7-115">`NotInheritable` модификатор — не позволяет использовать класс в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="9c4b7-116">`MustInherit` модификатор — указывает, что класс предназначен для использования в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="9c4b7-117">Экземпляры `MustInherit` классов нельзя создать напрямую; они могут быть созданы только как базовый класс экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="9c4b7-118">(Другие языки программирования, таких как C# и C++ использовать термин *абстрактного класса* для описания такого класса.)</span><span class="sxs-lookup"><span data-stu-id="9c4b7-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="9c4b7-119">Переопределение свойств и методов в производных классах</span><span class="sxs-lookup"><span data-stu-id="9c4b7-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="9c4b7-120">По умолчанию производный класс наследует свойства и методы от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="9c4b7-121">Если унаследованное свойство или метод должен вести себя по-разному в производном классе, он может быть *переопределении*.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="9c4b7-122">То есть можно определить новую реализацию метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="9c4b7-123">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="9c4b7-124">`Overridable` — Позволяет свойства или метода в классе для переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="9c4b7-125">`Overrides` Переопределяет `Overridable` свойства или метода, определенного в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="9c4b7-126">`NotOverridable` — Не позволяет переопределять свойство или метод в наследующем классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="9c4b7-127">По умолчанию `Public` методы являются `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="9c4b7-128">`MustOverride` — Требуется, производном классе переопределяют свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="9c4b7-129">Когда `MustOverride` используется ключевое слово, определение метода состоит из только что `Sub`, `Function`, или `Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="9c4b7-130">Другие инструкции не допускаются и в частности является не `End Sub` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="9c4b7-131">`MustOverride` методы должны быть объявлены в `MustInherit` классы.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="9c4b7-132">Предположим, что вы хотите определить классы для обработки заработной платы.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="9c4b7-133">Можно определить универсальный `Payroll` класс, содержащий `RunPayroll` метод, который рассчитывает платежную неделю.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="9c4b7-134">Затем можно использовать `Payroll` как базовый класс для более специализированного `BonusPayroll` класс, который может использоваться при распределении премий между сотрудниками.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="9c4b7-135">`BonusPayroll` Класс может наследовать и переопределять `PayEmployee` метод, определенный в базовом `Payroll` класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="9c4b7-136">В следующем примере определяется базовый класс, `Payroll,` и производный класс `BonusPayroll`, который переопределяет унаследованный метод `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="9c4b7-137">Процедура `RunPayroll`, создает и затем передает `Payroll` объекта и `BonusPayroll` в функцию `Pay`, выполняющего `PayEmployee` обоих объектов.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="9c4b7-138">MyBase-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="9c4b7-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="9c4b7-139">`MyBase` Ключевое слово ведет себя как объектную переменную, которая ссылается на базовый класс текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="9c4b7-140">`MyBase` часто используются для доступа к членам базового класса, которые переопределены или скрыты в производном классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="9c4b7-141">В частности `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="9c4b7-142">Например предположим, что вы разрабатываете производного класса, который переопределяет метод, унаследованный от базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="9c4b7-143">Переопределенный метод можно вызвать метод в базовом классе и изменить возвращаемое значение, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="9c4b7-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 <span data-ttu-id="9c4b7-144">Следующий список описывает ограничения на использование `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="9c4b7-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="9c4b7-145">`MyBase` относится непосредственно к базовому классу и его унаследованным членам.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="9c4b7-146">Он не может использоваться для доступа к `Private` членов в классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="9c4b7-147">`MyBase` является зарезервированным словом, а не реальным объектом.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="9c4b7-148">`MyBase` нельзя присвоить переменной, передаваемой процедурам или использовать в `Is` сравнения.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="9c4b7-149">Метод, `MyBase` определяет не обязательно должен быть определен в непосредственно к базовому классу; вместо этого может определяться в косвенно наследуемый базовый класс.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="9c4b7-150">Ссылка, с указанием `MyBase` для правильной компиляции один из базовых классов должен содержать метод, сопоставляющий имена и типы параметров, появляющихся в вызове.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="9c4b7-151">Нельзя использовать `MyBase` для вызова `MustOverride` базовые методы класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="9c4b7-152">`MyBase` не может использоваться для квалификации самого себя.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="9c4b7-153">Таким образом следующий код является недопустимым:</span><span class="sxs-lookup"><span data-stu-id="9c4b7-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="9c4b7-154">`MyBase` не может использоваться в модулях.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="9c4b7-155">`MyBase` не может использоваться для доступа к членам базового класса, помеченные как `Friend` Если базовый класс находится в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="9c4b7-156">Дополнительные сведения и еще один пример см. в разделе [как: доступ к переменной скрыто, класса, производного от](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="9c4b7-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="9c4b7-157">MyClass-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="9c4b7-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="9c4b7-158">`MyClass` Ключевое слово ведет себя как объектную переменную, которая ссылается на текущий экземпляр класса, который был изначально реализован.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="9c4b7-159">`MyClass` напоминает `Me`, но каждый метод и свойство вызова на `MyClass` считается, что метод или свойство были [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="9c4b7-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="9c4b7-160">Таким образом что метод или свойство не изменяется путем переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="9c4b7-161">`MyClass` является зарезервированным словом, а не реальным объектом.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="9c4b7-162">`MyClass` нельзя присвоить переменной, передаваемой процедурам или использовать в `Is` сравнения.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="9c4b7-163">`MyClass` ссылается на содержащий класс и его унаследованные члены.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="9c4b7-164">`MyClass` можно использовать в качестве квалификатора для `Shared` члены.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="9c4b7-165">`MyClass` нельзя использовать внутри `Shared` метода, но может использоваться внутри метода экземпляра для доступа к общему члену класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="9c4b7-166">`MyClass` не может использоваться в стандартных модулях.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="9c4b7-167">`MyClass` можно использовать для определения метода, который определен в базовом классе и не имеющего реализации метода этого класса.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="9c4b7-168">Эта ссылка имеет то же значение, что `MyBase.` *метод*.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="9c4b7-169">В следующем примере сравниваются `Me` и `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-169">The following example compares `Me` and `MyClass`.</span></span>  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="9c4b7-170">Несмотря на то что `derivedClass` переопределяет `testMethod`, `MyClass` ключевое слово в `useMyClass` аннулирует переопределение и компилятор вызов версию базового класса `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="9c4b7-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4b7-171">См. также</span><span class="sxs-lookup"><span data-stu-id="9c4b7-171">See Also</span></span>  
 [<span data-ttu-id="9c4b7-172">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="9c4b7-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="9c4b7-173">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="9c4b7-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
