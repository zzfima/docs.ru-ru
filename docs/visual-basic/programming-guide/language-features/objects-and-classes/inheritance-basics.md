---
title: "Основы наследования (Visual Basic) | Документы Microsoft"
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
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
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
ms.sourcegitcommit: 4892ed6dcfb3843bd6cb2de2d3e032bfeb1efdf9
ms.openlocfilehash: 43b6505634b12f7f8353866e938151f1e00fb073
ms.contentlocale: ru-ru
ms.lasthandoff: 05/16/2017

---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="7224e-102">Основы наследования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7224e-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="7224e-103">`Inherits` Инструкция используется для объявления нового класса, называемого *производный класс*, основанный на существующем классе, называемом *базового класса*.</span><span class="sxs-lookup"><span data-stu-id="7224e-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="7224e-104">Производные классы наследуют и могут расширять свойства, методы, события, поля и константы, определенные в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="7224e-105">В следующем разделе описаны некоторые правила наследования и модификаторы, которые можно использовать для изменения способа классы наследуют или наследования:</span><span class="sxs-lookup"><span data-stu-id="7224e-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="7224e-106">По умолчанию все классы могут наследоваться в том случае, если помечено `NotInheritable` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7224e-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="7224e-107">Классы могут наследовать от других классов в проекте или из классов других сборок, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="7224e-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="7224e-108">В отличие от языков, которые позволяют множественное наследование [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] позволяет только единичное наследование в классах; то есть производные классы могут иметь только один базовый класс.</span><span class="sxs-lookup"><span data-stu-id="7224e-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="7224e-109">Хотя в классах не допускается множественное наследование, классы могут реализовывать несколько интерфейсов, которые способны эффективно выполнять те же самые задачи.</span><span class="sxs-lookup"><span data-stu-id="7224e-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="7224e-110">Чтобы предотвратить предоставление элементов с ограничениями в базовом классе, тип доступа производного класса должен быть равен или больше ограничений, чем ее базовый класс.</span><span class="sxs-lookup"><span data-stu-id="7224e-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="7224e-111">Например `Public` класс не может наследовать `Friend` или `Private` класс и `Friend` класс не может наследовать `Private` класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="7224e-112">Модификаторы наследования</span><span class="sxs-lookup"><span data-stu-id="7224e-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7224e-113">вводит следующие инструкции на уровне класса и модификаторы для поддержки наследования:</span><span class="sxs-lookup"><span data-stu-id="7224e-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="7224e-114">`Inherits`инструкции — определяет базовый класс.</span><span class="sxs-lookup"><span data-stu-id="7224e-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="7224e-115">`NotInheritable`модификатор — не позволяет использовать класс в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="7224e-116">`MustInherit`модификатор — указывает, что класс предназначен для использования только в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="7224e-117">Экземпляры `MustInherit` классы нельзя создать напрямую, они могут быть созданы только как базовый класс экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="7224e-118">(Другие языки программирования, такие как C++ и C#, использовать термин *абстрактного класса* для описания такого класса.)</span><span class="sxs-lookup"><span data-stu-id="7224e-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="7224e-119">Переопределение свойств и методов в производных классах</span><span class="sxs-lookup"><span data-stu-id="7224e-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="7224e-120">По умолчанию производный класс наследует свойства и методы от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="7224e-121">Если унаследованное свойство или метод должен вести себя по-разному в производном классе может быть *переопределении*.</span><span class="sxs-lookup"><span data-stu-id="7224e-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="7224e-122">То есть можно определить новую реализацию метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="7224e-123">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="7224e-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="7224e-124">`Overridable`— Позволяет свойство или метод в классе для переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="7224e-125">`Overrides`Переопределяет `Overridable` свойство или метод, определенный в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="7224e-126">`NotOverridable`— Не позволяет переопределять свойство или метод в наследующем классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="7224e-127">По умолчанию `Public` методы являются `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="7224e-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="7224e-128">`MustOverride`— Требует, что производного класса переопределяют свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="7224e-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="7224e-129">Когда `MustOverride` используется ключевое слово, определение метода состоит из только что `Sub`, `Function`, или `Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7224e-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="7224e-130">Другие инструкции не допускаются и в частности является не `End Sub` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7224e-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="7224e-131">`MustOverride`методы должны быть объявлены в `MustInherit` классы.</span><span class="sxs-lookup"><span data-stu-id="7224e-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="7224e-132">Предположим, что необходимо определить классы для обработки платежных ведомостей.</span><span class="sxs-lookup"><span data-stu-id="7224e-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="7224e-133">Можно определить универсальный `Payroll` класс, содержащий `RunPayroll` метод, который рассчитывает платежную неделю.</span><span class="sxs-lookup"><span data-stu-id="7224e-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="7224e-134">Затем можно использовать `Payroll` в качестве базового класса для более специализированного `BonusPayroll` класс, который может использоваться при распределении премий между сотрудниками.</span><span class="sxs-lookup"><span data-stu-id="7224e-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="7224e-135">`BonusPayroll` Класс может наследовать и переопределять `PayEmployee` метод, определенный в базовом `Payroll` класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="7224e-136">В следующем примере определяется базовый класс, `Payroll,` и производный класс `BonusPayroll`, который переопределяет унаследованный метод `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="7224e-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="7224e-137">Процедура `RunPayroll`, создает и затем передает `Payroll` объекта и `BonusPayroll` в функцию `Pay`, который выполняет `PayEmployee` обоих объектов.</span><span class="sxs-lookup"><span data-stu-id="7224e-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 <span data-ttu-id="7224e-138">[!code-vb[VbVbalrOOP&#28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7224e-138">[!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span></span>  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="7224e-139">MyBase-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="7224e-139">The MyBase Keyword</span></span>  
 <span data-ttu-id="7224e-140">`MyBase` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-140">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="7224e-141">`MyBase`часто используется для доступа к членам базового класса, которые переопределены или скрыты в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-141">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="7224e-142">В частности `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-142">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="7224e-143">Например предположим, что разрабатывается производный класс, который переопределяет метод, унаследованный от базового класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-143">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="7224e-144">Переопределенный метод можно вызвать метод в базовом классе и изменить возвращаемое значение, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="7224e-144">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="7224e-145">[!code-vb[VbVbalrOOP&#109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7224e-145">[!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="7224e-146">Следующий список описывает ограничения на использование `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="7224e-146">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="7224e-147">`MyBase`относится непосредственно к базовому классу и его унаследованным членам.</span><span class="sxs-lookup"><span data-stu-id="7224e-147">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="7224e-148">Он не может использоваться для доступа к `Private` членов в классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-148">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="7224e-149">`MyBase`является зарезервированным словом, а не реальным объектом.</span><span class="sxs-lookup"><span data-stu-id="7224e-149">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="7224e-150">`MyBase`нельзя присвоить переменной, передаваемой процедурам или использовать в `Is` сравнения.</span><span class="sxs-lookup"><span data-stu-id="7224e-150">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="7224e-151">Метод, `MyBase` определяет не обязательно должен быть определен в непосредственно к базовому классу; вместо этого можно задать в косвенно наследуемый базовый класс.</span><span class="sxs-lookup"><span data-stu-id="7224e-151">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="7224e-152">Ссылка, с указанием `MyBase` для правильной компиляции некоторых базовых классов должен содержать метод, сопоставляющий имена и типы параметров, появляющихся в вызове.</span><span class="sxs-lookup"><span data-stu-id="7224e-152">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="7224e-153">Нельзя использовать `MyBase` для вызова `MustOverride` базовые методы класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-153">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="7224e-154">`MyBase`не может использоваться для квалификации самого себя.</span><span class="sxs-lookup"><span data-stu-id="7224e-154">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="7224e-155">Таким образом следующий код является недопустимым:</span><span class="sxs-lookup"><span data-stu-id="7224e-155">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="7224e-156">`MyBase`не может использоваться в модулях.</span><span class="sxs-lookup"><span data-stu-id="7224e-156">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="7224e-157">`MyBase`не может использоваться для доступа к членам базового класса, помеченные как `Friend` , если базовый класс находится в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="7224e-157">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="7224e-158">Дополнительные сведения и еще один пример см. в разделе [Практическое руководство: доступ к переменной скрыты с помощью производного класса](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="7224e-158">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="7224e-159">MyClass-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="7224e-159">The MyClass Keyword</span></span>  
 <span data-ttu-id="7224e-160">`MyClass` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован.</span><span class="sxs-lookup"><span data-stu-id="7224e-160">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="7224e-161">`MyClass`напоминает `Me`, но каждый метод и свойство вызвать `MyClass` рассматривается, как будто метод или свойство [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="7224e-161">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="7224e-162">Таким образом метод или свойство не изменяется путем переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7224e-162">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="7224e-163">`MyClass`является зарезервированным словом, а не реальным объектом.</span><span class="sxs-lookup"><span data-stu-id="7224e-163">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="7224e-164">`MyClass`нельзя присвоить переменной, передаваемой процедурам или использовать в `Is` сравнения.</span><span class="sxs-lookup"><span data-stu-id="7224e-164">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="7224e-165">`MyClass`ссылается на содержащий класс и его унаследованные члены.</span><span class="sxs-lookup"><span data-stu-id="7224e-165">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="7224e-166">`MyClass`может использоваться в качестве квалификатора для `Shared` члены.</span><span class="sxs-lookup"><span data-stu-id="7224e-166">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="7224e-167">`MyClass`нельзя использовать внутри `Shared` метода, но можно использовать внутри метода экземпляра для доступа к общему члену класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-167">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="7224e-168">`MyClass`не может использоваться в стандартных модулях.</span><span class="sxs-lookup"><span data-stu-id="7224e-168">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="7224e-169">`MyClass`можно использовать для квалификации метода, определенного в базовом классе и не имеющего реализации метода этого класса.</span><span class="sxs-lookup"><span data-stu-id="7224e-169">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="7224e-170">Эта ссылка имеет то же значение, что `MyBase.` *метод*.</span><span class="sxs-lookup"><span data-stu-id="7224e-170">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="7224e-171">В следующем примере сравниваются `Me` и `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="7224e-171">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="7224e-172">Несмотря на то что `derivedClass` переопределяет `testMethod`, `MyClass` ключевое слово в `useMyClass` аннулирует переопределение и компилятор вызов версию базового класса `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="7224e-172">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7224e-173">См. также</span><span class="sxs-lookup"><span data-stu-id="7224e-173">See Also</span></span>  
 <span data-ttu-id="7224e-174">[Оператор Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7224e-174">[Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="7224e-175"> [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="7224e-175"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>

