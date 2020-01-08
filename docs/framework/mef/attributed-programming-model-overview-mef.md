---
title: Общие сведения о модели атрибутивного программирования (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: c6b1093d2e821a55cc5513b077a270748a780b71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347629"
---
# <a name="attributed-programming-model-overview-mef"></a>Общие сведения о модели атрибутивного программирования (MEF)

В Managed Extensibility Framework (MEF) *модель программирования* представляет собой определенный способ задания набора концептуальных объектов, с которыми MEF работает. Такие концептуальные объекты включают в себя части, импорты и экспорты. MEF использует их, но не указывает, как они должны быть представлены. Это делает возможным применение широкого спектра моделей программирования, включая настраиваемые.

По умолчанию в MEF используется *атрибутивная модель программирования*. В атрибутивной модели программирования части, импорты, экспорты и другие объекты определены с атрибутами, которые декорируют рядовые классы платформы .NET Framework. Этот раздел описывает использование атрибутов, предоставляемых атрибутивной моделью программирования, для создания приложения MEF.

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a>Основы импорта и экспорта

*Экспорт* — это значение, которое часть предоставляет другим частям в контейнере, а *импорт* — это требование, которое часть выражает для контейнера и заполняется из доступных экспортов. В атрибутивной модели программирования импорты и экспорты объявляются за счет декорирования классов или членов атрибутами `Import` и `Export` . Атрибут `Export` может декорировать класс, поле, свойство или метод, а атрибут `Import` может декорировать поле, свойство или параметр конструктора.

Для сопоставления импорта с экспортом они должны иметь один *контракт*. Контракт состоит из строки, называемой *именем контракта*, и типа экспортированного или импортированного объекта, называемого *типом контракта*. Только в случае совпадения имени контракта и типа контракта считается, что экспорт выполняет определенный импорт.

Любой из параметров контракта или оба этих параметра могут быть неявными или явными. В следующем коде показан класс, объявляющий базовый импорт.

```vb
Public Class MyClass1
    <Import()>
    Public Property MyAddin As IMyAddin
End Class
```

```csharp
public class MyClass
{
    [Import]
    public IMyAddin MyAddin { get; set; }
}
```

В этом импорте атрибут `Import` не имеет прикрепленного параметра ни для типа, ни для имени контракта. Таким образом, они оба будут выведены из декорированного свойства. В данном случае тип контракта будет иметь значение `IMyAddin`, а именем контракта будет уникальная строка, созданная из типа контракта. (Другими словами, имя контракта будет соответствовать только экспортам, имена которых также выведены из типа `IMyAddin`.)

Ниже показан экспорт, соответствующий предыдущему импорту.

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

В данном экспорте тип контракта имеет значение `IMyAddin` , так как оно указано в качестве параметра атрибута `Export` . Экспортированный тип должен совпадать с типом контракта, быть производным от типа контракта либо реализовывать тип контракта, если он является интерфейсом. В этом экспорте фактический тип `MyLogger` реализует интерфейс `IMyAddin`. Имя контракта выводится из типа контракта, значит, этот экспорт будет соответствовать предыдущему импорту.

> [!NOTE]
> В общем случае экспорты и импорты следует объявлять в открытых классах или членах. Другие объявления поддерживаются, однако экспорт или импорт закрытого, защищенного внутреннего члена нарушает модель изоляции для данной части и поэтому не рекомендуется к применению.

Для соответствия экспорта и импорта требуется полное совпадение типа контракта. Рассмотрим следующий экспорт.

```vb
<Export()> 'WILL NOT match the previous import!
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export] //WILL NOT match the previous import!
public class MyLogger : IMyAddin { }
```

В данном экспорте тип контракта имеет значение `MyLogger` вместо `IMyAddin`. Хотя `MyLogger` реализует `IMyAddin`и поэтому может быть сведен к объекту `IMyAddin` , данный экспорт не соответствует предыдущему импорту из-за несовпадения типов контракта.

В общем случае указывать имя контракта не требуется, и большинство контрактов следует определять с учетом типа контракта и метаданных. Однако при определенных условиях важно напрямую указать имя контракта. Чаще всего это происходит, когда класс экспортирует несколько значений, использующих общий тип, например, примитивы. Имя контракта можно указать в качестве первого параметра атрибута `Import` или `Export` . В следующем коде показан импорт и экспорт с заданным именем контракта `MajorRevision`.

```vb
Public Class MyExportClass

    'This one will match
    <Export("MajorRevision")>
    Public ReadOnly Property MajorRevision As Integer
        Get
            Return 4
        End Get
    End Property

    <Export("MinorRevision")>
    Public ReadOnly Property MinorRevision As Integer
        Get
            Return 16
        End Get
    End Property
End Class
```

```csharp
public class MyClass
{
    [Import("MajorRevision")]
    public int MajorRevision { get; set; }
}

public class MyExportClass
{
    [Export("MajorRevision")] //This one will match.
    public int MajorRevision = 4;

    [Export("MinorRevision")]
    public int MinorRevision = 16;
}
```

Если тип контракта не задан, он все равно выводится из типа импорта или экспорта. Однако даже в случае явного указания имени контракта для признания соответствия экспорта и импорта требуется полное совпадение типа контракта. Например, если бы поле `MajorRevision` было строкой, выводимые типы контракта не совпадали, поэтому экспорт не соответствовал бы импорту, несмотря на одинаковое имя контракта.

### <a name="importing-and-exporting-a-method"></a>Импортирование и экспортирование метода

Атрибут `Export` может декорировать метод по аналогии с декорированием класса, свойства или функции. Экспорты метода должны указывать тип или имя контракта, так как тип нельзя вывести. Указанный тип может быть настраиваемым делегатом или универсальным типом, например `Func`. Следующий класс экспортирует метод с именем `DoSomething`.

```vb
Public Class MyAddin

    'Explicitly specifying a generic type
    <Export(GetType(Func(Of Integer, String)))>
    Public Function DoSomething(ByVal TheParam As Integer) As String
        Return Nothing 'Function body goes here
    End Function

End Class
```

```csharp
public class MyAddin
{
    //Explicitly specifying a generic type.
    [Export(typeof(Func<int, string>))]
    public string DoSomething(int TheParam);
}
```

В этом классе метод `DoSomething` принимает один параметр `int` и возвращает `string`. Для соответствия данному экспорту часть импорта должна объявить подходящий член. Следующий класс импортирует метод `DoSomething` .

```vb
Public Class MyClass1

    'Contract name must match!
    <Import()>
    Public Property MajorRevision As Func(Of Integer, String)
End Class
```

```csharp
public class MyClass
{
    [Import] //Contract name must match!
    public Func<int, string> DoSomething { get; set; }
}
```

Дополнительные сведения об использовании объекта `Func<T, T>` см. в разделе <xref:System.Func%602>.

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a>Типы импортов

MEF поддерживает несколько типов импортов, включая динамический, отложенный, предварительный и необязательный.

### <a name="dynamic-imports"></a>Динамические импорты

В некоторых случаях импортирующему классу может потребоваться сопоставить экспорты любого типа с определенным именем контракта. В этом сценарии класс может объявить *динамический импорт*. Следующий импорт соответствует любому экспорту с именем контракта "TheString".

```vb
Public Class MyClass1

    <Import("TheString")>
    Public Property MyAddin

End Class
```

```csharp
public class MyClass
{
    [Import("TheString")]
    public dynamic MyAddin { get; set; }
}
```

Когда тип контракта выводится из ключевого слова `dynamic` , он будет соответствовать любому типу контракта. В этом случае импорт должен **всегда** указывать имя контракта для сопоставления. (Если имя контракта не указано, импорт будет рассматриваться как не совпадающий экспорт.) Оба следующих экспорта будут соответствовать предыдущему импорту.

```vb
<Export("TheString", GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class

<Export("TheString")>
Public Class MyToolbar

End Class
```

```csharp
[Export("TheString", typeof(IMyAddin))]
public class MyLogger : IMyAddin { }

[Export("TheString")]
public class MyToolbar { }
```

Очевидно, что импортирующий класс должен быть готов к работе с объектом произвольного типа.

### <a name="lazy-imports"></a>Отложенные импорты

В некоторых случаях импортирующему классу может потребоваться косвенная ссылка на импортированный объект, чтобы не создавать экземпляр этого объекта немедленно. В этом сценарии класс может объявить *отложенный импорт* , используя тип контракта `Lazy<T>`. Следующее свойство импорта объявляет отложенный импорт.

```vb
Public Class MyClass1

    <Import()>
    Public Property MyAddin As Lazy(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [Import]
    public Lazy<IMyAddin> MyAddin { get; set; }
}
```

С точки зрения подсистемы композиции тип контракта `Lazy<T>` считается идентичным типу контракта `T`. Таким образом, предыдущий импорт будет соответствовать следующему экспорту.

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

Имя контракта и тип контракта можно указать в атрибуте `Import` для отложенного импорта, как описано выше в разделе "Основы импорта и экспорта".

### <a name="prerequisite-imports"></a>Предварительные импорты

Экспортированные части MEF обычно создаются подсистемой композиции, когда поступает непосредственный запрос или требуется заполнить соответствующий импорт. По умолчанию при создании части подсистема композиции использует конструктор без параметров. Чтобы подсистема использовала другой конструктор, можно отметить его с помощью атрибута `ImportingConstructor` .

Для каждой части подсистема композиции может использовать только один конструктор. Если не указать конструктор без параметров и атрибут `ImportingConstructor` или указать несколько атрибутов `ImportingConstructor`, возникает ошибка.

Для заполнения параметров конструктора, помеченного атрибутом `ImportingConstructor` , все они автоматически объявляются в качестве импортов. Это удобный способ для объявления импортов, используемых во время инициализации части. Следующий класс использует `ImportingConstructor` для объявления импорта.

```vb
Public Class MyClass1

    Private _theAddin As IMyAddin

    'Parameterless constructor will NOT be used
    'because the ImportingConstructor
    'attribute is present.
    Public Sub New()

    End Sub

    'This constructor will be used.
    'An import with contract type IMyAddin
    'is declared automatically.
    <ImportingConstructor()>
    Public Sub New(ByVal MyAddin As IMyAddin)
        _theAddin = MyAddin
    End Sub

End Class
```

```csharp
public class MyClass
{
    private IMyAddin _theAddin;

    //Parameterless constructor will NOT be
    //used because the ImportingConstructor
    //attribute is present.
    public MyClass() { }

    //This constructor will be used.
    //An import with contract type IMyAddin is
    //declared automatically.
    [ImportingConstructor]
    public MyClass(IMyAddin MyAddin)
    {
        _theAddin = MyAddin;
    }
}
```

По умолчанию атрибут `ImportingConstructor` использует выводимые типы и имена контракта для всех импортов параметров. Это можно переопределить посредством декорирования параметров с помощью атрибутов `Import` , которые затем могут явным образом определить тип контракта и имя контракта. Следующий код демонстрирует конструктор, использующий такой синтаксис для импорта производного класса вместо родительского класса.

```vb
<ImportingConstructor()>
Public Sub New(<Import(GetType(IMySubAddin))> ByVal MyAddin As IMyAddin)

End Sub
```

```csharp
[ImportingConstructor]
public MyClass([Import(typeof(IMySubAddin))]IMyAddin MyAddin)
{
    _theAddin = MyAddin;
}
```

В частности, вам следует внимательно отнестись к параметрам коллекции. Например, если вы задаете `ImportingConstructor` в конструкторе с параметром типа `IEnumerable<int>`, импорт будет соответствовать отдельному экспорту типа `IEnumerable<int>`, а не наборе экспортов типа `int`. Для соответствия набору экспортов типа `int`необходимо декорировать параметр атрибутом `ImportMany` .

Параметры, объявленные атрибутом `ImportingConstructor` в качестве импортов, также помечаются как *предварительные импорты*. В общем случае MEF разрешает экспортам и импортам формировать *цикл*. Например, цикл, в котором объект А импортирует объект Б, который в свою очередь импортирует объект А. В рядовой ситуации этот цикл не вызывает проблем, и контейнер композиции создает оба объекта обычным образом.

Если импортированное значение требуется конструктору части, этот объект не может принимать участие в цикле. Если объект А требует, чтобы перед его созданием был создан объект Б, а объект Б импортирует объект А, такой цикл будет невозможно разрешить, и возникнет ошибка композиции. Таким образом, импорты, объявленные в параметрах конструктора, являются предварительными и должны быть заполнены до того, как можно будет использовать любой экспорт из объекта, которому требуются такие импорты.

### <a name="optional-imports"></a>Необязательные импорты

Атрибут `Import` указывает требования для части к функции. Если импорт нельзя выполнить, произойдет сбой композиции этой части, а сама часть будет недоступна.

Вы можете указать, что импорт является *необязательным* , с помощью свойства `AllowDefault` . В этом случае композиция будет выполнена, даже если импорт не соответствует ни одному из доступных экспортов, а для свойства импорта будет задано значение по умолчанию для его типа свойства (`null` для свойств объекта, `false` для логических значений или ноль для числовых свойств). Следующий класс использует необязательный импорт.

```vb
Public Class MyClass1

    <Import(AllowDefault:=True)>
    Public Property thePlugin As Plugin

    'If no matching export is available,
    'thePlugin will be set to null.
End Class
```

```csharp
public class MyClass
{
    [Import(AllowDefault = true)]
    public Plugin thePlugin { get; set; }

    //If no matching export is available,
    //thePlugin will be set to null.
}
```

### <a name="importing-multiple-objects"></a>Импорт нескольких объектов

Создание атрибута `Import` выполняется успешно только тогда, когда он соответствует одному и только одному экспорту. В других случаях возникает ошибка композиции. Чтобы импортировать несколько экспортов, соответствующих одному контракту, используйте атрибут `ImportMany` . Помеченные им импорты всегда являются необязательными. Например, сбой композиции не возникнет, если отсутствуют соответствующие экспорты. Следующий класс импортирует любое число экспортов типа `IMyAddin`.

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<IMyAddin> MyAddin { get; set; }
}
```

Для доступа к импортированному массиву можно использовать стандартные методы и синтаксис `IEnumerable<T>` . Вместо этого можно также использовать обычный массив (`IMyAddin[]`).

Такой подход может быть очень важен при его использовании совместно с синтаксисом `Lazy<T>` . Например, с помощью `ImportMany`, `IEnumerable<T>`и `Lazy<T>`вы можете импортировать косвенные ссылки на любое число объектов и создать экземпляры только для тех из них, в которых возникает необходимость. Этот подход продемонстрирован в следующем классе.

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of Lazy(Of IMyAddin))

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<Lazy<IMyAddin>> MyAddin { get; set; }
}
```

<a name="avoiding_discovery"></a>

## <a name="avoiding-discovery"></a>Предотвращение обнаружения

В некоторых случаях вам может понадобиться предотвратить обнаружение вхождения части в каталог. Например, часть может быть базовым классом, предназначенным для наследования, а не для использования. Существует два пути решения этой задачи. Во-первых, вы можете использовать ключевое слово `abstract` для класса части. Абстрактные классы никогда не предоставляют экспорты, хотя могут предоставлять унаследованные экспорты производным от них классам.

Если класс нельзя сделать абстрактным, вы можете декорировать его атрибутом `PartNotDiscoverable` . Часть, декорированная этим атрибутом, не будет включена ни в какие каталоги. В следующем примере демонстрируются такие подходы. `DataOne` будет обнаружен каталогом. Поскольку `DataTwo` является абстрактным, он не будет обнаружен. Поскольку `DataThree` использовал атрибут `PartNotDiscoverable` , он не будет обнаружен.

```vb
<Export()>
Public Class DataOne
    'This part will be discovered
    'as normal by the catalog.
End Class

<Export()>
Public MustInherit Class DataTwo
    'This part will not be discovered
    'by the catalog.
End Class

<PartNotDiscoverable()>
<Export()>
Public Class DataThree
    'This part will also not be discovered
    'by the catalog.
End Class
```

```csharp
[Export]
public class DataOne
{
    //This part will be discovered
    //as normal by the catalog.
}

[Export]
public abstract class DataTwo
{
    //This part will not be discovered
    //by the catalog.
}

[PartNotDiscoverable]
[Export]
public class DataThree
{
    //This part will also not be discovered
    //by the catalog.
}
```

<a name="metadata_and_metadata_views"></a>

## <a name="metadata-and-metadata-views"></a>Метаданные и их представления

Экспорты могут предоставлять дополнительные сведения о себе, которые называются *метаданными*. Метаданные можно использовать для передачи свойств экспортированного объекта в импортирующую часть. Импортирующая часть может использовать эти данные для выбора используемого экспорта или для сбора информации об экспорте без необходимости его создания. По этой причине для использования метаданных импорт должен быть отложенным.

Чтобы использовать метаданные обычно объявляется интерфейс, называемый *представлением метаданных*, который объявляет о доступности метаданных. Интерфейс представления метаданных должен иметь только свойства, и эти свойства должны иметь методы доступа `get` . Следующий интерфейс является примером представления метаданных.

```vb
Public Interface IPluginMetadata

    ReadOnly Property Name As String

    <DefaultValue(1)>
    ReadOnly Property Version As Integer

End Interface
```

```csharp
public interface IPluginMetadata
{
    string Name { get; }

    [DefaultValue(1)]
    int Version { get; }
}
```

В качестве представления метаданных также можно использовать общую коллекцию `IDictionary<string, object>`, однако это нивелирует преимущества проверки типа и поэтому не рекомендовано к применению.

В общем случае все указанные в представлении метаданных свойства являются обязательными, а любые экспорты, которые их не предоставляют, не будут считаться соответствующими. Атрибут `DefaultValue` указывает на то, что свойство является необязательным. Если свойство не задано, ему назначается значение по умолчанию, указанное в качестве параметра `DefaultValue`. Ниже приведены два разных класса, декорированных метаданными. Оба этих класса будут соответствовать предыдущему представлению метаданных.

```vb
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class MyLogger
    Implements IPlugin

End Class

'Version is not required because of the DefaultValue
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Disk Writer")>
Public Class DWriter
    Implements IPlugin

End Class
```

```csharp
[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
}

[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Disk Writer")]
    //Version is not required because of the DefaultValue
public class DWriter : IPlugin
{
}
```

Метаданные указываются после атрибута `Export` с помощью атрибута `ExportMetadata` . Каждый элемент метаданных состоит из пары имя-значение. Часть имени в метаданных должна совпадать с именем соответствующего свойства в представлении метаданных, а значение будет назначено этому свойству.

Используемое представление метаданных (если оно имеется) задает импортер. Импорт с метаданными объявляется как отложенный, при этом интерфейс метаданных используется в качестве второго параметра типа для `Lazy<T,T>`. Следующий класс импортирует предыдущую часть с метаданными.

```vb
Public Class Addin

    <Import()>
    Public Property plugin As Lazy(Of IPlugin, IPluginMetadata)
End Class
```

```csharp
public class Addin
{
    [Import]
    public Lazy<IPlugin, IPluginMetadata> plugin;
}
```

Во многих случаях вам потребуется объединить метаданные с атрибутом `ImportMany` , чтобы выполнить синтаксический анализ доступных импортов, выбрать один из них и создать его экземпляр либо отфильтровать коллекцию для соответствия определенному условию. Следующий класс создает экземпляры только тех объектов `IPlugin` , у которых `Name` имеет значение "Logger".

```vb
Public Class User

    <ImportMany()>
    Public Property plugins As IEnumerable(Of Lazy(Of IPlugin, IPluginMetadata))

    Public Function InstantiateLogger() As IPlugin

        Dim logger As IPlugin
        logger = Nothing

        For Each Plugin As Lazy(Of IPlugin, IPluginMetadata) In plugins
            If Plugin.Metadata.Name = "Logger" Then
                logger = Plugin.Value
            End If
        Next
        Return logger
    End Function

End Class
```

```csharp
public class User
{
    [ImportMany]
    public IEnumerable<Lazy<IPlugin, IPluginMetadata>> plugins;

    public IPlugin InstantiateLogger()
    {
        IPlugin logger = null;

        foreach (Lazy<IPlugin, IPluginMetadata> plugin in plugins)
        {
            if (plugin.Metadata.Name == "Logger")
                logger = plugin.Value;
        }
        return logger;
    }
}
```

<a name="import_and_export_inheritance"></a>

## <a name="import-and-export-inheritance"></a>Наследование импорта и экспорта

Если класс наследует от части, он также может стать частью. Импорты всегда наследуются подклассами. Таким образом, подкласс части всегда будет частью и будет иметь те же импорты, что и его родительский класс.

Экспорты, объявленные с помощью атрибута `Export` , не наследуются подклассами. Однако часть может экспортировать сама себя с помощью атрибута `InheritedExport` . Подклассы этой части будут наследовать и предоставлять тот же экспорт, включая имя и тип контракта. В отличие от атрибута `Export` атрибут `InheritedExport` можно применить не на уровне членов, а только на уровне классов. Таким образом, экспорты на уровне членов никогда не наследуются.

Четыре следующих класса демонстрируют принципы наследования импорта и экспорта. `NumTwo` наследует от `NumOne`, поэтому `NumTwo` импортирует `IMyData`. Обычные импорты не наследуются, поэтому `NumTwo` ничего не экспортирует. Тип`NumFour` наследуется от типа `NumThree`. Поскольку `NumThree` использовал `InheritedExport`, `NumFour` имеет один экспорт с типом контракта `NumThree`. Экспорты на уровне членов никогда не наследуются, поэтому `IMyData` не экспортируется.

```vb
<Export()>
Public Class NumOne
    <Import()>
    Public Property MyData As IMyData
End Class

Public Class NumTwo
    Inherits NumOne

    'Imports are always inherited, so NumTwo will
    'Import IMyData

    'Ordinary exports are not inherited, so
    'NumTwo will NOT export anything.  As a result it
    'will not be discovered by the catalog!

End Class

<InheritedExport()>
Public Class NumThree

    <Export()>
    Public Property MyData As IMyData

    'This part provides two exports, one of
    'contract type NumThree, and one of
    'contract type IMyData.

End Class

Public Class NumFour
    Inherits NumThree

    'Because NumThree used InheritedExport,
    'this part has one export with contract
    'type NumThree.

    'Member-level exports are never inherited,
    'so IMyData is not exported.

End Class
```

```csharp
[Export]
public class NumOne
{
    [Import]
    public IMyData MyData { get; set; }
}

public class NumTwo : NumOne
{
    //Imports are always inherited, so NumTwo will
    //import IMyData.

    //Ordinary exports are not inherited, so
    //NumTwo will NOT export anything. As a result it
    //will not be discovered by the catalog!
}

[InheritedExport]
public class NumThree
{
    [Export]
    Public IMyData MyData { get; set; }

    //This part provides two exports, one of
    //contract type NumThree, and one of
    //contract type IMyData.
}

public class NumFour : NumThree
{
    //Because NumThree used InheritedExport,
    //this part has one export with contract
    //type NumThree.

    //Member-level exports are never inherited,
    //so IMyData is not exported.
}
```

При наличии метаданных, связанных с атрибутом `InheritedExport` , они также наследуются. (Дополнительные сведения см. в разделе "метаданные и представления метаданных" выше.) Наследованные метаданные не могут быть изменены подклассом. Однако за счет повторного объявления атрибута `InheritedExport` с таким же именем и типом контракта и новыми метаданными подкласс может заменить унаследованные метаданные на новые. Следующий класс демонстрирует этот принцип. Часть `MegaLogger` наследует от `Logger` и включает атрибут `InheritedExport` . Поскольку `MegaLogger` повторно объявляет новые метаданные с именем Status, он не наследует метаданные Name и Version от `Logger`.

```vb
<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class Logger
    Implements IPlugin

    'Exports with contract type IPlugin
    'and metadata "Name" and "Version".
End Class

Public Class SuperLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Name" and "Version", exactly the same
    'as the Logger class.

End Class

<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Status", "Green")>
Public Class MegaLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Status" only. Re-declaring
    'the attribute replaces all metadata.

End Class
```

```csharp
[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version".
}

public class SuperLogger : Logger
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version", exactly the same
    //as the Logger class.
}

[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Status", "Green")]
public class MegaLogger : Logger        {
    //Exports with contract type IPlugin and
    //metadata "Status" only. Re-declaring
    //the attribute replaces all metadata.
}
```

При повторном объявлении атрибута `InheritedExport` для переопределения метаданных убедитесь в совпадении типов контракта. (В предыдущем примере `IPlugin` является типом контракта.) Если они отличаются, вместо переопределения второй атрибут будет создавать второй, Независимый экспорт из части. В общем случае это означает, что нужно явно задавать тип контракта при переопределении атрибута `InheritedExport` , как показано в предыдущем примере.

Поскольку экземпляры для интерфейсов нельзя создавать непосредственно, в общем случае их нельзя декорировать атрибутами `Export` или `Import` . Однако интерфейс можно декорировать атрибутом `InheritedExport` на уровне интерфейсов, и этот экспорт наравне со всеми сопоставленными метаданными будет наследоваться любыми реализующими классами. Однако сам интерфейс не будет доступен в качестве части.

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a>Настраиваемые атрибуты экспорта

Базовые атрибуты экспорта `Export` и `InheritedExport`можно расширить для включения метаданных в качестве свойств атрибута. Эту методику удобно использовать для применения одних метаданных многим частям или создания дерева наследования атрибутов метаданных.

Настраиваемый атрибут может задавать тип контракта, имя контракта или любые другие метаданные. Чтобы определить настраиваемый атрибут, наследующий от `ExportAttribute` (или `InheritedExportAttribute`) класс должен быть декорирован атрибутом `MetadataAttribute` . Следующий класс определяет настраиваемый атрибут.

```vb
<MetadataAttribute()>
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=false)>
Public Class MyAttribute
    Inherits ExportAttribute

    Public Property MyMetadata As String

    Public Sub New(ByVal myMetadata As String)
        MyBase.New(GetType(IMyAddin))

        myMetadata = myMetadata
    End Sub

End Class
```

```csharp
[MetadataAttribute]
[AttributeUsage(AttributeTargets.Class, AllowMultiple=false)]
public class MyAttribute : ExportAttribute
{
    public MyAttribute(string myMetadata)
        : base(typeof(IMyAddin))
    {
        MyMetadata = myMetadata;
    }

    public string MyMetadata { get; private set; }
}
```

Этот класс определяет настраиваемый атрибут, имеющий имя `MyAttribute` , тип контракта `IMyAddin` и некоторые метаданные с именем `MyMetadata`. Все свойства в классе, помеченном атрибутом `MetadataAttribute` , считаются метаданными, определенными в настраиваемом атрибуте. Два следующих объявления эквивалентны.

```vb
<Export(GetType(IMyAddin))>
<ExportMetadata("MyMetadata", "theData")>
Public Property myAddin As MyAddin
```

```vb
<MyAttribute("theData")>
Public Property myAddin As MyAddin
```

```csharp
[Export(typeof(IMyAddin)),
    ExportMetadata("MyMetadata", "theData")]
public MyAddin myAddin { get; set; }
```

```csharp
[MyAttribute("theData")]
public MyAddin myAddin { get; set; }
```

В первом объявлении тип контракта и метаданные заданы явным образом. Во втором объявлении тип контракта и метаданные заданы неявно в настраиваемом атрибуте. В случаях, когда большой объем одинаковых метаданных необходимо применить к множеству частей (например, информация об авторе или авторских правах), использование настраиваемого атрибута позволяет сэкономить много времени и избежать повторений. Кроме того, для внесения отличий можно создавать деревья наследования настраиваемых атрибутов.

Чтобы создать необязательные метаданные в настраиваемом атрибуте, можно воспользоваться атрибутом `DefaultValue` . При применении к свойству в классе настраиваемых атрибутов этот атрибут указывает, что декорированное свойство является необязательным и может не предоставляться экспортером. Если значение свойства не задано, ему назначается значение по умолчанию для данного типа свойства (обычно это `null`, `false`или 0).

<a name="creation_policies"></a>

## <a name="creation-policies"></a>Политики создания

Когда часть указывает импорт и выполняется композиция, контейнер композиции пытается найти соответствующий экспорт. Если он успешно сопоставляет импорт с экспортом, для импортирующего члена устанавливается экземпляр экспортированного объекта. Источник этого экземпляра контролируется *политикой создания*экспортирующей части.

Возможны две политики создания — *общая* и *не общая*. Часть с общей политикой создания предоставляется для общего доступа всем импортам в контейнере для части с таким контрактом. Когда подсистема композиции находит соответствие и должна задать импортирующее свойство, она создает экземпляр новой копии этой части, если такая копия еще не существует, в противном случае она предоставляет имеющуюся копию. Это означает, что несколько объектов могут иметь ссылки на одну часть. Такие части не должны полагаться на внутреннее состояние, которое может быть изменено из разных мест. Эта политика подходит для статических частей, частей, предоставляющих службы, и частей, потребляющих большой объем памяти или других ресурсов.

Часть с политикой создания, не являющейся общей, будет создаваться каждый раз при обнаружении соответствующего импорта для одного из ее экспортов. Таким образом, экземпляр новой копии будет создаваться для каждого импорта в контейнере, соответствующем одному из экспортированных контактов части. Внутреннее состояние этих копий не предоставляется для общего доступа. Эта политика подходит для частей, в которых каждому импорту требуется свое внутреннее состояние.

Политику создания для части может указывать как импорт, так и экспорт, для этого доступны следующие значения: `Shared`, `NonShared`и `Any`. По умолчанию как для импортов, так и для экспортов используется `Any` . Экспорт, указывающий `Shared` или `NonShared` , будет сопоставлен только с импортом, указывающим то же значение или значение `Any`. Аналогичным образом, импорт, указывающий `Shared` или `NonShared` , будет сопоставлен только с экспортом, указывающим то же значение или значение `Any`. Импорты и экспорты с несовместимыми политиками создания соответствием не считаются по аналогии с импортами и экспортами, имеющими разные имена или типы контракта. Если как импорт, так и экспорт указывают значение `Any`либо не указывают никакого значения, используя политику создания по умолчанию `Any`, задается общая политика создания.

В следующем примере показано задание политик создания как импортами, так и экспортами. `PartOne` не задает политику создания, поэтому используется значение по умолчанию `Any`. `PartTwo` не задает политику создания, поэтому используется значение по умолчанию `Any`. Поскольку как импорт, так и экспорт используют значение по умолчанию `Any`, политика `PartOne` будет общей. `PartThree` задает политику создания `Shared` , поэтому `PartTwo` и `PartThree` будут совместно использовать одну копию `PartOne`. `PartFour` задает политику создания `NonShared` , поэтому политика `PartFour` не будет являться общей в `PartFive`. `PartSix` задает политику создания `NonShared` . `PartFive` и `PartSix` получат отдельные копии `PartFour`. `PartSeven` задает политику создания `Shared` . Поскольку экспортированный `PartFour` с политикой создания `Shared`отсутствует, импорт `PartSeven` не имеет совпадений и не заполняется.

```vb
<Export()>
Public Class PartOne
    'The default creation policy for an export is Any.
End Class

Public Class PartTwo

    <Import()>
    Public Property partOne As PartOne

    'The default creation policy for an import is Any.
    'If both policies are Any, the part will be shared.

End Class

Public Class PartThree

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partOne As PartOne

    'The Shared creation policy is explicitly specified.
    'PartTwo and PartThree will receive references to the
    'SAME copy of PartOne.

End Class

<Export()>
<PartCreationPolicy(CreationPolicy.NonShared)>
Public Class PartFour
    'The NonShared creation policy is explicitly specified.
End Class

Public Class PartFive

    <Import()>
    Public Property partFour As PartFour

    'The default creation policy for an import is Any.
    'Since the export's creation policy was explicitly
    'defined, the creation policy for this property will
    'be non-shared.

End Class

Public Class PartSix

    <Import(RequiredCreationPolicy:=CreationPolicy.NonShared)>
    Public Property partFour As PartFour

    'Both import and export specify matching creation
    'policies.  PartFive and PartSix will each receive
    'SEPARATE copies of PartFour, each with its own
    'internal state.

End Class

Public Class PartSeven

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partFour As PartFour

    'A creation policy mismatch.  Because there is no
    'exported PartFour with a creation policy of Shared,
    'this import does not match anything and will not be
    'filled.

End Class
```

```csharp
[Export]
public class PartOne
{
    //The default creation policy for an export is Any.
}

public class PartTwo
{
    [Import]
    public PartOne partOne { get; set; }

    //The default creation policy for an import is Any.
    //If both policies are Any, the part will be shared.
}

public class PartThree
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartOne partOne { get; set; }

    //The Shared creation policy is explicitly specified.
    //PartTwo and PartThree will receive references to the
    //SAME copy of PartOne.
}

[Export]
[PartCreationPolicy(CreationPolicy.NonShared)]
public class PartFour
{
    //The NonShared creation policy is explicitly specified.
}

public class PartFive
{
    [Import]
    public PartFour partFour { get; set; }

    //The default creation policy for an import is Any.
    //Since the export's creation policy was explicitly
    //defined, the creation policy for this property will
    //be non-shared.
}

public class PartSix
{
    [Import(RequiredCreationPolicy = CreationPolicy.NonShared)]
    public PartFour partFour { get; set; }

    //Both import and export specify matching creation
    //policies.  PartFive and PartSix will each receive
    //SEPARATE copies of PartFour, each with its own
    //internal state.
}

public class PartSeven
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartFour partFour { get; set; }

    //A creation policy mismatch.  Because there is no
    //exported PartFour with a creation policy of Shared,
    //this import does not match anything and will not be
    //filled.
}
```

<a name="life_cycle_and_disposing"></a>

## <a name="life-cycle-and-disposing"></a>Жизненный цикл и утилизация

Поскольку части размещаются в контейнере композиции, их жизненный цикл может быть сложнее, чем у обычных объектов. Части могут реализовать два важных интерфейса, связанных с жизненным циклом: `IDisposable` и `IPartImportsSatisfiedNotification`.

Части, которые требуют выполнения операций при завершении работы или освобождают ресурсы, должны реализовать `IDisposable`, как это принято для объектов .NET Framework. Однако, поскольку контейнер создает и обслуживает ссылки на части, вызов метода `Dispose` для части должен осуществлять только тот контейнер, которому она принадлежит. Сам контейнер реализует `IDisposable`, а в рамках очистки в `Dispose` он вызывает `Dispose` для всех принадлежащих ему частей. Поэтому вас следует всегда утилизировать контейнер композиции, когда он и любые принадлежащие ему части больше не нужны.

Для контейнеров композиции с большим временем существования может возникнуть проблема использования памяти, которую вызывают части с политикой создания, не являющейся общей. Такие не являющиеся общими части могут создаваться несколько раз и не утилизируются до тех пор, пока не будет утилизирован сам контейнер. Для решения данной проблемы контейнер предоставляет метод `ReleaseExport` . Вызов этого метода для не являющегося общим экспорта удаляет данный экспорт из контейнера композиции и утилизирует его. Части, используемые только этим удаленным экспортом, и все вложенные элементы также удаляются и утилизируются. Это позволяет освободить ресурсы без утилизации всего контейнера композиции.

`IPartImportsSatisfiedNotification` содержит один метод с именем `OnImportsSatisfied`. Этот метод вызывается контейнером композиции для любых частей, реализующих интерфейс, когда композиция уже завершена, а импорты части готовы к использованию. Части создаются подсистемой композиции для заполнения импортов других частей. До установки импортов части вы не можете выполнять никакую инициализацию, которая основана на импортированных значениях в конструкторе частей или выполняет операции с ними, если только эти значения не были указаны в качестве необходимых условий с помощью атрибута `ImportingConstructor` . В общем случае этот метод является предпочтительным, но иногда внедрение конструктора может быть недоступно. В таких ситуациях инициализацию можно выполнить в `OnImportsSatisfied`, при этом часть должна реализовать `IPartImportsSatisfiedNotification`.

## <a name="see-also"></a>См. также:

- [Видео канала 9. Open Up Your Applications with the Managed Extensibility Framework (Раскройте потенциал своих приложений с помощью Managed Extensibility Framework)](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [Видео канала 9. Managed Extensibility Framework (MEF) 2.0](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)
