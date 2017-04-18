---
title: "Ссылки на объявленные элементы (Visual Basic) | Документы Microsoft"
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
- declared elements
- references, declared elements
- qualified names
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48a04f81075accc073b0d1f5b7a61006bef807ae
ms.lasthandoff: 03/13/2017

---
# <a name="references-to-declared-elements-visual-basic"></a>Ссылки на объявленные элементы (Visual Basic)
Когда код ссылается на объявленный элемент [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятора соответствует имени в ссылке соответствующему объявлению этого имени. Если более чем один элемент объявлен с тем же именем, можно выбрать, какие из этих элементов должен ссылаться на *соответствующая* его имя.  
  
 Компилятор пытается сопоставить ссылку имени с объявлением с *узкой области*. Это означает, что он начинается с кода, делая ссылку и работая через последовательные уровни содержащих элементов.  
  
 В следующем примере показаны ссылки на две переменные с тем же именем. В примере объявляются две переменные, каждая с именем `totalCount`, на различных уровнях области в модуле `container`. Если процедура `showCount` отображает `totalCount` без квалификации, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор разрешает ссылку на объявление с самой узкой областью, а именно, локальное объявление внутри `showCount`. При уточнении `totalCount` с содержащим модулем `container`, компилятор разрешает ссылку на объявление с более широкой областью.  
  
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
 Если требуется переопределить этот процесс поиска и задать имя, объявленное в более широкой области, необходимо *уточнения* имя содержащим элементом более широкой области. В некоторых случаях может потребоваться уточнять содержащий элемент.  
  
 Уточнение имени означает предшествующего ему в исходном операторе сведения, определяющие, где определен целевой элемент. Эта информация называется *уточняющую строку*. Она может включать одно или несколько пространств имен и модуля, класса или структуры.  
  
 Строка квалификации должна однозначно указать модуль, класс или структура, содержащая целевой элемент. Контейнер, в свою очередь может находиться в другом вмещающем элементе, обычно в пространстве имен. Может потребоваться включить несколько элементов в уточняющую строку.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Чтобы получить доступ к объявленным элементом, указав его имя  
  
1.  Определите расположение, в котором был определен элемент. Это может включать пространство имен или даже иерархии пространств имен. В пространстве имен нижнего уровня элемент должен содержаться в модуля, класса или структуры.  
  
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
  
2.  Определите классификационный путь на основе расположения целевого элемента. Начнем с пространство имен верхнего уровня, перейдите к пространству имен самого низкого уровня и заканчиваться модуля, класса или структуры, содержащей целевой элемент. Каждый элемент пути должен содержать элемент, следующий за ним.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Подготовка уточняющей строки для целевого элемента. Поместите точку (`.`) после каждого элемента пути. Приложение должно иметь доступ к каждому элементу уточняющей строки.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Напишите выражение или оператор присваивания, ссылающийся на конечный элемент обычным образом.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Перед именем целевого элемента уточняющую строку. Имя должна стоять точка (`.`), который следует за модуля, класса или структуры, которая содержит элемент.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Компилятор использует уточняющую строку, чтобы найти точное, однозначное объявление, к которому может сопоставить ссылку на целевой элемент.  
  
 Может также потребоваться уточнять ссылки на имена, если приложение имеет доступ к более чем один элемент программирования, который имеет то же имя. Например <xref:System.Windows.Forms>и <xref:System.Web.UI.WebControls>пространства имен содержат `Label` класса (<xref:System.Windows.Forms.Label?displayProperty=fullName> и <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</xref:System.Web.UI.WebControls.Label?displayProperty=fullName> </xref:System.Windows.Forms.Label?displayProperty=fullName> </xref:System.Web.UI.WebControls> </xref:System.Windows.Forms> Если приложение использует оба или определяет собственный `Label` класса, необходимо различать разные `Label` объектов. Включите пространство имен или псевдоним в объявлении переменной. В следующем примере псевдоним импорта.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Члены других содержащих элементов  
 При использовании не совместно членом другого класса или структуры нужно сначала уточнить имя члена с помощью переменной или выражения, указывающего на экземпляр класса или структуры. В следующем примере `demoClass` представляет собой экземпляр класса с именем `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Нельзя использовать имя самого класса для уточнения члена, который не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Необходимо сначала создать экземпляр в переменной объекта (в данном случае `demoClass`) и затем сослаться на него, используя имя переменной.  
  
 Если класс или структура имеет `Shared` член, уточнить этот член именем класса или структуры, переменной или выражение, которое указывает на экземпляр.  
  
 Модуль имеет любой отдельных экземпляров, и все его члены являются `Shared` по умолчанию. Таким образом уточняется член модуля с именем модуля.  
  
 В следующем примере полные ссылки на процедуры члена модуля. В примере объявляются две `Sub` процедуры, обе с именем `perform`, в разных модулях проекта. Каждая из них можно указывать без уточнения внутри собственный модуль, но должно быть уточнено обращения из других мест. Так как последняя ссылка в `module3` неприменима `perform`, компилятор не может разрешить эту ссылку.  
  
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
 Для использования [открытый](../../../../visual-basic/language-reference/modifiers/public.md) элементов, определенных в другом проекте, необходимо сначала установить *ссылки* для этого проекта сборку или библиотеку типов. Чтобы установить ссылку, нажмите кнопку **добавить ссылку** на **проекта** меню или используйте [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр командной строки компилятора.  
  
 Например, можно использовать объектную модель XML из [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Если задать ссылку на <xref:System.Xml>пространства имен, можно объявить и использовать все его классы, такие как <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> </xref:System.Xml> В следующем примере используется <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Импорт содержащих элементов  
 Можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для *импорта* пространства имен, содержащих модули или классы, которые вы хотите использовать. Это позволяет ссылаться на элементы, определенные в импортированном пространстве имен без полных имен. Следующий пример перезаписывает предыдущий пример для импорта <xref:System.Xml>имен.</xref:System.Xml>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Кроме того `Imports` можно определить оператор *псевдоним импорта* для каждого импортируемого пространства имен. Это может сделать исходный код короче и удобнее для чтения. Следующий пример перезаписывает предыдущий пример для использования `xD` в качестве псевдонима для <xref:System.Xml>имен.</xref:System.Xml>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 `Imports` Инструкция не делает элементы из других проектов доступными для приложения. То есть он не замещать ссылку. Импорт пространства имен просто освобождает от необходимости уточнения имен, определенных в этом пространстве имен.  
  
 Можно также использовать `Imports` для импорта модулей, классов, структур и перечислений. Затем можно использовать члены импортированных элементов без уточнения. Тем не менее всегда необходимо предварять собственным членам классов и структур с помощью переменной или выражение, результатом которого является экземпляром класса или структуры.  
  
## <a name="naming-guidelines"></a>Правила именования  
 При определении двух или более элементов программирования, которые имеют одинаковое имя, *неоднозначность имен* может привести к когда компилятор пытается разрешить ссылку на это имя. Если более одного определения находится в области, или если определение отсутствует в области, ссылка является неразрешимой. Пример в разделе «Полное пример ссылки» на этой странице справки.  
  
 Неоднозначность имен можно избежать, присвоив уникальные имена всех элементов. Затем можно сделать ссылку на любой элемент без уточнения его имени пространства имен, модуля или класса. Можно также снизить вероятность случайной ссылки на неправильный элемент.  
  
## <a name="shadowing"></a>Затенение  
 Если два программных элемента имеют общее имя, один из них может скрыть, или *тени*, другой. Затененный элемент недоступен для обращения. Вместо этого в том случае, если ваш код использует затененного имени элемента, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор разрешает его переопределяющий элемент. Более подробное описание с примерами см. в разделе [сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>См. также  
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [NIB Практическое руководство: изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)
