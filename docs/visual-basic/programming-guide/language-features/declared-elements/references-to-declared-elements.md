---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: a6477a9f0abaf8eb9176f4f6ab2a920af6c8f500
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345299"
---
# <a name="references-to-declared-elements-visual-basic"></a>Ссылки на объявленные элементы (Visual Basic)
Когда код ссылается на объявленный элемент, компилятор Visual Basic сопоставляет имя в ссылке с соответствующим объявлением этого имени. Если с одним и тем же именем объявлено несколько элементов, можно указать, к какому из этих элементов следует обращаться с помощью *уточнения* его имени.  
  
 Компилятор пытается сопоставить ссылку на имя с объявлением имени с *самой короткой областью*. Это означает, что он начинается с кода, который делает ссылку и работает наружу через последовательные уровни содержащихся элементов.  
  
 В следующем примере показаны ссылки на две переменные с одинаковым именем. В примере объявляются две переменные, каждая с именем `totalCount`, на разных уровнях области в `container`модуля. Если процедура `showCount` отображает `totalCount` без квалификации, компилятор Visual Basic разрешает ссылку на объявление с самой узкий областью, а именно локальное объявление в `showCount`. Когда он определяет `totalCount`, содержащий `container`модуля, компилятор разрешает ссылку на объявление с более широкой областью.  
  
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
 Если вы хотите переопределить этот процесс поиска и указать имя, объявленное в более широкой области видимости, необходимо *уточнить* имя с помощью содержащего его элемента из более широкой области. В некоторых случаях может также потребоваться квалификация содержащего его элемента.  
  
 Уточнение имени означает, что перед ним в исходном операторе содержатся сведения, указывающие, где определен целевой элемент. Эти сведения называются *уточняющей строкой*. Он может включать одно или несколько пространств имен, а также модуль, класс или структуру.  
  
 Уточняющая строка должна однозначно указывать модуль, класс или структуру, содержащую целевой элемент. Контейнер может находиться в другом содержащем его элементе, обычно в пространстве имен. Может потребоваться включить несколько элементов, содержащихся в уточняющей строке.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Получение доступа к объявленному элементу с помощью уточнения его имени  
  
1. Определите расположение, в котором был определен элемент. Это может быть пространство имен или даже иерархия пространств имен. В пространстве имен самого низкого уровня элемент должен содержаться в модуле, классе или структуре.  
  
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
  
2. Определите классификационный путь на основе расположения целевого элемента. Начните с пространства имен наивысшего уровня, перейдите к пространству имен самого низкого уровня и завершите работу с модулем, классом или структурой, содержащей целевой элемент. Каждый элемент в пути должен содержать элемент, следующий за ним.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. Подготовьте уточняющую строку для целевого элемента. Поместите точку (`.`) после каждого элемента в пути. Приложение должно иметь доступ к каждому элементу в уточняющей строке.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. Напишите выражение или оператор присваивания, ссылающийся на целевой элемент обычным способом.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. Перед именем целевого элемента введите уточняющую строку. Имя должно следовать за точкой (`.`) после модуля, класса или структуры, содержащей элемент.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. Компилятор использует строку квалификации для поиска четкого однозначного объявления, к которому он может сопоставить ссылку на целевой элемент.  
  
 Также может потребоваться уточнение ссылки на имя, если приложение имеет доступ к более чем одному элементу программирования с тем же именем. Например, пространства имен <xref:System.Windows.Forms> и <xref:System.Web.UI.WebControls> содержат класс `Label` (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Если приложение использует оба объекта или определяет собственный класс `Label`, необходимо отличать разные объекты `Label`. Включите пространство имен или псевдоним импорта в объявление переменной. В следующем примере используется псевдоним Import.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Члены других содержащих элементов  
 При использовании несовместного члена другого класса или структуры необходимо сначала уточнить имя члена с помощью переменной или выражения, указывающего на экземпляр класса или структуры. В следующем примере `demoClass` является экземпляром класса с именем `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Нельзя использовать имя класса для определения члена, который не является [общим](../../../../visual-basic/language-reference/modifiers/shared.md). Сначала необходимо создать экземпляр в объектной переменной (в данном случае `demoClass`), а затем сослаться на него по имени переменной.  
  
 Если класс или структура имеет элемент `Shared`, можно указать, что этот элемент имеет имя класса или структуры либо переменную или выражение, которое указывает на экземпляр.  
  
 Модуль не имеет отдельных экземпляров, и все его члены `Shared` по умолчанию. Таким образом, для члена модуля необходимо указать имя модуля.  
  
 В следующем примере показаны полные ссылки на процедуры членов модуля. В примере объявляются две `Sub` процедуры, как именованные `perform`, в разных модулях проекта. Каждый из них можно указать без квалификации в своем собственном модуле, но должен быть квалифицирован при ссылке из любого места. Поскольку последняя ссылка в `module3` не имеет квалификаторов `perform`, компилятор не может разрешить эту ссылку.  
  
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
 Чтобы использовать [открытые](../../../../visual-basic/language-reference/modifiers/public.md) элементы, определенные в другом проекте, необходимо сначала задать *ссылку* на сборку или библиотеку типов этого проекта. Чтобы задать ссылку, щелкните **Добавить ссылку** в меню **проект** или используйте параметр компилятора командной строки [-Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) .  
  
 Например, можно использовать объектную модель XML .NET Framework. Если задать ссылку на пространство имен <xref:System.Xml>, можно объявить и использовать любой из его классов, например <xref:System.Xml.XmlDocument>. В следующем примере используется <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Импорт содержащих элементов  
 Для *импорта* пространств имен, содержащих модули или классы, которые необходимо использовать, можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) . Это позволяет ссылаться на элементы, определенные в импортированном пространстве имен, без указания полных имен. В следующем примере показана перезапись предыдущего примера для импорта пространства имен <xref:System.Xml>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Кроме того, оператор `Imports` может определять *Псевдоним импорта* для каждого импортированного пространства имен. Это может сделать исходный код короче и проще в чтении. В следующем примере показана перезапись предыдущего примера для использования `xD` в качестве псевдонима для пространства имен <xref:System.Xml>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Инструкция `Imports` не делает элементы из других проектов доступными для приложения. Это значит, что не стоит устанавливать ссылку. При импорте пространства имен просто удаляются требования для уточнения имен, определенных в этом пространстве имен.  
  
 Можно также использовать инструкцию `Imports` для импорта модулей, классов, структур и перечислений. Затем можно использовать члены таких импортированных элементов без уточнения. Однако необходимо всегда уточнять несовместное использование членов классов и структур переменной или выражением, результатом которого является экземпляр класса или структуры.  
  
## <a name="naming-guidelines"></a>Правила задания имен  
 При определении двух или более элементов программирования с одинаковыми именами может возникнуть *неоднозначность имени* , когда компилятор пытается разрешить ссылку на это имя. Если в области есть несколько определений или если определение не находится в области видимости, то используется ссылка неразрешимая. Пример см. на странице справки «пример с полными ссылками».  
  
 Неоднозначность имен можно избежать, присваивая всем элементам уникальные имена. Затем можно сделать ссылку на любой элемент, не указывая его имя с помощью пространства имен, модуля или класса. Кроме того, уменьшается вероятность случайной ссылки на неправильный элемент.  
  
## <a name="shadowing"></a>Удаленное управление  
 Если два программных элемента имеют одно и то же имя, один из них может скрыть или *затенить*другой. Затененный элемент недоступен для справки; Вместо этого, если в коде используется имя затененного элемента, компилятор Visual Basic разрешает его в элемент с тенью. Более подробное объяснение с примерами см. [в разделе теневая поддержка в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>См. также

- [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
