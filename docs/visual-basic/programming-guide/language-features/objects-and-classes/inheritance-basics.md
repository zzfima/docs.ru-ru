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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401463"
---
# <a name="inheritance-basics-visual-basic"></a>Основы наследования (Visual Basic)

Заявление `Inherits` используется для объявления нового класса, называемого *производным классом,* основанным на существующем классе, известном как *базовый класс.* Полученные классы наследуют и могут расширять свойства, методы, события, поля и константы, определенные в базовом классе. В следующем разделе описаны некоторые правила наследования, а также модификаторы, которые можно использовать для изменения способа наследования или наследования классов:

- По умолчанию все классы наследуются, если не помечены `NotInheritable` ключевым словом. Классы могут наследовать от других классов в проекте или из классов в других собраниях, на которые ссылается ваш проект.

- В отличие от языков, которые позволяют многократное наследование, Visual Basic разрешает только одно наследование в классах; то есть, производные классы могут иметь только один базовый класс. Хотя несколько наследований не допускается в классах, классы могут реализовать несколько интерфейсов, которые могут эффективно выполнять одни и те же цели.

- Для предотвращения разоблачения ограниченных элементов в базовом классе тип доступа производного класса должен быть равен или более ограничен, чем его базовый класс. Например, `Public` класс не `Friend` может `Private` наследовать или `Friend` класс, `Private` а класс не может наследовать класс.

## <a name="inheritance-modifiers"></a>Модификаторы наследования

Visual Basic вводит следующие инструкции классового уровня и модификаторы для поддержки наследования:

- `Inherits`заявление - определяет базовый класс.

- `NotInheritable`модификатор - Предотвращает использование программистами класса в качестве базового класса.

- `MustInherit`модификатор - указывает, что класс предназначен для использования только в качестве базового класса. Случаи `MustInherit` классов не могут быть созданы напрямую; они могут быть созданы только как экземпляры базового класса производного класса. (Другие языки программирования, такие как СЗ и СЗ, используют термин *абстрактный класс* для описания такого класса.)

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Преобладающие свойства и методы в классах производных

По умолчанию полученный класс наследует свойства и методы из своего базового класса. Если унаследованное свойство или метод должны вести себя по-разному в производном классе, оно может быть *переопределено.* То есть можно определить новую реализацию метода в производном классе. Следующие модификаторы используются для управления переопределением свойств и методов.

- `Overridable`- Позволяет переопределить свойство или метод в классе в производном классе.

- `Overrides`- Переопределяет `Overridable` свойство или метод, определенный в базовом классе.

- `NotOverridable`Предотвращает переопределить свойство или метод в наследственном классе. По умолчанию, `Public` `NotOverridable`методы .

- `MustOverride`- Требуется, чтобы полученный класс переопределить свойство или метод. Когда `MustOverride` ключевое слово используется, определение метода `Sub` `Function`состоит `Property` только из, или заявление. Никакие другие заявления не допускаются, и конкретно нет `End Sub` или `End Function` заявление. `MustOverride`методы должны быть `MustInherit` объявлены в классах.

Предположим, вы хотите определить классы для обработки заработной платы. Можно определить общий `Payroll` класс, `RunPayroll` содержащий метод, который вычисляет заработную плату за типичную неделю. Затем можно `Payroll` использовать в качестве базового `BonusPayroll` класса для более специализированного класса, который может быть использован при распределении бонусов сотрудников.

Класс `BonusPayroll` может наследовать и переопределять `PayEmployee` метод, `Payroll` определенный в базовом классе.

Следующий пример определяет базовый `Payroll,` класс и производный класс, `BonusPayroll`который `PayEmployee`переопределяет унаследованный метод. `RunPayroll`Процедура, , создает, а `Payroll` затем `BonusPayroll` передает объект и `Pay`объект функции, которая выполняет `PayEmployee` метод обоих объектов.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>Ключевое слово MyBase

Ключевое `MyBase` слово ведет себя как объектная переменная, отсылающая к базовому классу текущего экземпляра класса. `MyBase`часто используется для доступа к членам базового класса, которые переопределены или затеняются в производных классах. В частности, `MyBase.New` используется для явного вызова конструктора базового класса из производного конструктора класса.

Например, предположим, что вы разрабатываете производный класс, который переопределяет метод, унаследованный от базового класса. Переиверенный метод может вызвать метод в базовом классе и изменить значение возврата, как показано в следующем фрагменте кода:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

В следующем списке `MyBase`описаны ограничения на использование:

- `MyBase`относится к непосредственному базовому классу и его унаследованных членов. Он не может `Private` быть использован для доступа к членам в классе.

- `MyBase`является ключевым словом, а не реальным объектом. `MyBase`не могут быть назначены переменной, переданы `Is` процедуры или использованы в сравнении.

- Метод, `MyBase` который квалифицируется, не должен быть определен в непосредственном базовом классе; вместо этого он может быть определен в косвенно унаследованный базовый класс. Для правильной компиляции ссылки, квалифицированной `MyBase` для правильной компиляции, некоторый базовый класс должен содержать метод, соответствующий имени и типам параметров, которые отображаются в вызове.

- Вы не `MyBase` можете `MustOverride` использовать для вызова методов базового класса.

- `MyBase`не может быть использован для квалификации себя. Таким образом, следующий код не действителен:

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`не могут быть использованы в модулях.

- `MyBase`не может быть использован для доступа `Friend` к членам базового класса, которые помечены как если бы базовый класс находится в другой сборке.

Для получения дополнительной информации и другой пример, [см. Как: Доступ к переменной скрытые производные класса](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>Ключевое слово MyClass

Ключевое `MyClass` слово ведет себя как объектная переменная, отсылающая к текущему экземпляру класса как первоначально реализованный. `MyClass``Me`напоминает, но каждый метод `MyClass` и свойство вызова на рассматривается как если бы метод или свойство были [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Таким образом, метод или свойство не зависит от переопределения в производном классе.

- `MyClass`является ключевым словом, а не реальным объектом. `MyClass`не могут быть назначены переменной, переданы `Is` процедуры или использованы в сравнении.

- `MyClass`относится к содержащему классу и его наследственным членам.

- `MyClass`может быть использован в `Shared` качестве квалификатора для участников.

- `MyClass`не может быть `Shared` использован внутри метода, но может быть использован внутри экземпляра для доступа к общему члену класса.

- `MyClass`не могут быть использованы в стандартных модулях.

- `MyClass`может быть использован для квалификации метода, который определяется в базовом классе и который не имеет реализации метода, предусмотренного в этом классе. Такая ссылка имеет то `MyBase.`же значение, что и *метод.*

Следующий пример `Me` сравнивает и `MyClass`.

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

Даже `derivedClass` если `testMethod`переопределяет `MyClass` , `useMyClass` ключевое слово в сводит на нет последствия переопределения, и компилятор разрешает вызов в версию базового `testMethod`класса .

## <a name="see-also"></a>См. также раздел

- [Оператор Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
