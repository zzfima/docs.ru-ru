---
title: "Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "операторы объявления, объявленные элементы"
  - "объявления, элементы"
  - "объявленные элементы, сведения об объявленных элементах"
  - "объявленные элементы, создание ссылок"
  - "объявление элементов"
  - "имена элементов, квалификация"
  - "квалификация, имен элементов"
  - "ссылки, объявленные элементы"
  - "создание ссылок на объявленные элементы"
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Cкрыть переменную можно *затенением*, то есть переопределением переменной с тем же именем.  Затенить переменную, которую требуется скрыть, можно двумя способами:  
  
-   **Затенение через область действия.** Можно затенить переменную в области действия путем переопределения ее внутри вложенного блока, внешний блок которого содержит переменную, которую требуется скрыть.  
  
-   **Затенение через наследование.** Если переменная, которую требуется скрыть, определена на уровне класса, то ее можно затенить через наследование путем ее переопределения с помощью ключевого слова [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) в производном классе.  
  
## Два способа сокрытия переменной  
  
#### Чтобы скрыть переменную с помощью затенения в области действия, выполните следующие действия:  
  
1.  Определите область действия переменной, которую требуется скрыть, и подобласть, в которой будет производиться переопределение переменной.  
  
    |Область действия переменной|Допустимые подобласти для ее переопределения|  
    |---------------------------------|--------------------------------------------------|  
    |Модуль|Класс в модуле|  
    |Класс|Подкласс внутри класса<br /><br /> Процедура внутри класса|  
  
     Нельзя переопределить переменную процедуры в блоке, находящемся внутри этой процедуры, например, в конструкции `If`...`End If` или в цикле `For`.  
  
2.  Создайте подобласть, если она еще не существует.  
  
3.  В пределах подобласти напишите оператор [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md), объявляющий затеняемую переменную.  
  
     Когда код внутри подобласти ссылается на имя переменной, компилятор разрешает ссылку с помощью затеняющей переменной.  
  
     В следующем примере показано затенение через область действия, а также обращение, обходящее затенение.  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     В предыдущем примере переменная `num` объявляется как на уровне модуля, так и на уровне процедуры \(в процедуре `show`\).  Локальная переменная `num` скрывает переменную уровня модуля `num` в `show`, поэтому локальная переменная принимает значение 2.  Однако локальной переменной для скрытия `num` в процедуре `useModuleLevelNum` нет.  Поэтому `useModuleLevelNum` присваивает значение 1 переменной на уровне модуля.  
  
     Вызов `MsgBox` внутри `show` обходит затеняющий механизм путем уточнения `num` с помощью имени модуля.  Поэтому в нем отображается переменная уровня модуля, а не локальная переменная.  
  
#### Чтобы скрыть переменную с помощью наследования, выполните следующие действия:  
  
1.  Убедитесь, что переменная, которую требуется скрыть, объявлена в классе и на уровне класса \(вне всех процедур\).  В противном случае скрыть ее через наследование нельзя.  
  
2.  Определите класс, производный от класса переменной, если такой еще не существует.  
  
3.  Внутри производного класса напишите оператор `Dim`, объявляющий переменную.  Включите в объявление ключевое слово [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md).  
  
     Если код в производном классе ссылается на имя переменной, компилятор разрешает ссылку с помощью созданной таким образом переменной.  
  
     В следующем примере показано затенение через наследование.  Производятся два обращения: одно — к затеняющей переменной, другое же обходит затенение.  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     В этом примере переменная `shadowString`, объявленная в базовом классе, скрывается в производном классе.  Процедура `showStrings` в производном классе отображает версию затеняющую версию строки, если имя `shadowString` не квалифицировано полностью.  Затем затененная версия отображается, если `shadowString` определяется с помощью ключевого слова `MyBase`.  
  
## Отказоустойчивость  
 Затенение представляет несколько версий переменной с тем же именем.  Если оператор кода ссылается на имя переменной, то версия переменной, на которую компилятор разрешает ссылку, зависит от таких факторов, как расположение оператора кода и наличие строки с именем квалификации.  Это может повысить риск обращения к непредусмотренной версии затеняемой переменной.  Снизить этот риск можно путем полной квалификации всех обращений к затеняемой переменной.  
  
## См. также  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Различия между сокрытием и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [Практическое руководство. Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Практическое руководство. Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)