---
title: Managed Extensibility Framework (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
ms.openlocfilehash: add2b1320e80ccbe1b4bfac94c051148d86a4722
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837029"
---
# <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

В этой статье приводятся общие сведения о библиотеке Managed Extensibility Framework, которая появилась на платформе .NET Framework 4.

## <a name="what-is-mef"></a>Что такое MEF

Платформа Managed Extensibility Framework (MEF) — это библиотека для создания простых и расширяемых приложений. Она позволяет разработчикам приложений находить и использовать расширения без каких-либо настроек. Она также позволяет разработчикам расширений легко инкапсулировать код и избегать ненадежных жестких зависимостей. MEF позволяет повторно использовать в приложениях не только расширения, но и целые приложения.

## <a name="the-problem-of-extensibility"></a>Проблема расширяемости

Представьте себе, что вы являетесь архитектором крупного приложения, которое должно обеспечивать поддержку для расширяемости. Приложение должно включать потенциально большое количество небольших компонентов, а также отвечает за их создание и запуск.

Простейшим подходом к решению такой проблемы является включение компонентов в виде исходного кода в приложение и их вызов прямо из кода. Такой подход имеет ряд очевидных недостатков. Самое главное, что нельзя добавлять новые компоненты без изменения исходного кода — данное ограничение может быть приемлемым, например, для веб-приложения, но не для клиентского приложения. Столь же проблематичной может оказаться ситуация, что у вас не будет доступа к исходному коду для компонентов, так как они могут разрабатываться сторонними производителями, и в силу ряда причин вы не сможете разрешить им доступ к своим приложениям.

Несколько более сложный подход будет заключаться в предоставлении точки или интерфейса расширения, позволяющего разделять приложение и его компоненты. В рамках этой модели можно предоставить интерфейс, который может реализовывать компонент, а также интерфейс API, позволяющий ему взаимодействовать с приложением. Это позволяет решить проблему необходимости доступа к исходному коду, но по-прежнему имеет свои собственные сложности.

Так как приложение не в состоянии самостоятельно обнаруживать компоненты, ему по-прежнему необходимо явным образом сообщать, какие компоненты имеются в наличии и подлежат загрузке. Обычно для этого применяется явная регистрация доступных компонентов в файле конфигурации. Это означает, что обеспечение нужных компонентов превращается в задачу обслуживания, особенно в тех случаях, когда обновление должен выполнять конечный пользователь, а не сам разработчик.

Кроме того, компоненты могут взаимодействовать друг с другом, за исключением строго определенных каналов самого приложения. Если в архитектуре приложения не учтена потребность в определенной связи, то обычно это оказывается невозможным.

Наконец, разработчики компонентов вынуждены принимать жесткие зависимости от того, какая именно сборка содержит реализуемый ими интерфейс. Это затрудняет возможное применение компонента в нескольких приложениях и также может вызвать проблемы при создании тестовой платформы для компонентов.

## <a name="what-mef-provides"></a>Сведения о возможностях MEF

Вместо явной регистрации доступных компонент MEF позволяет обнаруживать их неявным образом — с помощью *композиции*. Компонент MEF, называемый *частью*, декларативно указывает как свои зависимости (называемые *импортом*), так и свои возможности, которые он предоставляет (называемые *экспортом*). При создании некоторой части обработчик композиции MEF удовлетворяет свои импортируемые компоненты за счет элементов, доступных из других частей.

Такой поход позволяет решить проблемы, рассмотренные в предыдущем разделе. Так как части MEF декларативно указывают свои возможности, они могут быть обнаружены во время выполнения, то есть, приложение может применять части без жестко кодированных ссылок или ненадежных файлов конфигурации. Платформа MEF позволяет приложениям обнаруживать и анализировать части с помощью своих метаданных без создания экземпляров и даже без загрузки их сборок. В результате нет необходимости четко указывать время и способ загрузки расширений.

Кроме обеспечиваемого экспорта, часть может указать свои импортируемые элементы, которые будут заполнены другими частями. Это делает связь между частями не только возможной, но и простой, и обеспечивает качественное разбиение кода. Например, общие для нескольких компонентов службы можно выделить в отдельную часть, которую можно будет легко изменять или заменять.

Так как для модели MEF жесткие зависимости от определенной сборки приложения не требуются, она позволяет повторно использовать расширения в различных приложениях. Это также упрощает разработку окружения теста, не зависящего от приложения, для тестирования компонентов расширений.

Расширяемое приложение, созданное с помощью платформы MEF, объявляет импортируемый элемент, который может быть заполнен компонентами расширения, а также может объявить экспортируемые элементы, позволяющие применять службы приложений для расширений. Каждый компонент расширения объявляет экспортируемый элемент, а также может объявлять импортируемые элементы. Таким образом, сами компоненты расширения автоматически становятся расширяемыми.

## <a name="where-mef-is-available"></a>Где доступна MEF

MEF является неотъемлемой частью .NET Framework 4 и присутствует везде, где применяется платформа .NET Framework. MEF можно использовать в клиентских приложениях, независимо от того, применяют они Windows Forms, WPF или любую другую технологию, либо в серверных приложениях, где применяется ASP.NET.

## <a name="mef-and-maf"></a>MEF и MAF

На платформе .NET Framework предыдущих версий появилась платформа Managed Add-in Framework (MAF), которая позволяет изолировать и управлять расширениями в приложениях. MAF находится на более высоком уровне, чем MEF, и отвечает за изоляцию расширения, а также загрузку и выгрузку сборки, тогда как MEF отвечает за возможность обнаружения, расширяемости и переноса. Обе эти платформы тесно взаимодействуют друг с другом, и каждое одиночное приложение могут воспользоваться преимуществами их обоих.

## <a name="simplecalculator-an-example-application"></a>SimpleCalculator — пример приложения

Чтобы узнать о возможностях MEF, проще всего создать простое приложение MEF. В этом примере выполняется создание очень простого калькулятора, который называется SimpleCalculator. SimpleCalculator предназначен для создания консольного приложения, принимающего основные арифметические команды в формате «5 + 3» или «6 - 2» и возвращающего правильные ответы. Благодаря применению MEF, вы сможете добавлять новые операторы без изменения кода приложения.

Чтобы скачать полный исходный код для этого примера, см. раздел [Пример SimpleCalculator (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).

> [!NOTE]
> Пример с SimpleCalculator предназначен просто для демонстрации концепции и синтаксиса платформы MEF, а не описания реального сценария для ее использования. Многие приложения, которые будут использовать возможности MEF, являются более сложными, чем SimpleCalculator. Более сложные примеры см. в разделе [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) в GitHub.

- Чтобы приступить к работе, создайте проект консольного приложения в Visual Studio и назовите его `SimpleCalculator`.

- Добавьте ссылку на сборку `System.ComponentModel.Composition`, где находится MEF.

- Откройте *Module1.vb* или *Program.cs* и добавьте инструкции `Imports` или `using` для `System.ComponentModel.Composition` и `System.ComponentModel.Composition.Hosting`. Оба этих пространства имен содержат типы MEF, необходимые для разработки расширяемого приложения.

- Если вы используете Visual Basic, добавьте ключевое слово `Public` в строку, в которой объявляется модуль `Module1`.

## <a name="composition-container-and-catalogs"></a>Контейнер композиции и каталоги

Основным элементом модели композиции MEF является *контейнер композиции*, который содержит все доступные части и выполняет композицию. Композиция обеспечивает сопоставление импортируемых и экспортируемых элементов. Наиболее распространенным типом контейнера композиции является <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, который вы будете использовать для SimpleCalculator.

Если вы используете Visual Basic, добавьте открытый класс с именем `Program` в *Module1.vb*.

Добавьте следующую строку в класс `Program` в *Module1.vb* или *Program.cs*:

```vb
Dim _container As CompositionContainer
```

```csharp
private CompositionContainer _container;
```

Для обнаружения доступных частей в контейнерах композиции используется *каталог*. Каталог – это объект, который делает доступными части, обнаруженные в определенном источнике. MEF содержит каталоги для обнаружения частей с заданным типом, сборкой или директорией. Разработчики приложений могут легко создавать новые каталоги для обнаружения частей из других источников, например, веб-служб.

Добавьте следующий конструктор в класс `Program`:

```vb
Public Sub New()
    ' An aggregate catalog that combines multiple catalogs.
     Dim catalog = New AggregateCatalog()

    ' Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))

    ' Create the CompositionContainer with the parts in the catalog.
    _container = New CompositionContainer(catalog)

    ' Fill the imports of this object.
    Try
        _container.ComposeParts(Me)
    Catch ex As CompositionException
        Console.WriteLine(ex.ToString)
    End Try
End Sub
```

```csharp
private Program()
{
    // An aggregate catalog that combines multiple catalogs.
    var catalog = new AggregateCatalog();
    // Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));

    // Create the CompositionContainer with the parts in the catalog.
    _container = new CompositionContainer(catalog);

    // Fill the imports of this object.
    try
    {
        this._container.ComposeParts(this);
    }
    catch (CompositionException compositionException)
    {
        Console.WriteLine(compositionException.ToString());
   }
}
```

Вызов <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> указывает контейнеру композиции на необходимость компоновки определенного набора частей (в данном случае текущий экземпляр `Program`). Однако на этом этапе ничего не происходит, так как в `Program` нет импортируемых элементов для заполнения.

## <a name="imports-and-exports-with-attributes"></a>Импортируемые и экспортируемые элементы с атрибутами

Во-первых, необходимо выбрать `Program` для импорта калькулятора. Это позволит отделять вопросы пользовательского интерфейса, например, ввод и вывод консоли, который будет поступать в `Program`, от логики калькулятора.

Добавьте следующий код в класс `Program` :

```vb
<Import(GetType(ICalculator))>
Public Property calculator As ICalculator
```

```csharp
[Import(typeof(ICalculator))]
public ICalculator calculator;
```

Следует отметить, что объявление объекта `calculator` не является необычным, однако он содержит атрибут <xref:System.ComponentModel.Composition.ImportAttribute>. Этот атрибут объявляет что-нибудь, подлежащее импорту; то есть, это будет заполнено обработчиком композиции при составлении объекта.

Каждый импортируемый элемент имеет *контракт*, определяющий, с какими экспортируемыми элементами будет выполняться сопоставление. Контракт может быть явно заданный строкой, или он может создаваться автоматически платформой MEF из заданного типа (в данном случае интерфейс `ICalculator`). Любой экспортируемый элемент, объявленный с помощью контракта сопоставления, будет подставляться в этот импорт. Следует отметить, что типом объекта `calculator` на самом деле является `ICalculator`, это не является обязательным. Контракт не зависит от типа импортирующего объекта. (В этом случае можно опустить `typeof(ICalculator)`. MEF автоматически предположит, что контракт должен быть основан на типе импорта, если не указано явным образом.)

Добавьте этот простейший интерфейс в модуль или пространство имен `SimpleCalculator`:

```vb
Public Interface ICalculator
    Function Calculate(input As String) As String
End Interface
```

```csharp
public interface ICalculator
{
    String Calculate(String input);
}
```

Теперь, после определения `ICalculator`, нужен класс, который его реализует. Добавьте следующий класс в модуль или пространство имен `SimpleCalculator`:

```vb
<Export(GetType(ICalculator))>
Public Class MySimpleCalculator
   Implements ICalculator

End Class
```

```csharp
[Export(typeof(ICalculator))]
class MySimpleCalculator : ICalculator
{

}
```

Здесь используется экспортируемый элемент, соответствующий импортируемому элементу в `Program`. Чтобы экспортируемый элемент соответствовал импортируемому, экспорт должен иметь такой же контракт. Экспорт по контракту на основе `typeof(MySimpleCalculator)` вызовет несовпадение, и импортируемый элемент не будет заполнен; контракт должен в точности совпадать.

Так как контейнер композиции будет заполняться всеми доступными в этой сборке частями, часть `MySimpleCalculator` будет доступна. Когда конструктор для `Program` выполняет композицию для объекта `Program`, его импортируемый элемент будет заполняться объектом `MySimpleCalculator`, который будет создан для этой цели.

Для уровня пользовательского интерфейса (`Program`) никакая другая информация не требуется. Таким образом, можно заполнить остальную часть логики интерфейса пользователя в методе `Main`.

Добавьте следующий код в метод `Main`:

```vb
Sub Main()
    ' Composition is performed in the constructor.
    Dim p As New Program()
    Dim s As String
    Console.WriteLine("Enter Command:")
    While (True)
        s = Console.ReadLine()
        Console.WriteLine(p.calculator.Calculate(s))
    End While
End Sub
```

```csharp
static void Main(string[] args)
{
    // Composition is performed in the constructor.
    var p = new Program();
    string s;
    Console.WriteLine("Enter Command:");
    while (true)
    {
        s = Console.ReadLine();
        Console.WriteLine(p.calculator.Calculate(s));
    }
}
```

 Этот код просто считывает строку входных данных и вызывает функцию `Calculate` калькулятора `ICalculator` с результатом, который он записывает в консоль. То есть, весь код, требуемый в `Program`. Все остальные действия будут выполняться по частям.

## <a name="further-imports-and-importmany"></a>Дополнительные импортируемые элементы и атрибут ImportMany

Чтобы приложение SimpleCalculator было расширяемым, оно должно импортировать список операций. Обычный атрибут <xref:System.ComponentModel.Composition.ImportAttribute> заполняется одним и только одним <xref:System.ComponentModel.Composition.ExportAttribute>. Если имеется несколько значений, обработчик композиции выдаст ошибку. Чтобы создать импортируемый элемент, который может заполняться произвольным количеством экспортируемых элементов, можно использовать атрибут <xref:System.ComponentModel.Composition.ImportManyAttribute>.

Добавьте в класс `MySimpleCalculator` следующее свойство операций:

```vb
<ImportMany()>
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))
```

```csharp
[ImportMany]
IEnumerable<Lazy<IOperation, IOperationData>> operations;
```

<xref:System.Lazy%602> — это тип, задаваемый платформой MEF для сохранения косвенных ссылок на экспортируемые элементы. Здесь, кроме самого экспортируемого объекта, вы также получаете *метаданные экспорта* или информацию, описывающую экспортируемый объект. Каждый <xref:System.Lazy%602> содержит объект `IOperation`, представляющий собой фактическую операцию, и объект `IOperationData`, представляющий ее метаданные.

Добавьте следующие простые интерфейсы в модуль или пространство имен `SimpleCalculator`:

```vb
Public Interface IOperation
    Function Operate(left As Integer, right As Integer) As Integer
End Interface

Public Interface IOperationData
    ReadOnly Property Symbol As Char
End Interface
```

```csharp
public interface IOperation
{
     int Operate(int left, int right);
}

public interface IOperationData
{
    Char Symbol { get; }
}
```

 В этом случае метаданными для каждой операции является символ, представляющий данную операцию, например, +, -, \* и т. д. Чтобы сделать доступной операцию сложения, добавьте следующий класс в модуль или пространство имен `SimpleCalculator`:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "+"c)>
Public Class Add
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left + right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '+')]
class Add: IOperation
{
    public int Operate(int left, int right)
    {
        return left + right;
    }
}
```

Атрибут <xref:System.ComponentModel.Composition.ExportAttribute> функционирует так же, как и раньше. Атрибут <xref:System.ComponentModel.Composition.ExportMetadataAttribute> присоединяет метаданные к данному экспортируемому элементу в виде пары "имя значение". Если `Add` реализует `IOperation`, то класс, реализующий `IOperationData`, явным образом не определен. Вместо этого, он создается неявным образом платформой MEF со свойствами на основе имен предоставленных метаданных. (Это один из нескольких способов доступа к метаданным в MEF.)

Композиция на платформе MEF является *рекурсивной*. Вы явным образом составили композицию объекта `Program`, импортировавшего `ICalculator`, который получил тип `MySimpleCalculator`. `MySimpleCalculator`, в свою очередь, импортирует коллекцию объектов `IOperation`, и данный импорт будет заполнен при создании `MySimpleCalculator`, одновременно с импортируемыми элементами `Program`. Если `Add` класс объявил дополнительный импортируемый элемент, он тоже должен быть заполнен, и т. д. Любой незаполненный импорт будет вызывать ошибку композиции. (Однако можно объявить, что импортируемые элементы являются необязательными, или присвоить им значения по умолчанию.)

## <a name="calculator-logic"></a>Логика калькулятора

При наличии всех этих частей все, что остается, представляет собой саму логику калькулятора. Добавьте следующий код в класс `MySimpleCalculator` для реализации метода `Calculate`:

```vb
Public Function Calculate(input As String) As String Implements ICalculator.Calculate
    Dim left, right As Integer
    Dim operation As Char
    ' Finds the operator.
    Dim fn = FindFirstNonDigit(input)
    If fn < 0 Then
        Return "Could not parse command."
    End If
    operation = input(fn)
    Try
        ' Separate out the operands.
        left = Integer.Parse(input.Substring(0, fn))
        right = Integer.Parse(input.Substring(fn + 1))
    Catch ex As Exception
        Return "Could not parse command."
    End Try
    For Each i As Lazy(Of IOperation, IOperationData) In operations
        If i.Metadata.symbol = operation Then
            Return i.Value.Operate(left, right).ToString()
        End If
    Next
    Return "Operation not found!"
End Function
```

```csharp
public String Calculate(string input)
{
    int left;
    int right;
    char operation;
    // Finds the operator.
    int fn = FindFirstNonDigit(input); 
    if (fn < 0) return "Could not parse command.";

    try
    {
        // Separate out the operands.
        left = int.Parse(input.Substring(0, fn));
        right = int.Parse(input.Substring(fn + 1));
    }
    catch
    {
        return "Could not parse command.";
    }

    operation = input[fn];

    foreach (Lazy<IOperation, IOperationData> i in operations)
    {
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();
    }
    return "Operation Not Found!";
}
```

Начальные действия анализируют входную строку по левому и правому операндам, а также символ оператора. В цикле `foreach` анализируется каждый член коллекции `operations`. Эти объекты относятся к типу <xref:System.Lazy%602>, а доступ к значениям их метаданных и экспортируемому объекту можно получить с помощью, соответственно, свойств <xref:System.Lazy%602.Metadata%2A> и <xref:System.Lazy%601.Value%2A>. В этом случае, если обнаружено, что свойство `Symbol` объекта `IOperationData` совпадает, калькулятор вызывает метод `Operate` объекта `IOperation` и возвращает результат.

Для завершения работы над калькулятором также нужен вспомогательный метод, который возвращает позицию первого нецифрового символа в строке. Добавьте в класс `MySimpleCalculator` следующий вспомогательный метод:

```vb
Private Function FindFirstNonDigit(s As String) As Integer
    For i = 0 To s.Length - 1
        If Not Char.IsDigit(s(i)) Then Return i
    Next
    Return -1
End Function
```

```csharp
private int FindFirstNonDigit(string s)
{
    for (int i = 0; i < s.Length; i++)
    {
        if (!Char.IsDigit(s[i])) return i;
    }
    return -1;
}
```

Теперь вы должны получить возможность скомпилировать и запустить проект. В Visual Basic убедитесь, что вы добавили ключевое слово `Public` в `Module1`. В окне консоли введите операцию сложения, например "5 + 3", и калькулятор вернет результат. Любой другой оператор вернет сообщение "Operation Not Found" (Операция не найдена). !".

## <a name="extending-simplecalculator-using-a-new-class"></a>Расширение приложения SimpleCalculator с помощью нового класса

Теперь, когда калькулятор работает, добавление новой операции является простой задачей. Добавьте следующий класс в модуль или пространство имен `SimpleCalculator`:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "-"c)>
Public Class Subtract
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left - right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '-')]
class Subtract : IOperation
{
    public int Operate(int left, int right)
    {
        return left - right;
    }
}
```

Скомпилируйте и запустите проект. Выполните операцию вычитания, например, "5 - 3". Теперь калькулятор выполняет операции вычитания наряду со сложением.

## <a name="extending-simplecalculator-using-a-new-assembly"></a>Расширение приложения SimpleCalculator с помощью новой сборки

Процедура добавления классов в исходный код является довольно простой, но MEF позволяет искать части за пределами исходного кода приложения. Чтобы продемонстрировать это, необходимо изменить приложение SimpleCalculator для поиска в каталоге, а также в его собственной сборке, частей путем добавления <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.

Добавьте новый каталог с именем `Extensions` в проект SimpleCalculator. Убедитесь, что добавление выполняется на уровне проекта, а не на уровне решения. Затем добавьте новый проект библиотеки классов в решение с именем `ExtendedOperations`. Новый проект будет скомпилирован в отдельную сборку.

Откройте конструктор свойств проекта для проекта ExtendedOperations и перейдите на вкладку **Компиляция** или **Сборка**. Измените значение в поле **Выходной путь сборки** или **Выходной путь** так, чтобы оно указывало на каталог расширений в каталоге проекта SimpleCalculator ( *..\SimpleCalculator\Extensions\\* ).

 В *Module1.vb* или *Program.cs* добавьте следующую строку в конструктор `Program`:

```vb
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))
```

```csharp
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));
```

Замените пример пути на путь к каталогу расширений. (Этот абсолютный путь используется только для отладки. В реальном приложении будет использоваться относительный путь.) <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> добавит все части, найденные в сборках в каталоге расширений, в контейнер композиции.

В проекте ExtendedOperations добавьте ссылки на приложение SimpleCalculator и System.ComponentModel.Composition. В файле класса ExtendedOperations добавьте оператор `Imports` или `using` для System.ComponentModel.Composition. В Visual Basic также добавьте оператор `Imports` для SimpleCalculator. Затем добавьте следующий класс в файл класса ExtendedOperations:

```vb
<Export(GetType(SimpleCalculator.IOperation))>
<ExportMetadata("Symbol", "%"c)>
Public Class Modulo
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left Mod right
    End Function
End Class
```

```csharp
[Export(typeof(SimpleCalculator.IOperation))]
[ExportMetadata("Symbol", '%')]
public class Mod : SimpleCalculator.IOperation
{
    public int Operate(int left, int right)
    {
        return left % right;
    }
}
```

Следует отметить, что для совпадения контрактов атрибут <xref:System.ComponentModel.Composition.ExportAttribute> должен иметь тот же тип, что и <xref:System.ComponentModel.Composition.ImportAttribute>.

Скомпилируйте и запустите проект. Проверьте новый оператор Mod (%).

## <a name="conclusion"></a>Заключение

В этом разделе рассмотрены основные концепции платформы MEF.

- Части, каталоги и контейнер композиции

     Части и контейнер композиции являются базовыми строительными блоками приложения MEF. Часть — это любой объект, который импортирует или экспортирует значение, вплоть до самого себя. Каталог содержит коллекцию частей из определенного источника. Контейнер композиции использует части, предоставленные каталогом для выполнения композиции, привязки импортируемых и экспортируемых элементов.

- Импортируемые и экспортируемые элементы

     Импортируемые и экспортируемые элементы позволяют компонентам взаимодействовать друг с другом. При импорте компонент указывает на необходимость в определенном значении или объекте, а при экспорте он указывает на доступность значения. Каждый импортируемый элемент сопоставляется со списком экспортируемых элементов при помощи своего контракта.

## <a name="next-steps"></a>Следующие шаги

Чтобы скачать полный исходный код для этого примера, см. раздел [Пример SimpleCalculator (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).

 Дополнительные сведения и примеры кода см. в разделе [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef). Список типов MEF см. в пространстве имен <xref:System.ComponentModel.Composition?displayProperty=nameWithType>.
