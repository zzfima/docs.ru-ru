---
title: Ссылки на объявленные элементы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 0fca02ab2dcb507c1129f18f31a25c7809fc9710
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296710"
---
# <a name="references-to-declared-elements-visual-basic"></a>Ссылки на объявленные элементы (Visual Basic)
Когда код ссылается на объявленный элемент, компилятор Visual Basic совпадает с именем в ссылке соответствующий объявлению. Если более чем один элемент объявлен с тем же именем, вы можете контролировать, какие из этих элементов — на них ссылается *удовлетворяющим требованиям* его имя.  
  
 Компилятор пытается сопоставить ссылку имени с объявлением с *наиболее узкой области*. Это означает, что он начинается с кода, делая ссылку и работая через последовательные уровни, содержащего элементы.  
  
 Пример ссылки на две переменные с тем же именем. В примере объявляются две переменные, каждая с именем `totalCount`, на разных уровнях области в модуле `container`. Когда процедура `showCount` отображает `totalCount` без квалификации, компилятор Visual Basic разрешает ссылку на объявление с самой узкой областью, а именно: локальное объявление внутри `showCount`. При уточнении `totalCount` с содержащим модулем `container`, компилятор разрешает ссылку на объявление с более широкой областью.  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a>Уточнение имени элемента  
 Если вы хотите переопределить этот процесс поиска и укажите имя, объявленное в более широкую область необходимо *квалифицировать* имя с содержащим элементом более широкой области. В некоторых случаях может потребоваться уточнять содержащий элемент.  
  
 Уточнение имени означает, что предшествует ей в исходном операторе сведения, которые определяют, где определен целевой элемент. Эта информация называется *уточняющей строке*. Она может включать одно или несколько пространств имен и модуля, класса или структуры.  
  
 Строка квалификации должна однозначно указать модуль, класс или структура, содержащая целевой элемент. Контейнер, в свою очередь могут находиться в другой содержащий элемент, обычно в пространстве имен. Может потребоваться включить несколько элементов в уточняющей строке.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Для доступа к объявленного элемента, указав его имя  
  
1. Определите расположение, в котором был определен элемент. Это может включать пространство имен или даже иерархии пространств имен. В пространстве имен самого низкого уровня элемент должен содержаться в модуля, класса или структуры.  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. Определите путь квалификации, в зависимости от расположения целевого элемента. Начнем с самого верхнего уровня пространства имен, перейдите к пространству имен самого низкого уровня и заканчиваться модуль, класс или структура, содержащая целевой элемент. Каждый элемент в пути должен содержать элемент, следующий за ним.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. Подготовка уточняющей строки для целевого элемента. Поместите точку (`.`) после каждого элемента в пути. Приложение должно иметь доступ к каждому элементу уточняющей строки.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. Напишите выражение или оператор присваивания, ссылающийся на целевой элемент обычным способом.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. Перед именем целевой элемент в уточняющей строке. Имя должно следовать сразу за период (`.`), который следует за модуля, класса или структуры, которая содержит элемент.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. Компилятор использует уточняющей строке, чтобы найти точное, однозначное объявление, к которому она может соответствовать ссылку на целевой элемент.  
  
 Кроме того, может потребоваться уточнять ссылки на имена, если приложение имеет доступ к более одного элемента программирования, который имеет то же имя. Например <xref:System.Windows.Forms> и <xref:System.Web.UI.WebControls> пространства имен оба содержат `Label` класс (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Если приложение использует оба или определяет собственный `Label` класса, необходимо различать разные `Label` объектов. Включите пространство имен или псевдоним в объявлении переменной. В следующем примере используется псевдоним импорта.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Членами других элементов с содержимым  
 При использовании члену другого класса или структуры, сначала необходимо уточнить имя члена с помощью переменной или выражение, которое указывает на экземпляр класса или структуры. В следующем примере `demoClass` является экземпляром класса с именем `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Нельзя использовать имя самого класса для уточнения члена, не [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Во-первых, необходимо создать экземпляр в переменной объекта (в данном случае `demoClass`) и затем ссылаться на него по имени этой переменной.  
  
 Если класс или структура имеет `Shared` член, можно уточнить этот член с именем класса или структуры, переменной или выражение, которое указывает на экземпляр.  
  
 Модуль имеет все отдельные экземпляры, и все его члены являются `Shared` по умолчанию. Таким образом вы уточнения члена модуля с именем модуля.  
  
 В следующем примере полные ссылки на процедуры члена модуля. В этом примере объявляется два `Sub` процедуры, и именованные `perform`, в разных модулях в проекте. Каждая из них можно указывать без уточнения внутри свой собственный модуль, но должен быть определен, если ссылка в других местах. Так как последняя ссылка в `module3` неприменима `perform`, компилятор не может разрешить эту ссылку.  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a>Ссылки на проекты  
 Для использования [открытый](../../../../visual-basic/language-reference/modifiers/public.md) элементов, определенных в другом проекте, необходимо сначала установить *ссылку* для этого проекта сборки или библиотеки типов. Чтобы задать ссылку, щелкните **добавить ссылку** на **проекта** меню или используйте [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр командной строки компилятора.  
  
 Например, можно использовать объектную модель XML [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Если задать ссылку на <xref:System.Xml> пространства имен, можно объявить и использовать любой из его классы, такие как <xref:System.Xml.XmlDocument>. В следующем примере используется <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Импорт элементов  
 Можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для *импорта* пространства имен, содержащих модули или классы, которые вы хотите использовать. Это позволяет ссылаться на элементы, определенные в импортированное пространство имен без полных имен. Следующий пример перезаписывает предыдущий пример для импорта <xref:System.Xml> пространства имен.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Кроме того `Imports` можно определить оператор *псевдоним импорта* для каждого импортируемого пространства имен. Это может сделать исходный код короче и удобнее для чтения. Следующий пример перезаписывает предыдущий пример для использования `xD` в качестве псевдонима для <xref:System.Xml> пространства имен.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 `Imports` Инструкция не выполняет элементы из других проектов доступными для приложения. То есть он не замещать ссылку. Импорт пространства имен просто удаляет требование для уточнения имен, определенных в этом пространстве имен.  
  
 Можно также использовать `Imports` для импорта модулей, классов, структур и перечислений. Затем можно использовать члены импортированных элементов без указания полного имени. Тем не менее всегда необходимо определять членам экземпляров классов и структур с переменной или выражение, значением которого является экземпляр класса или структуры.  
  
## <a name="naming-guidelines"></a>Правила именования  
 При определении два или несколько программных элементов, которые имеют одинаковое имя, *неоднозначность имен* может привести к Если компилятор пытается разрешить ссылку на это имя. Если более одного определения находится в области, или если определение не находится в области, ссылка является неразрешимой. Например см. в разделе «Пример уточненной ссылки» на этой странице справки.  
  
 Неоднозначность имен можно избежать, предоставляя уникальные имена всех элементов. Затем можно создать ссылку к любому элементу без уточнения его именем пространства имен, модуля или класса. Вы также снизить вероятность случайной ссылки на неправильный элемент.  
  
## <a name="shadowing"></a>Удаленное управление  
 Если два программных элемента имеют одинаковые имена, один из них может скрыть, или *тени*, другой. Скрытый элемент недоступен для обращения. Вместо этого когда код использует затененного имени элемента, компилятор Visual Basic разрешает его скрывающий элемент. Более подробное описание с примерами, см. в разделе [сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>См. также

- [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Управление свойствами проекта и решения](/visualstudio/ide/managing-project-and-solution-properties)
- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
