---
title: Основы наследования
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
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350823"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="44f21-102">Основы наследования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44f21-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="44f21-103">Оператор `Inherits` используется для объявления нового класса, называемого *производным классом*, на основе существующего класса, называемого *базовым классом*.</span><span class="sxs-lookup"><span data-stu-id="44f21-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="44f21-104">Производные классы наследуют и могут расширять, свойства, методы, события, поля и константы, определенные в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="44f21-105">В следующем разделе описаны некоторые правила наследования, а также модификаторы, которые можно использовать для изменения способа наследования или наследования классов.</span><span class="sxs-lookup"><span data-stu-id="44f21-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="44f21-106">По умолчанию все классы наследуются, если не отмечено ключевым словом `NotInheritable`.</span><span class="sxs-lookup"><span data-stu-id="44f21-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="44f21-107">Классы могут наследовать от других классов в проекте или из классов в других сборках, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="44f21-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="44f21-108">В отличие от языков, допускающих множественное наследование, Visual Basic допускает только одно наследование в классах; то есть производные классы могут иметь только один базовый класс.</span><span class="sxs-lookup"><span data-stu-id="44f21-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="44f21-109">Хотя множественное наследование не разрешено в классах, классы могут реализовывать несколько интерфейсов, что может эффективно выполнять те же самые концы.</span><span class="sxs-lookup"><span data-stu-id="44f21-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="44f21-110">Чтобы предотвратить предоставление ограниченных элементов в базовом классе, тип доступа производного класса должен быть равным или более ограничивающим, чем его базовый класс.</span><span class="sxs-lookup"><span data-stu-id="44f21-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="44f21-111">Например, класс `Public` не может наследовать `Friend` или класс `Private`, а класс `Friend` не может наследовать класс `Private`.</span><span class="sxs-lookup"><span data-stu-id="44f21-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="44f21-112">Модификаторы наследования</span><span class="sxs-lookup"><span data-stu-id="44f21-112">Inheritance Modifiers</span></span>

<span data-ttu-id="44f21-113">Visual Basic вводит следующие операторы и модификаторы уровня класса для поддержки наследования:</span><span class="sxs-lookup"><span data-stu-id="44f21-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="44f21-114">Оператор `Inherits` — указывает базовый класс.</span><span class="sxs-lookup"><span data-stu-id="44f21-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="44f21-115">Модификатор `NotInheritable` — не позволяет программистам использовать класс в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="44f21-116">Модификатор `MustInherit` — указывает, что класс предназначен для использования только в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="44f21-117">Экземпляры классов `MustInherit` не могут быть созданы напрямую; они могут быть созданы только как экземпляры базового класса производного класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="44f21-118">(Другие языки программирования, такие как C++ и C#, используют термин *абстрактный класс* для описания такого класса.)</span><span class="sxs-lookup"><span data-stu-id="44f21-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="44f21-119">Переопределение свойств и методов в производных классах</span><span class="sxs-lookup"><span data-stu-id="44f21-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="44f21-120">По умолчанию производный класс наследует свойства и методы от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="44f21-121">Если унаследованное свойство или метод должны вести себя по-разному в производном классе, его можно *переопределить*.</span><span class="sxs-lookup"><span data-stu-id="44f21-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="44f21-122">То есть можно определить новую реализацию метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="44f21-123">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="44f21-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="44f21-124">`Overridable` — позволяет переопределять свойство или метод в классе в производном классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="44f21-125">`Overrides` — переопределяет свойство `Overridable` или метод, определенный в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="44f21-126">`NotOverridable` — предотвращает переопределение свойства или метода в наследующем классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="44f21-127">По умолчанию `Public` методы `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="44f21-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="44f21-128">`MustOverride` — требует, чтобы производный класс переопределял свойство или метод.</span><span class="sxs-lookup"><span data-stu-id="44f21-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="44f21-129">При использовании ключевого слова `MustOverride` определение метода состоит только из `Sub`, `Function`или `Property` оператора.</span><span class="sxs-lookup"><span data-stu-id="44f21-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="44f21-130">Никакие другие инструкции не допускаются, а в частности нет `End Sub` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="44f21-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="44f21-131">`MustOverride` методы должны быть объявлены в классах `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="44f21-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="44f21-132">Предположим, необходимо определить классы для работы с Payroll.</span><span class="sxs-lookup"><span data-stu-id="44f21-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="44f21-133">Можно определить универсальный `Payroll` класс, содержащий метод `RunPayroll`, который вычисляет зарплату для типичной недели.</span><span class="sxs-lookup"><span data-stu-id="44f21-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="44f21-134">Затем можно использовать `Payroll` в качестве базового класса для более специализированного `BonusPayroll` класса, который можно использовать при распределении премий сотрудников.</span><span class="sxs-lookup"><span data-stu-id="44f21-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="44f21-135">Класс `BonusPayroll` может наследовать и переопределять метод `PayEmployee`, определенный в базовом классе `Payroll`.</span><span class="sxs-lookup"><span data-stu-id="44f21-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="44f21-136">В следующем примере определяется базовый класс, `Payroll,` и производный класс `BonusPayroll`, который переопределяет унаследованный метод `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="44f21-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="44f21-137">Процедура, `RunPayroll`, создает и передает `Payroll` объект и объект `BonusPayroll` в функцию, `Pay`, которая выполняет метод `PayEmployee` обоих объектов.</span><span class="sxs-lookup"><span data-stu-id="44f21-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="44f21-138">Ключевое слово MyBase</span><span class="sxs-lookup"><span data-stu-id="44f21-138">The MyBase Keyword</span></span>

<span data-ttu-id="44f21-139">Ключевое слово `MyBase` ведет себя как объектная переменная, которая ссылается на базовый класс текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="44f21-140">`MyBase` часто используется для доступа к членам базового класса, которые переопределяются или переобъявляются в производном классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="44f21-141">В частности, `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="44f21-142">Например, предположим, что вы разрабатываете производный класс, переопределяющий метод, унаследованный от базового класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="44f21-143">Переопределенный метод может вызвать метод в базовом классе и изменить возвращаемое значение, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="44f21-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="44f21-144">В следующем списке описаны ограничения на использование `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="44f21-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="44f21-145">`MyBase` ссылается на непосредственный базовый класс и его унаследованные члены.</span><span class="sxs-lookup"><span data-stu-id="44f21-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="44f21-146">Его нельзя использовать для доступа к членам `Private` в классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="44f21-147">`MyBase` является ключевым словом, а не реальным объектом.</span><span class="sxs-lookup"><span data-stu-id="44f21-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="44f21-148">`MyBase` нельзя присвоить переменной, передать ее процедурам или использовать в сравнении `Is`.</span><span class="sxs-lookup"><span data-stu-id="44f21-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="44f21-149">Метод, `MyBase`ные квалификаторы, не должен определяться в непосредственном базовом классе. Вместо этого его можно определить в косвенно наследуемом базовом классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="44f21-150">Чтобы обеспечить правильную компиляцию ссылки с `MyBase`, некоторые базовые классы должны содержать метод, соответствующий имени и типам параметров, которые отображаются в вызове.</span><span class="sxs-lookup"><span data-stu-id="44f21-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="44f21-151">Нельзя использовать `MyBase` для вызова методов `MustOverride` базового класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="44f21-152">`MyBase` нельзя использовать для квалификации самого себя.</span><span class="sxs-lookup"><span data-stu-id="44f21-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="44f21-153">Поэтому следующий код является недопустимым:</span><span class="sxs-lookup"><span data-stu-id="44f21-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="44f21-154">`MyBase` нельзя использовать в модулях.</span><span class="sxs-lookup"><span data-stu-id="44f21-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="44f21-155">`MyBase` нельзя использовать для доступа к членам базового класса, помеченным как `Friend`, если базовый класс находится в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="44f21-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="44f21-156">Дополнительные сведения и другой пример см. в разделе [как получить доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="44f21-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="44f21-157">Ключевое слово MyClass</span><span class="sxs-lookup"><span data-stu-id="44f21-157">The MyClass Keyword</span></span>

<span data-ttu-id="44f21-158">Ключевое слово `MyClass` ведет себя как объектная переменная, которая ссылается на текущий экземпляр класса как изначально реализованный.</span><span class="sxs-lookup"><span data-stu-id="44f21-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="44f21-159">`MyClass` напоминает `Me`, но каждый вызов метода и свойства в `MyClass` обрабатывается так, как если бы метод или свойство были [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="44f21-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="44f21-160">Таким образом, переопределение в производном классе не влияет на метод или свойство.</span><span class="sxs-lookup"><span data-stu-id="44f21-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="44f21-161">`MyClass` является ключевым словом, а не реальным объектом.</span><span class="sxs-lookup"><span data-stu-id="44f21-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="44f21-162">`MyClass` нельзя присвоить переменной, передать ее процедурам или использовать в сравнении `Is`.</span><span class="sxs-lookup"><span data-stu-id="44f21-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="44f21-163">`MyClass` ссылается на содержащий класс и его унаследованные члены.</span><span class="sxs-lookup"><span data-stu-id="44f21-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="44f21-164">`MyClass` можно использовать в качестве квалификатора для членов `Shared`.</span><span class="sxs-lookup"><span data-stu-id="44f21-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="44f21-165">`MyClass` не может использоваться в методе `Shared`, но может использоваться внутри метода экземпляра для доступа к общему члену класса.</span><span class="sxs-lookup"><span data-stu-id="44f21-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="44f21-166">`MyClass` нельзя использовать в стандартных модулях.</span><span class="sxs-lookup"><span data-stu-id="44f21-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="44f21-167">`MyClass` можно использовать для определения метода, который определен в базовом классе и не имеет реализации метода, предоставленного в этом классе.</span><span class="sxs-lookup"><span data-stu-id="44f21-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="44f21-168">Такая ссылка имеет то же значение, что и *метод*`MyBase.`.</span><span class="sxs-lookup"><span data-stu-id="44f21-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="44f21-169">В следующем примере сравниваются `Me` и `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="44f21-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="44f21-170">Хотя `derivedClass` переопределяет `testMethod`, ключевое слово `MyClass` в `useMyClass` сводят последствия переопределения, и компилятор разрешает вызов версии базового класса `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="44f21-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="44f21-171">См. также</span><span class="sxs-lookup"><span data-stu-id="44f21-171">See also</span></span>

- [<span data-ttu-id="44f21-172">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="44f21-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="44f21-173">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="44f21-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
