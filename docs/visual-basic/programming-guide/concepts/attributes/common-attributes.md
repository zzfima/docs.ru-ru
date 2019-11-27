---
title: Общие атрибуты
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 2889411779a275baa8c91862d4cac2f820d660d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353529"
---
# <a name="common-attributes-visual-basic"></a>Общие атрибуты (Visual Basic)

В этом разделе описываются атрибуты, наиболее часто используемые в Visual Basic программах.

- [Глобальные атрибуты](#Global)

- [Атрибут Obsolete](#Obsolete)

- [Атрибут Conditional](#Conditional)

- [Информационные атрибуты вызывающего объекта](#CallerInfo)

- [Атрибуты Visual Basic](#VB)

## <a name="Global"></a> Глобальные атрибуты

Большинство атрибутов применяется к определенным элементам языка, таким как классы или методы. Тем не менее некоторые атрибуты являются глобальными — они применяются ко всей сборке или модулю. Например, атрибут <xref:System.Reflection.AssemblyVersionAttribute> можно использовать для встраивания сведений о версии в сборку, например следующим образом:

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

Глобальные атрибуты появляются в исходном коде после любых операторов верхнего уровня `Imports` и перед объявлениями типа, модуля или пространства имен. Глобальные атрибуты могут содержаться в нескольких исходных файлах, однако эти файлы должны быть скомпилированы за один проход компиляции. Для проектов Visual Basic глобальные атрибуты обычно помещаются в файл AssemblyInfo. vb (файл создается автоматически при создании проекта в Visual Studio).

Атрибуты сборки — это значения, которые предоставляют сведения о сборке. Они подразделяются на следующие категории:

- Атрибуты удостоверения сборки

- Информационные атрибуты

- Атрибуты манифеста сборки

### <a name="assembly-identity-attributes"></a>Атрибуты удостоверения сборки

Три атрибута (со строгим именем, если оно применимо) определяют удостоверение сборки: имя, версию, язык и региональные параметры. Эти атрибуты формируют полное имя сборки и являются обязательными при ссылке на нее в коде. Атрибуты можно использовать для задания версии сборки и языка и региональных параметров. Однако значение имени задается компилятором, в интегрированной среде разработки Visual Studio, в [диалоговом окне сведений о сборке](/visualstudio/ide/reference/assembly-information-dialog-box) или в компоновщике сборок (Al.exe) при создании сборки на основе файла, содержащего манифест сборки. Атрибут <xref:System.Reflection.AssemblyFlagsAttribute> указывает, могут ли сосуществовать несколько копий сборки.

В следующей таблице приведены атрибуты удостоверения.

|Атрибут|Цель|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|Полностью описывает удостоверение сборки.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Задает версию сборки.|
|<xref:System.Reflection.AssemblyCultureAttribute>|Указывает, какой язык и региональные параметры поддерживает сборка.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Указывает, поддерживает ли сборка параллельное выполнение на одном компьютере, в одном процессе или в одном домене приложения.|

### <a name="informational-attributes"></a>Информационные атрибуты

Информационные атрибуты можно использовать для предоставления дополнительных сведений о компании или продукте в сборке. В следующей таблице показаны информационные атрибуты, определенные в пространстве имен <xref:System.Reflection?displayProperty=nameWithType>.

|Атрибут|Цель|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Определяет настраиваемый атрибут, задающий имя продукта для манифеста сборки.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Определяет настраиваемый атрибут, задающий товарный знак для манифеста сборки.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Определяет настраиваемый атрибут, задающий информационную версию для манифеста сборки.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Определяет настраиваемый атрибут, задающий название организации для манифеста сборки.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Определяет настраиваемый атрибут, задающий уведомление об авторских правах для манифеста сборки.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Дает компилятору указание использовать определенный номер версии для ресурса версии файла Win32.|
|<xref:System.CLSCompliantAttribute>|Указывает, соответствует ли сборка спецификации CLS.|

### <a name="assembly-manifest-attributes"></a>Атрибуты манифеста сборки

Атрибуты манифеста сборки можно использовать для предоставления сведений в манифесте сборки. К ним относится заголовок, описание, псевдоним по умолчанию и конфигурация. В следующей таблице показаны атрибуты манифеста сборки, определенные в пространстве имен <xref:System.Reflection?displayProperty=nameWithType>.

|Атрибут|Цель|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Определяет настраиваемый атрибут, задающий название сборки для манифеста сборки.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Определяет настраиваемый атрибут, задающий описание сборки для манифеста сборки.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Определяет настраиваемый атрибут, задающий конфигурацию сборки для манифеста сборки.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Определяет понятный псевдоним по умолчанию для манифеста сборки.|

## <a name="Obsolete"></a> Атрибут Obsolete

Атрибут `Obsolete` помечает сущность программы как нерекомендуемую для использования. Каждый случай использования сущности, помеченной как устаревшая, будет приводить к созданию предупреждения или сообщения об ошибке в зависимости от настройки атрибута. Пример.

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

В этом примере атрибут `Obsolete` применяется к классу `A` и к методу `B.OldMethod`. Поскольку для второго аргумента конструктора атрибутов, примененного к `B.OldMethod`, задано значение `true`, этот метод будет вызывать ошибку компилятора, тогда как при использовании класса `A` будет просто создаваться предупреждение. При этом вызов `B.NewMethod` не создает предупреждений или ошибок.

Строка, предоставленная в качестве первого аргумента конструктору атрибута, будет отображаться как часть предупреждения или ошибки. Например, при использовании с предыдущими определениями следующий код создает два предупреждения и одну ошибку:

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

Создается два предупреждения для класса `A`: одно для объявления ссылки на класс, а второе — для конструктора класса.

Атрибут `Obsolete` может использоваться без аргументов, однако рекомендуется включать пояснение о том, почему соответствующий элемент является устаревшим и что следует использовать вместо него.

Атрибут `Obsolete` является атрибутом однократного использования и может применяться к любой сущности, допускающей использование атрибутов. `Obsolete` является псевдонимом для <xref:System.ObsoleteAttribute>.

## <a name="Conditional"></a> Атрибут Conditional

Атрибут `Conditional` определяет зависимость выполнения метода от идентификатора предварительной обработки. Атрибут `Conditional` является псевдонимом для <xref:System.Diagnostics.ConditionalAttribute> и может применяться к методу или классу атрибута.

В этом примере атрибут `Conditional` применяется к методу для включения и отключения отображения диагностической информации для конкретной программы:

```vb
#Const TRACE_ON = True
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

Если идентификатор `TRACE_ON` не определен, выходные данные трассировки не отображаются.

Атрибут `Conditional` часто используется с идентификатором `DEBUG` для включения функций трассировки и ведения журнала для отладочных сборок (но не сборок выпуска) следующим образом:

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

Когда вызывается метод, помеченный как условный, наличие или отсутствие заданного символа предварительной обработки определяет, включается ли вызов или пропускается. Если этот символ определен, вызов включается; в противном случае вызов пропускается. Использование атрибута `Conditional` — это более понятная, элегантная и менее подверженная ошибкам альтернатива вложению методов в блоки `#if…#endif`, например следующим образом:

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

Условный метод должен быть методом в объявлении класса или структуры и не должен возвращать значение.

### <a name="using-multiple-identifiers"></a>Использование нескольких идентификаторов

Если метод содержит несколько атрибутов `Conditional`, вызов метода включается, если определен хотя бы один из условных символов (другими словами, символы логически связаны с помощью оператора ИЛИ). В этом примере наличие `A` или `B` приведет к вызову метода:

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

Для получения эффекта логического связывания символов с помощью оператора И можно определить последовательные условные методы. Например, второй метод ниже будет выполняться, только если определены `A` и `B`:

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

### <a name="using-conditional-with-attribute-classes"></a>Использование атрибута Conditional с классами атрибутов

Атрибут `Conditional` также может применяться к определению класса атрибута. В этом примере настраиваемый атрибут `Documentation` добавит сведения в метаданные, только если задано значение DEBUG.

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

## <a name="CallerInfo"></a> Информационные атрибуты вызывающего объекта

С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода. Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.

Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам. Каждый необязательный параметр задает значение по умолчанию. В следующей таблице перечислены информационные атрибуты вызывающего объекта, которые определены в пространстве имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:

|Атрибут|Описание|Введите|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Полный путь исходного файла, содержащего вызывающий объект. Это путь во время компиляции.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Номер строки в исходном файле, из которого вызывается метод.|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Имя свойства или метода вызывающего объекта. Дополнительные сведения см. в разделе [сведения о вызывающем объекте (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).|`String`|

Дополнительные сведения об атрибутах сведений о вызывающем объекте см. в разделе [сведения о вызывающем объекте (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).

## <a name="VB"></a>Атрибуты Visual Basic

В следующей таблице перечислены атрибуты, характерные для Visual Basic.

|Атрибут|Цель|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|Указывает компилятору, что класс должен быть представлен в виде COM-объекта.|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Разрешает доступ к членам модуля с использованием только квалификации, необходимой для модуля.|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Задает размер строки фиксированной длины в структуре для использования с входными и выходными функциями файлов.|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Задает размер фиксированного массива в структуре для использования с входными и выходными функциями файла.|

### <a name="comclassattribute"></a>COMClassAttribute

Используйте `COMClassAttribute`, чтобы упростить процесс создания COM-компонентов из Visual Basic. Объекты COM значительно отличаются от .NET Framework сборок, и без `COMClassAttribute`необходимо выполнить ряд действий по созданию COM-объекта из Visual Basic. Для классов, помеченных `COMClassAttribute`, компилятор выполняет многие из этих шагов автоматически.

### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute

Используйте `HideModuleNameAttribute`, чтобы разрешить доступ к членам модуля только с помощью квалификации, необходимой для модуля.

### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute

Используйте `VBFixedStringAttribute`, чтобы принудительно Visual Basic создать строку фиксированной длины. По умолчанию строки имеют переменную длину, и этот атрибут полезен при хранении строк в файлах. Следующий код демонстрирует это:

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

Используйте `VBFixedArrayAttribute`, чтобы объявить массивы с фиксированным размером. Как и в случае с Visual Basic строками, по умолчанию массивы имеют переменную длину. Этот атрибут полезен при сериализации или записи данных в файлы.

## <a name="see-also"></a>См. также

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)
- [Атрибуты](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))
