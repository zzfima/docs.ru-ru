---
title: "Общие атрибуты (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f470e6ff3e316076d71a34346f741cc4504471a3
ms.lasthandoff: 03/13/2017

---
# <a name="common-attributes-visual-basic"></a>Общие атрибуты (Visual Basic)
В этом разделе описываются атрибуты, которые чаще всего используются в программах Visual Basic.  
  
-   [Глобальные атрибуты](#Global)  
  
-   [Устаревший атрибут](#Obsolete)  
  
-   [Условный атрибут](#Conditional)  
  
-   [Информационные атрибуты вызывающего](#CallerInfo)  
  
-   [Атрибуты Visual Basic](#VB)  
  
##  <a name="Global"></a>Глобальные атрибуты  
 Большинство атрибутов применяется к определенным элементам языка, такие как классы или методы; Тем не менее, некоторые атрибуты являются глобальными — они применяются для всей сборки или модуля. Например <xref:System.Reflection.AssemblyVersionAttribute>атрибут может использоваться для встраивания сведений о версии в сборку, следующим образом:</xref:System.Reflection.AssemblyVersionAttribute>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 Глобальные атрибуты отображаются в исходном коде после любых верхнего уровня`Imports` инструкций и перед всеми объявлениями типов, модуль или пространство имен. Глобальные атрибуты могут появляться в нескольких исходных файлов, но файлы должны быть скомпилированы за один проход компиляции. Для проектов Visual Basic глобальных атрибутов обычно помещаются в файле AssemblyInfo.vb (файл создается автоматически при создании проекта в Visual Studio).  
  
 Атрибуты сборки — это значения, которые предоставляют сведения о сборке. Они делятся на следующие категории:  
  
-   Атрибуты удостоверения сборки.  
  
-   Информационные атрибуты  
  
-   Атрибуты манифеста сборки  
  
### <a name="assembly-identity-attributes"></a>Атрибуты удостоверения сборки  
 Удостоверение сборки определяют три атрибута (со строгим именем, если применимо): имя, версию и язык и региональные параметры. Эти атрибуты формируют полное имя сборки и являются обязательными при создании ссылки в коде. Можно задать язык и региональные параметры с помощью атрибутов и версии сборки. Однако значение имени задается компилятором, в СРЕДЕ Visual Studio [диалоговое окно сведений о сборке](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), или компоновщик сборок (Al.exe) при создании сборки на основе файла, содержащего манифест сборки. <xref:System.Reflection.AssemblyFlagsAttribute>Атрибут указывает, могут ли сосуществовать несколько копий сборки.</xref:System.Reflection.AssemblyFlagsAttribute>  
  
 Ниже приведены атрибуты удостоверения.  
  
|Атрибут|Цель|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>|Полностью описывает удостоверение сборки.|  
|<xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute>|Указывает версию сборки.|  
|<xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute>|Указывает, какой язык и региональные параметры поддерживает сборка.|  
|<xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute>|Указывает, поддерживает ли сборка side-by-side выполнения на одном компьютере, в том же процессе или в том же домене приложения.|  
  
### <a name="informational-attributes"></a>Информационные атрибуты  
 Информационные атрибуты можно использовать для предоставления дополнительных сведений о компании или продукте в сборке. В следующей таблице показаны информационные атрибуты, определенные в <xref:System.Reflection?displayProperty=fullName>имен.</xref:System.Reflection?displayProperty=fullName>  
  
|Атрибут|Цель|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute>|Определяет пользовательский атрибут, который указывает название продукта для манифеста сборки.|  
|<xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute>|Определяет пользовательский атрибут товарного знака для манифеста сборки.|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute>|Определяет пользовательский атрибут версии для манифеста сборки.|  
|<xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute>|Определяет пользовательский атрибут, который указывает название компании для манифеста сборки.|  
|<xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute>|Определяет пользовательский атрибут авторских прав для манифеста сборки.|  
|<xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute>|Указывает компилятору использовать определенный номер версии для ресурса версии файла Win32.|  
|<xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute>|Указывает, является ли сборка совместимым с общей спецификацией (CLS).|  
  
### <a name="assembly-manifest-attributes"></a>Атрибуты манифеста сборки  
 Атрибуты манифеста сборки можно использовать для предоставления сведений в манифесте сборки. Это включает в себя заголовок, описание, псевдоним по умолчанию и конфигурации. В следующей таблице представлены атрибуты манифеста сборки определены в <xref:System.Reflection?displayProperty=fullName>имен.</xref:System.Reflection?displayProperty=fullName>  
  
|Атрибут|Цель|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute>|Определяет пользовательский атрибут названия сборки для манифеста сборки.|  
|<xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute>|Определяет пользовательский атрибут описания сборки для манифеста сборки.|  
|<xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute>|Определяет пользовательский атрибут, который описывает конфигурацию сборки (например, распространение или отладку) для манифеста сборки.|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute>|Определяет понятный псевдоним по умолчанию для манифеста сборки|  
  
##  <a name="Obsolete"></a>Устаревший атрибут  
 `Obsolete` Помечает сущности программы, не рекомендуется использовать. Каждый случай использования сущности, отмеченной устаревшей постоянно генерирует предупреждение или сообщение об ошибке, в зависимости от настройки атрибута. Например:  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 В этом примере `Obsolete` атрибут применяется к классу `A` и метод `B.OldMethod`. Так как второй аргумент конструктора атрибута, применить к `B.OldMethod` задано значение `true`, этот метод будет приводить к ошибке компилятора, а с помощью класса `A` будет просто создают предупреждения. Вызов `B.NewMethod`, тем не менее, создает предупреждение или ошибка.  
  
 Строка, предоставленная в качестве первого аргумента конструктору атрибута будет отображаться как часть предупреждения или ошибки. Например при использовании с предыдущими определениями следующий код генерирует два предупреждения и одну ошибку:  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 Два предупреждения для класса `A` создаются: один для объявления ссылки на класс и один для конструктора класса.  
  
 `Obsolete` Атрибут может использоваться без аргументов, но включать пояснение, почему соответствующий элемент является устаревшим и что следует использовать вместо него рекомендуется использовать.  
  
 `Obsolete` Атрибут является атрибутом однократного использования и может применяться к любой сущности, допускающей использование атрибутов. `Obsolete`является псевдонимом для <xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute>  
  
##  <a name="Conditional"></a>Условный атрибут  
 `Conditional` Атрибут делает выполнение метода зависимым от идентификатора предварительной обработки. `Conditional` Атрибута является псевдонимом для <xref:System.Diagnostics.ConditionalAttribute>и может применяться к методу или атрибут класса</xref:System.Diagnostics.ConditionalAttribute>  
  
 В этом примере `Conditional` применяется к методу для включения и отключения отображения диагностической информации для конкретной программы:  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 Если `TRACE_ON` идентификатор не определен, отображаются выходные данные трассировки.  
  
 `Conditional` Атрибут часто используется с `DEBUG` идентификатор для включения трассировки и функции ведения журнала для построения отладки, но не в построениях выпуска, следующим образом:  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 Когда вызывается метод, помеченный как условный, наличие или отсутствие заданного символа предварительной обработки определяет, включен ли вызов или опущен. Если этот символ определен, вызов включается; в противном случае — вызов опускается. С помощью `Conditional` представляет собой более понятную, элегантную и менее подверженную ошибкам альтернативу вложению методов в `#if…#endif` блоки, следующим образом:  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 Условный метод должен быть методом в объявлении класса или структуры и не возвращает значение.  
  
### <a name="using-multiple-identifiers"></a>Использование нескольких идентификаторов  
 Если метод имеет несколько `Conditional` атрибутов, вызов метода включается, если определен хотя бы один из условных символов (другими словами, символы логически связаны оператором OR). В этом примере на наличие `A` или `B` приведет к вызову метода:  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 Для получения эффекта логического связывания символов оператором AND, можно задать последовательные условные методы. Например, второй метод, приведенный ниже будет выполняться, только если оба `A` и `B` определены:  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a>С помощью условного с классами атрибутов  
 `Conditional` Атрибут также может применяться к определению класса атрибутов. В этом примере пользовательский атрибут `Documentation` только добавляет сведения в метаданные, если задано значение DEBUG.  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <a name="CallerInfo"></a>Информационные атрибуты вызывающего  
 С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода. Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя члена, вызывающего объекта.  
  
 Чтобы получить сведения о вызывающем члена, используйте атрибуты, которые применяются к необязательным параметрам. Каждый дополнительный параметр задает значение по умолчанию. В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в <xref:System.Runtime.CompilerServices?displayProperty=fullName>пространство имен:</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
|Атрибут|Описание|Тип|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Полный путь исходного файла, содержащего вызывающий объект. Это путь во время компиляции.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Номер строки в исходном файле, из которого вызывается метод.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Имя метода или свойства вызывающего объекта. Дополнительные сведения см. в разделе [сведения о вызывающем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).|`String`|  
  
 Дополнительные сведения о информационные атрибуты вызывающего объекта, в разделе [сведения о вызывающем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).  
  
##  <a name="VB"></a>Атрибуты Visual Basic  
 В следующей таблице перечислены атрибуты, относящиеся к Visual Basic.  
  
|Атрибут|Цель|  
|---------------|-------------|  
|<xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>|Указывает компилятору на то, что класс должен быть предоставлен как COM-объект.|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Позволяет членам модуля должен осуществляться с использованием только квалификации, необходимой для модуля.|  
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Указывает размер строки фиксированной длины в структуре для использования с файлом входных и выходных данных функции.|  
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Указывает размер фиксированного массива в структуре для использования с файлом входных и выходных данных функции.|  
  
### <a name="comclassattribute"></a>COMClassAttribute  
 Использование `COMClassAttribute` для упрощения процесса создания COM-компонентов с помощью Visual Basic. COM-объекты существенно отличаются от сборок .NET Framework и не `COMClassAttribute`, необходимо выполнить ряд действий для создания объекта COM с помощью Visual Basic. Для классов, помеченных атрибутом `COMClassAttribute`, компилятор выполняет большинство этих шагов автоматически.  
  
### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute  
 Использование `HideModuleNameAttribute` позволяет членам модуля, к которым осуществляется с использованием только квалификации, необходимой для модуля.  
  
### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute  
 Используйте `VBFixedStringAttribute` для принудительного Visual Basic для создания строки фиксированной длины. Строки имеют переменную длину по умолчанию, и этот атрибут полезен при хранении строк для файлов. Следующий код демонстрирует это:  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute  
 Используйте `VBFixedArrayAttribute` Чтобы объявить массивы фиксированного размера. Как Visual Basic строки массивы имеют переменную длину по умолчанию. Этот атрибут полезен при сериализации или записи данных в файлы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c)   
 [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
