---
title: Ссылки на объявленные элементы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 18f9920891e35517efe7adcfd4c03e03ac771478
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="references-to-declared-elements-visual-basic"></a>Ссылки на объявленные элементы (Visual Basic)
Когда код ссылается на объявленный элемент, компилятор Visual Basic соответствует имени в ссылке соответствующему объявлению с тем же именем. Если с тем же именем объявлено несколько элементов, можно управлять, какой из этих элементов — для ссылки на *соответствующие* его имя.  
  
 Компилятор пытается сопоставить ссылку имени с объявлением с *узкой областью*. Это означает, что он начинается с кода, делая ссылку и работая через последовательные уровни содержащих элементов.  
  
 В следующем примере ссылки на две переменные с тем же именем. В примере объявляются две переменные, каждая с именем `totalCount`, на разных уровнях области в модуле `container`. Если процедура `showCount` отображает `totalCount` без указания полного имени, компилятор Visual Basic разрешает ссылку на объявление с самой узкой областью, а именно, локальное объявление внутри `showCount`. При уточнении `totalCount` с содержащим модулем `container`, компилятор разрешает ссылку на объявление с более широкой областью.  
  
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
 Если требуется переопределить этот процесс поиска и укажите имя, объявленное в более широкой области необходимо *квалифицировать* имя содержащим элементом более широкой области. В некоторых случаях может потребоваться уточнить содержащего его элемента.  
  
 Уточнение имени означает предшествует ей в исходном операторе сведения, которые определяют, где определен целевой элемент. Эта информация называется *уточняющей строки*. Он может включать один или несколько пространств имен и модуля, класса или структуры.  
  
 Уточняющей строки должна однозначно указать модуль, класс или структура, содержащая целевой элемент. Контейнер, в свою очередь может находиться в другом вмещающем элементе, обычно в пространстве имен. Может потребоваться включить несколько элементов в уточняющей строке.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Для доступа к объявленного элемента, указав его имя  
  
1.  Определите расположение, в котором определен элемент. Это может включать пространство имен или даже иерархии пространств имен. В пространстве имен самого низкого уровня элемент должен состоять из модуля, класса или структуры.  
  
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
  
2.  Определите классификационный путь на основе расположения целевого элемента. Запустить с самого верхнего уровня пространства имен, перейдите к пространству имен самого низкого уровня и заканчиваться модуля, класса или структуры, содержащей целевой элемент. Каждый элемент в путь должен содержать элемент, следующий за ним.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Подготовка уточняющей строки для целевого элемента. Поместите точку (`.`) после каждого элемента в пути. Приложение должно иметь доступ к каждому элементу уточняющей строки.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Напишите выражение или оператор присваивания, ссылающийся на целевой элемент обычным способом.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Перед именем целевого элемента уточняющей строки. Имя должно следовать сразу за период (`.`), который следует за модуля, класса или структуры, содержащей элемент.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Компилятор использует уточняющей строки, чтобы найти точное, однозначное объявление, к которому может сопоставить ссылку на целевой элемент.  
  
 Может также потребоваться уточнять ссылки на имена, если приложение имеет доступ к более чем один элемент программирования, который имеет то же имя. Например <xref:System.Windows.Forms> и <xref:System.Web.UI.WebControls> пространства имен оба содержат `Label` класса (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Если приложение использует оба или определяет собственный `Label` класса, необходимо различать разные `Label` объектов. Включите пространство имен или псевдоним в объявлении переменной. В следующем примере используется псевдоним импорта.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Члены других содержащих элементов  
 При использовании не совместно члена другого класса или структуры, нужно сначала уточнить имя члена с помощью переменной или выражение, которое указывает на экземпляр класса или структуры. В следующем примере `demoClass` является экземпляром класса с именем `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Нельзя использовать имя самого класса для уточнения члена, который не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Сначала необходимо создать экземпляр в переменной объекта (в данном случае `demoClass`) и затем ссылаться на него, используя имя переменной.  
  
 Если класс или структура имеет `Shared` член, можно уточнить этот член с именем класса или структуры, переменной или выражение, которое указывает на экземпляр.  
  
 Модуль не имеет любой отдельных экземпляров, и все его члены являются `Shared` по умолчанию. Таким образом уточняется член модуля имя модуля.  
  
 В следующем примере квалифицированные ссылки на процедуры члена модуля. В примере объявляются два `Sub` процедуры, и именованные `perform`, в различных модулях в проекте. Каждая из них можно указывать без уточнения внутри собственного модуля, но должен быть определен, если имеются ссылки в других местах. Так как последняя ссылка в `module3` не соответствует требованиям `perform`, компилятор не может разрешить эту ссылку.  
  
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
 Для использования [открытый](../../../../visual-basic/language-reference/modifiers/public.md) элементов, определенных в другом проекте, необходимо сначала установить *ссылки* для этого проекта сборки или библиотеки типов. Чтобы задать ссылку, щелкните **добавить ссылку** на **проекта** меню или используйте [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр командной строки компилятора.  
  
 Например, можно использовать объектную модель XML из [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Если задать ссылку на <xref:System.Xml> пространства имен, можно объявить и использовать любой из его классы, такие как <xref:System.Xml.XmlDocument>. В следующем примере используется <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Импорт содержащих элементов  
 Можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для *импорта* пространства имен, содержащих модули или классы, которые вы хотите использовать. Это позволяет обращаться к элементам, определенным в импортированном пространстве имен без использования полных имен. Следующий пример перезаписывает предыдущий пример для импорта <xref:System.Xml> пространства имен.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Кроме того `Imports` можно определить оператор *псевдоним импорта* для каждого импортируемого пространства имен. Это можно сделать исходный код короче и удобнее для чтения. Следующий пример перезаписывает предыдущий пример для использования `xD` в качестве псевдонима для <xref:System.Xml> пространства имен.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 `Imports` Инструкция не делает элементы из других проектов доступными для приложения. То есть вместо настройки ссылки не имеют. Импорт пространства имен просто освобождает от необходимости уточнения имен, определенных в этом пространстве имен.  
  
 Можно также использовать `Imports` инструкции для импорта модулей, классов, структур и перечислений. Затем можно использовать члены импортированных элементов без указания полного имени. Тем не менее всегда необходимо предварять собственным членам классов и структур с помощью переменной или выражение, результатом которого экземпляр этого класса или структуры.  
  
## <a name="naming-guidelines"></a>Правила именования  
 При определении двух или более программным элементам, которые имеют одинаковое имя, *неоднозначность имен* может возникнуть при этом компилятор пытается разрешить ссылку на это имя. Если более одного определения в области, или если определение не находится в области, ссылка является неразрешимой. Пример см. в разделе «Пример уточненной ссылки» на этой странице справки.  
  
 Неоднозначность имен можно избежать, задав все элементы, уникальные имена. Затем можно сделать ссылку на любой элемент без уточнения его имени пространства имен, модуля или класса. Кроме того, можно сократить вероятность случайной ссылки на неправильный элемент.  
  
## <a name="shadowing"></a>Затенение  
 Если два программных элемента имеют то же имя, один из них может скрыть, или *тени*, другой. Скрытый элемент недоступен для обращения. Вместо этого когда ваш код использует имя скрытый элемент, компилятор Visual Basic сопоставляется с скрывающий элемент. Более подробное описание с примерами см. в разделе [сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>См. также  
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)
