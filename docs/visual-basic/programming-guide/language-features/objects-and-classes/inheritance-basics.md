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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 58aee9f8c348eb06daec2b8c9e332f3f2775bcb6
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="inheritance-basics-visual-basic"></a>Основы наследования (Visual Basic)
`Inherits` Инструкция используется для объявления нового класса, называемого *производный класс*, основанный на существующем классе, называемом *базового класса*. Производные классы наследуют и могут расширять свойства, методы, события, поля и константы, определенные в базовом классе. В следующем разделе описаны некоторые правила наследования и модификаторы, которые можно использовать для изменения способа классы наследуют или наследования:  
  
-   По умолчанию все классы могут наследоваться в том случае, если помечено `NotInheritable` ключевое слово. Классы могут наследовать от других классов в проекте или из классов других сборок, на которые ссылается проект.  
  
-   В отличие от языков, которые позволяют множественное наследование [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] позволяет только единичное наследование в классах; то есть производные классы могут иметь только один базовый класс. Хотя в классах не допускается множественное наследование, классы могут реализовывать несколько интерфейсов, которые способны эффективно выполнять те же самые задачи.  
  
-   Чтобы предотвратить предоставление элементов с ограничениями в базовом классе, тип доступа производного класса должен быть равен или больше ограничений, чем ее базовый класс. Например `Public` класс не может наследовать `Friend` или `Private` класс и `Friend` класс не может наследовать `Private` класса.  
  
## <a name="inheritance-modifiers"></a>Модификаторы наследования  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]вводит следующие инструкции на уровне класса и модификаторы для поддержки наследования:  
  
-   `Inherits`инструкции — определяет базовый класс.  
  
-   `NotInheritable`модификатор — не позволяет использовать класс в качестве базового класса.  
  
-   `MustInherit`модификатор — указывает, что класс предназначен для использования только в качестве базового класса. Экземпляры `MustInherit` классы нельзя создать напрямую, они могут быть созданы только как базовый класс экземпляров производного класса. (Другие языки программирования, такие как C++ и C#, использовать термин *абстрактного класса* для описания такого класса.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Переопределение свойств и методов в производных классах  
 По умолчанию производный класс наследует свойства и методы от своего базового класса. Если унаследованное свойство или метод должен вести себя по-разному в производном классе может быть *переопределении*. То есть можно определить новую реализацию метода в производном классе. Следующие модификаторы используются для управления переопределением свойств и методов.  
  
-   `Overridable`— Позволяет свойство или метод в классе для переопределения в производном классе.  
  
-   `Overrides`Переопределяет `Overridable` свойство или метод, определенный в базовом классе.  
  
-   `NotOverridable`— Не позволяет переопределять свойство или метод в наследующем классе. По умолчанию `Public` методы являются `NotOverridable`.  
  
-   `MustOverride`— Требует, что производного класса переопределяют свойства или метода. Когда `MustOverride` используется ключевое слово, определение метода состоит из только что `Sub`, `Function`, или `Property` инструкции. Другие инструкции не допускаются и в частности является не `End Sub` или `End Function` инструкции. `MustOverride`методы должны быть объявлены в `MustInherit` классы.  
  
 Предположим, что необходимо определить классы для обработки платежных ведомостей. Можно определить универсальный `Payroll` класс, содержащий `RunPayroll` метод, который рассчитывает платежную неделю. Затем можно использовать `Payroll` в качестве базового класса для более специализированного `BonusPayroll` класс, который может использоваться при распределении премий между сотрудниками.  
  
 `BonusPayroll` Класс может наследовать и переопределять `PayEmployee` метод, определенный в базовом `Payroll` класса.  
  
 В следующем примере определяется базовый класс, `Payroll,` и производный класс `BonusPayroll`, который переопределяет унаследованный метод `PayEmployee`. Процедура `RunPayroll`, создает и затем передает `Payroll` объекта и `BonusPayroll` в функцию `Pay`, который выполняет `PayEmployee` обоих объектов.  
  
 [!code-vb[VbVbalrOOP&#28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>MyBase-ключевое слово  
 `MyBase` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра класса. `MyBase`часто используется для доступа к членам базового класса, которые переопределены или скрыты в производном классе. В частности `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
 Например предположим, что разрабатывается производный класс, который переопределяет метод, унаследованный от базового класса. Переопределенный метод можно вызвать метод в базовом классе и изменить возвращаемое значение, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP&#109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 Следующий список описывает ограничения на использование `MyBase`:  
  
-   `MyBase`относится непосредственно к базовому классу и его унаследованным членам. Он не может использоваться для доступа к `Private` членов в классе.  
  
-   `MyBase`является зарезервированным словом, а не реальным объектом. `MyBase`нельзя присвоить переменной, передаваемой процедурам или использовать в `Is` сравнения.  
  
-   Метод, `MyBase` определяет не обязательно должен быть определен в непосредственно к базовому классу; вместо этого можно задать в косвенно наследуемый базовый класс. Ссылка, с указанием `MyBase` для правильной компиляции некоторых базовых классов должен содержать метод, сопоставляющий имена и типы параметров, появляющихся в вызове.  
  
-   Нельзя использовать `MyBase` для вызова `MustOverride` базовые методы класса.  
  
-   `MyBase`не может использоваться для квалификации самого себя. Таким образом следующий код является недопустимым:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase`не может использоваться в модулях.  
  
-   `MyBase`не может использоваться для доступа к членам базового класса, помеченные как `Friend` , если базовый класс находится в другой сборке.  
  
 Дополнительные сведения и еще один пример см. в разделе [Практическое руководство: доступ к переменной скрыты с помощью производного класса](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>MyClass-ключевое слово  
 `MyClass` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован. `MyClass`напоминает `Me`, но каждый метод и свойство вызвать `MyClass` рассматривается, как будто метод или свойство [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Таким образом метод или свойство не изменяется путем переопределения в производном классе.  
  
-   `MyClass`является зарезервированным словом, а не реальным объектом. `MyClass`нельзя присвоить переменной, передаваемой процедурам или использовать в `Is` сравнения.  
  
-   `MyClass`ссылается на содержащий класс и его унаследованные члены.  
  
-   `MyClass`может использоваться в качестве квалификатора для `Shared` члены.  
  
-   `MyClass`нельзя использовать внутри `Shared` метода, но можно использовать внутри метода экземпляра для доступа к общему члену класса.  
  
-   `MyClass`не может использоваться в стандартных модулях.  
  
-   `MyClass`можно использовать для квалификации метода, определенного в базовом классе и не имеющего реализации метода этого класса. Эта ссылка имеет то же значение, что `MyBase.` *метод*.  
  
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
  
 Несмотря на то что `derivedClass` переопределяет `testMethod`, `MyClass` ключевое слово в `useMyClass` аннулирует переопределение и компилятор вызов версию базового класса `testMethod`.  
  
## <a name="see-also"></a>См. также  
 [Оператор Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

