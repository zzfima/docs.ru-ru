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
# <a name="inheritance-basics-visual-basic"></a>Основы наследования (Visual Basic)

Оператор `Inherits` используется для объявления нового класса, называемого *производным классом*, на основе существующего класса, называемого *базовым классом*. Производные классы наследуют и могут расширять, свойства, методы, события, поля и константы, определенные в базовом классе. В следующем разделе описаны некоторые правила наследования, а также модификаторы, которые можно использовать для изменения способа наследования или наследования классов.

- По умолчанию все классы наследуются, если не отмечено ключевым словом `NotInheritable`. Классы могут наследовать от других классов в проекте или из классов в других сборках, на которые ссылается проект.

- В отличие от языков, допускающих множественное наследование, Visual Basic допускает только одно наследование в классах; то есть производные классы могут иметь только один базовый класс. Хотя множественное наследование не разрешено в классах, классы могут реализовывать несколько интерфейсов, что может эффективно выполнять те же самые концы.

- Чтобы предотвратить предоставление ограниченных элементов в базовом классе, тип доступа производного класса должен быть равным или более ограничивающим, чем его базовый класс. Например, класс `Public` не может наследовать `Friend` или класс `Private`, а класс `Friend` не может наследовать класс `Private`.

## <a name="inheritance-modifiers"></a>Модификаторы наследования

Visual Basic вводит следующие операторы и модификаторы уровня класса для поддержки наследования:

- Оператор `Inherits` — указывает базовый класс.

- Модификатор `NotInheritable` — не позволяет программистам использовать класс в качестве базового класса.

- Модификатор `MustInherit` — указывает, что класс предназначен для использования только в качестве базового класса. Экземпляры классов `MustInherit` не могут быть созданы напрямую; они могут быть созданы только как экземпляры базового класса производного класса. (Другие языки программирования, такие как C++ и C#, используют термин *абстрактный класс* для описания такого класса.)

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Переопределение свойств и методов в производных классах

По умолчанию производный класс наследует свойства и методы от своего базового класса. Если унаследованное свойство или метод должны вести себя по-разному в производном классе, его можно *переопределить*. То есть можно определить новую реализацию метода в производном классе. Следующие модификаторы используются для управления переопределением свойств и методов.

- `Overridable` — позволяет переопределять свойство или метод в классе в производном классе.

- `Overrides` — переопределяет свойство `Overridable` или метод, определенный в базовом классе.

- `NotOverridable` — предотвращает переопределение свойства или метода в наследующем классе. По умолчанию `Public` методы `NotOverridable`.

- `MustOverride` — требует, чтобы производный класс переопределял свойство или метод. При использовании ключевого слова `MustOverride` определение метода состоит только из `Sub`, `Function`или `Property` оператора. Никакие другие инструкции не допускаются, а в частности нет `End Sub` или `End Function` инструкции. `MustOverride` методы должны быть объявлены в классах `MustInherit`.

Предположим, необходимо определить классы для работы с Payroll. Можно определить универсальный `Payroll` класс, содержащий метод `RunPayroll`, который вычисляет зарплату для типичной недели. Затем можно использовать `Payroll` в качестве базового класса для более специализированного `BonusPayroll` класса, который можно использовать при распределении премий сотрудников.

Класс `BonusPayroll` может наследовать и переопределять метод `PayEmployee`, определенный в базовом классе `Payroll`.

В следующем примере определяется базовый класс, `Payroll,` и производный класс `BonusPayroll`, который переопределяет унаследованный метод `PayEmployee`. Процедура, `RunPayroll`, создает и передает `Payroll` объект и объект `BonusPayroll` в функцию, `Pay`, которая выполняет метод `PayEmployee` обоих объектов.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>Ключевое слово MyBase

Ключевое слово `MyBase` ведет себя как объектная переменная, которая ссылается на базовый класс текущего экземпляра класса. `MyBase` часто используется для доступа к членам базового класса, которые переопределяются или переобъявляются в производном классе. В частности, `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.

Например, предположим, что вы разрабатываете производный класс, переопределяющий метод, унаследованный от базового класса. Переопределенный метод может вызвать метод в базовом классе и изменить возвращаемое значение, как показано в следующем фрагменте кода:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

В следующем списке описаны ограничения на использование `MyBase`.

- `MyBase` ссылается на непосредственный базовый класс и его унаследованные члены. Его нельзя использовать для доступа к членам `Private` в классе.

- `MyBase` является ключевым словом, а не реальным объектом. `MyBase` нельзя присвоить переменной, передать ее процедурам или использовать в сравнении `Is`.

- Метод, `MyBase`ные квалификаторы, не должен определяться в непосредственном базовом классе. Вместо этого его можно определить в косвенно наследуемом базовом классе. Чтобы обеспечить правильную компиляцию ссылки с `MyBase`, некоторые базовые классы должны содержать метод, соответствующий имени и типам параметров, которые отображаются в вызове.

- Нельзя использовать `MyBase` для вызова методов `MustOverride` базового класса.

- `MyBase` нельзя использовать для квалификации самого себя. Поэтому следующий код является недопустимым:

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase` нельзя использовать в модулях.

- `MyBase` нельзя использовать для доступа к членам базового класса, помеченным как `Friend`, если базовый класс находится в другой сборке.

Дополнительные сведения и другой пример см. в разделе [как получить доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>Ключевое слово MyClass

Ключевое слово `MyClass` ведет себя как объектная переменная, которая ссылается на текущий экземпляр класса как изначально реализованный. `MyClass` напоминает `Me`, но каждый вызов метода и свойства в `MyClass` обрабатывается так, как если бы метод или свойство были [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Таким образом, переопределение в производном классе не влияет на метод или свойство.

- `MyClass` является ключевым словом, а не реальным объектом. `MyClass` нельзя присвоить переменной, передать ее процедурам или использовать в сравнении `Is`.

- `MyClass` ссылается на содержащий класс и его унаследованные члены.

- `MyClass` можно использовать в качестве квалификатора для членов `Shared`.

- `MyClass` не может использоваться в методе `Shared`, но может использоваться внутри метода экземпляра для доступа к общему члену класса.

- `MyClass` нельзя использовать в стандартных модулях.

- `MyClass` можно использовать для определения метода, который определен в базовом классе и не имеет реализации метода, предоставленного в этом классе. Такая ссылка имеет то же значение, что и *метод*`MyBase.`.

В следующем примере сравниваются `Me` и `MyClass`.

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

Хотя `derivedClass` переопределяет `testMethod`, ключевое слово `MyClass` в `useMyClass` сводят последствия переопределения, и компилятор разрешает вызов версии базового класса `testMethod`.

## <a name="see-also"></a>См. также

- [Оператор Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
