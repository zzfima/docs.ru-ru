---
title: "Практическое руководство. Сокрытие наследуемой переменной (Visual Basic) | Microsoft Docs"
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
  - "объявленные элементы, сведения об объявленных элементах"
  - "объявленные элементы, создание ссылок"
  - "имена элементов, квалификация"
  - "квалификация, имен элементов"
  - "ссылки, объявленные элементы"
  - "создание ссылок на объявленные элементы"
  - "переменные [Visual Basic], скрытие наследуемых"
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Практическое руководство. Сокрытие наследуемой переменной (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Производный класс наследует все определения его базового класса.  Если необходимо определить переменную с тем же именем, что у элемента базового класса, можно скрыть или *затенить* элемент базового класса при определении переменной в производном классе.  Если это сделать, то код в производном классе получает доступ к переменной, если явно не обходится механизм затенения.  
  
 Другой причиной, по которой может потребоваться скрыть наследуемую переменную, является защита версии базового класса.  Базовый класс может претерпеть изменения, которые отразятся на наследуемом элементе.  В этом случае модификатор `Shadows` принудительно указывает на переменную из производного класса, вместо элемента базового класса.  
  
### Скрытие наследуемой переменной  
  
1.  Убедитесь, что переменная, которую требуется скрыть, объявлена на уровне класса \(вне любой процедуры\).  В противном случае ее скрывать необязательно.  
  
2.  Внутри производного класса используйте [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной.  Используйте имя, совпадающее с именем наследуемой переменной.  
  
3.  Включите в объявление ключевое слово [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md).  
  
     Если код в производном классе ссылается на имя переменной, компилятор разрешает ссылку с помощью созданной таким образом переменной.  
  
     В следующем примере показано скрытие \(затенение\) наследуемой переменной.  
  
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
  
     В этом примере переменная `shadowString`, объявленная в базовом классе, скрывается в производном классе.  Процедура `showStrings` в производном классе отображает версию затеняющую версию строки, если имя `shadowString` не квалифицировано полностью.  Затем отображается затененная версия, когда `shadowString` квалифицируется ключевым словом `MyBase`.  
  
## Отказоустойчивость  
 Затенение представляет несколько версий переменной с тем же именем.  Если оператор кода ссылается на имя переменной, то версия переменной, на которую компилятор разрешает ссылку, зависит от таких факторов, как расположение оператора кода и наличие строки с именем квалификации.  Это может повысить риск обращения к непредусмотренной версии затеняемой переменной.  Снизить этот риск можно путем полной квалификации всех обращений к затеняемой переменной.  
  
## См. также  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Различия между сокрытием и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [Практическое руководство. Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)