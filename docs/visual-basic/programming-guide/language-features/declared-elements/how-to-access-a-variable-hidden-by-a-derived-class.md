---
title: "Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "базовые классы, доступ к элементам"
  - "объявленные элементы, создание ссылок"
  - "имена элементов, квалификация"
  - "квалификация, имен элементов"
  - "ссылки, объявленные элементы"
  - "переменные [Visual Basic], доступ к скрытым"
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Когда код в производном классе обращается к переменной, компилятор обычно разрешает ссылку на ближайшую доступную версию, \(т.е. доступную версию, отличающуюся от обращающегося класса на минимальное количество производных действий\).  Если переменная определена в производном классе, код обычно обращается к этому определению.  
  
 Если переменная производного класса затеняет переменную в базовом классе, она скрывает версию базового класса.  Однако можно получить доступ к переменной базового класса путем определения ее с помощью ключевого слова `MyBase`.  
  
### Чтобы обратиться к переменной базового класса, скрытой производным классом  
  
-   В выражении или операторе присваивания укажите перед именем переменной ключевое слово `MyBase` и точку \(`.`\).  
  
     Компилятор разрешает ссылку на версию базового класса переменной.  
  
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
  
     В этом примере переменная `shadowString`, объявленная в базовом классе, скрывается в производном классе.  Процедура `showStrings` в производном классе отображает версию затеняющую версию строки, если имя `shadowString` не квалифицировано полностью.  Затем затененная версия отображается, если `shadowString` определяется с помощью ключевого слова `MyBase` .  
  
## Отказоустойчивость  
 Чтобы понизить риск ссылки на неправильную версию затененной переменной, можно полностью определить все ссылки на затененную переменную.  Затенение представляет несколько версий переменной с тем же именем.  Если оператор кода ссылается на имя переменной, то версия переменной, на которую компилятор разрешает ссылку, зависит от таких факторов, как расположение оператора кода и наличие строки с именем квалификации.  Это может увеличить риск ссылки на неправильную версию переменной.  
  
## См. также  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Различия между сокрытием и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [Практическое руководство. Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)