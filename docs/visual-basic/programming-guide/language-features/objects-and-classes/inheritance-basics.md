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
ms.openlocfilehash: 3d772fb81eb13b9454f44ff8ae4256bdb4144caa
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970302"
---
# <a name="inheritance-basics-visual-basic"></a>Основы наследования (Visual Basic)
`Inherits` Инструкция используется для объявления новый класс с именем *производный класс*, основываясь на существующий класс, известный как *базового класса*. Производные классы наследуют и могут расширять свойства, методы, события, поля и константы, определенные в базовом классе. В следующем разделе описаны некоторые правила наследования и модификаторов, которые можно использовать для изменения способа классы наследуют или наследования:  
  
-   По умолчанию все классы могут наследоваться в том случае, если они помечены как с `NotInheritable` ключевое слово. Классы могут наследовать от других классов в проекте, либо из классов в других сборках, на которые ссылается проект.  
  
-   В отличие от языков, которые позволяют множественное наследование Visual Basic позволяет только одиночное наследование в классах; то есть производные классы могут иметь только один базовый класс. Несмотря на то, что множественное наследование не допускается в классах, классы могут реализовывать несколько интерфейсов, которые способны эффективно выполнять те же самые задачи.  
  
-   Чтобы избежать предоставление элементов с ограничениями в базовом классе, тип доступа производного класса должен быть равным или более строгие, чем ее базовый класс. Например `Public` класс не может наследовать `Friend` или `Private` класса и `Friend` класс не может наследовать `Private` класса.  
  
## <a name="inheritance-modifiers"></a>Модификаторов наследования  
 Visual Basic предоставляет следующие инструкции на уровне класса и модификаторы для поддержки наследования:  
  
-   `Inherits` Инструкция — указывает базовый класс.  
  
-   `NotInheritable` модификатор — не позволяет использовать класс в качестве базового класса.  
  
-   `MustInherit` модификатор — указывает, что класс предназначен для использования в качестве базового класса. Экземпляры `MustInherit` классов нельзя создать напрямую; они могут создаваться только как базовый класс экземпляров производного класса. (Другие языки программирования, таком как C++ и C#, используется термин *абстрактного класса* для описания такого класса.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Переопределение свойств и методов в производных классах  
 По умолчанию производный класс наследует свойства и методы от своего базового класса. Если наследуемое свойство или метод должен работать по-разному в производном классе, он может быть *переопределении*. То есть можно определить новую реализацию метода в производном классе. Следующие модификаторы используются для управления переопределением свойств и методов.  
  
-   `Overridable` — Позволяет свойства или метода в классе, который будет переопределен в производном классе.  
  
-   `Overrides` Переопределяет `Overridable` свойство или метод, определенный в базовом классе.  
  
-   `NotOverridable` — Не позволяет переопределять свойство или метод в наследующем классе. По умолчанию `Public` методы являются `NotOverridable`.  
  
-   `MustOverride` — Требует, что класс, производный переопределения свойства или метода. Когда `MustOverride` используется ключевое слово, определение метода состоит из только что `Sub`, `Function`, или `Property` инструкции. Другие инструкции не допускаются и в частности есть не `End Sub` или `End Function` инструкции. `MustOverride` методы должны быть объявлены в `MustInherit` классы.  
  
 Предположим, что вы хотите определить классы для обработки платежных ведомостей. Можно определить универсальный `Payroll` класс, содержащий `RunPayroll` метод, который вычисляет заработной платы в неделю. Затем можно использовать `Payroll` как базовый класс для более специализированного `BonusPayroll` класс, который может использоваться при распределении премий между сотрудниками.  
  
 `BonusPayroll` Класс может наследовать и переопределить, `PayEmployee` метод, определенный в базовом `Payroll` класса.  
  
 В следующем примере определяется базовый класс, `Payroll,` и производный класс, `BonusPayroll`, который переопределяет унаследованный метод `PayEmployee`. Процедура `RunPayroll`, создает и затем передает `Payroll` объекта и `BonusPayroll` в функцию `Pay`, который выполняет `PayEmployee` обоих объектов.  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a>MyBase-ключевое слово  
 `MyBase` Ключевое слово ведет себя как объектную переменную, которая ссылается на базовый класс текущего экземпляра класса. `MyBase` часто используется для доступа к членам базового класса, переопределены или скрыты в производном классе. В частности `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
 Например предположим, что вы разрабатываете производного класса, который переопределяет метод, унаследованный от базового класса. Переопределенный метод можно вызвать метод в базовом классе и изменить возвращаемое значение, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 Следующий список описывает ограничения на использование `MyBase`:  
  
-   `MyBase` относится непосредственно к базовому классу и его унаследованные члены. Его нельзя использовать для доступа к `Private` членов в классе.  
  
-   `MyBase` является ключевым словом, а не реальным объектом. `MyBase` нельзя присвоить переменной, передано в процедуры или использовать в `Is` сравнения.  
  
-   Метод, `MyBase` определяет не должны быть определены в непосредственного базового класса; вместо этого могут определяться в косвенно наследуемый базовый класс. Ссылка, с указанием `MyBase` для правильной компиляции некоторого базового класса должен содержать метод, сопоставляющий имена и типы параметров, которые отображаются в вызове.  
  
-   Нельзя использовать `MyBase` для вызова `MustOverride` базовые методы класса.  
  
-   `MyBase` не может использоваться для квалификации самого себя. Таким образом следующий код является недопустимым:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase` не может использоваться в модулях.  
  
-   `MyBase` не может использоваться для доступа к членам базового класса, которые помечены как `Friend` Если базовый класс находится в другой сборке.  
  
 Дополнительные сведения и примеры см. в разделе [как: Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>MyClass-ключевое слово  
 `MyClass` Ключевое слово ведет себя как объектную переменную, которая ссылается на текущий экземпляр класса, первоначально реализован. `MyClass` напоминает `Me`, но каждый метод и свойство вызывать на `MyClass` обрабатывается так, будто метод или свойство [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Таким образом метод или свойство не зависит от переопределения в производном классе.  
  
-   `MyClass` является ключевым словом, а не реальным объектом. `MyClass` нельзя присвоить переменной, передано в процедуры или использовать в `Is` сравнения.  
  
-   `MyClass` ссылается на содержащий класс и его унаследованные члены.  
  
-   `MyClass` можно использовать в качестве квалификатора для `Shared` членов.  
  
-   `MyClass` нельзя использовать внутри `Shared` метод, но может использоваться внутри метода экземпляра, для доступа к общему члену класса.  
  
-   `MyClass` нельзя использовать в стандартных модулях.  
  
-   `MyClass` можно использовать для определения метода, который определен в базовом классе, не имеющего реализации метода этого класса. Эта ссылка имеет то же значение, что `MyBase.` *метод*.  
  
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
  
 Несмотря на то что `derivedClass` переопределяет `testMethod`, `MyClass` ключевое слово в `useMyClass` аннулирует переопределение и компилятор вызов базового класса версию `testMethod`.  
  
## <a name="see-also"></a>См. также
- [Оператор Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
