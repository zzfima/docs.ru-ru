---
title: Учебник. Создание средства для анализа и исправления кода
description: В этом руководстве описано, как создать анализатор и исправление кода с помощью пакета SDK для .NET Compiler Platform (API Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: f6fc21c010f9b5fcd5e709ef822639c020a7c93b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240554"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a>Учебник. Создание средства для анализа и исправления кода

Пакет SDK для .NET Compiler Platform предоставляет инструменты для создания пользовательских предупреждений для кода C# или Visual Basic. **Анализатор** содержит код, который распознает нарушения правила. **Исправление кода** содержит код, который исправляет эти нарушения. Правилами, которые вы реализуете, может быть что угодно — от структуры кода до его стиля или соглашений об именовании и многое другое. .NET Compiler Platform предоставляет платформу для выполнения анализа во время написания кода, а также все функции пользовательского интерфейса Visual Studio для отладки, включая отображение волнистых линий в редакторе, вывод списка ошибок в Visual Studio и отображение значка лампочки, указывающего на наличие предложений и предлагаемых исправлений.

В этом руководстве описано, как создать **анализатор** и соответствующее **исправление кода** с помощью API Roslyn. Анализатор выполняет анализ исходного кода и сообщает о проблеме пользователю. При необходимости анализатор может предложить соответствующее исправление для исходного кода пользователя. В этом руководстве описано, как создать анализатор, ищущий локальные переменные, которые можно объявить с помощью модификатора `const`, но которые не объявлены. Сопутствующее исправление кода добавляет модификатор `const` в эти объявления.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [Visual Studio 2019](https://www.visualstudio.com/downloads)

Необходимо установить **пакет SDK для .NET Compiler Platform** через Visual Studio Installer:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

Создать и проверить анализатор можно несколькими способами:

1. Создайте решение.
1. Зарегистрируйте имя и описание анализатора.
1. Создайте отчет анализатора о предупреждениях и рекомендациях.
1. Внедрите исправление кода, чтобы принимать рекомендации.
1. Улучшите анализ с помощью модульных тестов.

## <a name="explore-the-analyzer-template"></a>Изучение шаблона анализатора

Анализатор сообщает пользователю о любых объявлениях локальной переменной, которые можно преобразовать в локальные константы. Рассмотрим следующий пример кода:

```csharp
int x = 0;
Console.WriteLine(x);
```

В приведенном выше коде `x` присваивается значение константы, которое никогда не меняется. Ее можно объявить с помощью модификатора `const`:

```csharp
const int x = 0;
Console.WriteLine(x);
```

Чтобы определить, можно ли изменить переменную на константу, используется синтаксический анализ, анализ константы из выражения инициализатора, а также анализ потока данных, чтобы убедиться, что переменная не записана. .NET Compiler Platform предоставляет API для упрощения такого анализа. Сначала нужно создать новый проект C# **анализатора с исправлением кода**.

- В Visual Studio последовательно выберите **Файл > Создать > Проект**, чтобы открыть диалоговое окно "Новый проект".
- В разделе **Visual C# > Расширяемость** выберите **Analyzer with code fix (.NET Standard)** (Анализатор с исправлением кода (.NET Standard)).
- Присвойте проекту имя **MakeConst** и нажмите кнопку "ОК".

Анализатор с шаблоном исправления кода создаст три проекта: один содержит анализатор и исправление кода, второй — проект модульного теста и третий — проект VSIX. Запускаемым проектом по умолчанию является проект VSIX. Нажмите клавишу **F5**, чтобы запустить проект VSIX. Это запустит второй экземпляр Visual Studio с загруженным в него анализатором.

> [!TIP]
> Когда вы запустите анализатор, откроется вторая копия Visual Studio. Эта вторая копия использует другой куст реестра для хранения параметров, что позволяет различить параметры визуальных элементов в обоих копиях Visual Studio. Вы можете выбрать другую тему для экспериментального запуска Visual Studio. Кроме того, не следует перемещать параметры или выполнять вход в учетную запись Visual Studio в экспериментальном экземпляре Visual Studio. Так параметры останутся разными.

Во втором экземпляре Visual Studio, который вы только что создали, создайте проект C# консольного приложения (это может быть как проект .NET Core, так и .NET Framework, так как анализаторы работают на уровне источника). Наведите указатель мыши на токен с волнистым подчеркиванием. Появится текст предупреждения от анализатора.

Шаблон создает анализатор, который выдает предупреждение на каждое объявление типа, где имя типа состоит из букв нижнего регистра, как показано ниже:

![Предупреждение от анализатора](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

Также шаблон содержит исправление кода, которое меняет любые буквы нижнего регистра в имени типа на буквы верхнего регистра. Предлагаемые исправления можно просмотреть, щелкнув значок лампочки рядом с предупреждением. После принятия изменений имя типа и все ссылки на этот тип будут обновлены. Теперь, когда вы увидели работу начального анализатора, закройте второй экземпляр Visual Studio и вернитесь к проекту анализатора.

Для тестирования изменений в анализаторе не требуется каждый раз запускать вторую копию Visual Studio, так как шаблон создает проект модульного теста. В этом проекте содержатся два теста. `TestMethod1` показывает обычный формат теста, при котором анализ кода происходит без активации диагностики. `TestMethod2` — формат, при котором сначала активируется диагностика, а затем применяется исправление кода. Во время сборки анализатора и исправления кода вы напишете тесты для проверки разных структур. Модульные тесты проводятся гораздо быстрее, чем интерактивное тестирование анализаторов в Visual Studio.

> [!TIP]
> Модульные тесты анализатора — отличный инструмент, если вы знаете, какие конструкции кода должны и не должны запускать анализатор. В свою очередь запуск анализатора в другой копии Visual Studio позволяет определить и найти конструкции, о которых вы еще не задумывались.

## <a name="create-analyzer-registrations"></a>Регистрация анализатора

В файле **MakeConstAnalyzer.cs** с помощью шаблона создается начальный класс `DiagnosticAnalyzer`. В этом начальном анализаторе отображены два важных свойства каждого анализатора.

- В каждом диагностическом анализаторе должен быть указан атрибут `[DiagnosticAnalyzer]`, который описывает язык, на котором он работает.
- Каждый диагностический анализатор должен наследоваться от класса <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.

Также в шаблоне отображены базовые функции любого анализатора:

1. Регистрация действий. Действия представляют изменения кода, которые запускают анализатор для проверки нарушений. Когда Visual Studio обнаруживает изменения в коде, которые соответствуют зарегистрированному действию, происходит вызов зарегистрированного метода.
1. Создание диагностики. Обнаружив нарушения, анализатор создает объект диагностики, с помощью которого Visual Studio уведомляет пользователя об этом нарушении.

Действия регистрируются в переопределении метода <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>. При работе с этим руководстве вы просмотрите **синтаксические узлы** локальных объявлений и узнаете, какие из них имеют значения констант. Если объявление может быть константой, анализатор создаст диагностику и сформирует отчет.

Сначала обновите константы регистрации и метод `Initialize`, так как константы определяют ваш анализатор MakeConst. Большинство строковых констант определены в файле строковых ресурсов. Используйте их, чтобы упростить локализацию. Откройте файл **Resources.resx** для проекта анализатора **MakeConst**. Откроется редактор ресурсов. Измените строковые ресурсы, как показано ниже:

- Компонент `AnalyzerTitle` измените на Variable can be made constant (Переменная может быть константой).
- Компонент `AnalyzerMessageFormat` измените на Can be made constant (Может быть константой).
- Компонент `AnalyzerDescription` измените на Make Constant (Сделать константой).

Также измените раскрывающийся список **модификатора доступа** на `public`. Это упростит использование этих констант в модульных тестах. После настройки редактор ресурсов будет иметь следующий вид:

![Обновление строковых ресурсов](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

Остальные изменения будут в файле анализатора. Откройте файл **MakeConstAnalyzer.cs** в Visual Studio. Измените зарегистрированное действие на символы на действие на синтаксис. В методе `MakeConstAnalyzerAnalyzer.Initialize` найдите строку с действием на символы:

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

Замените ее приведенным ниже кодом:

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

После этого метод `AnalyzeSymbol` можно удалить. Этот анализатор проверяет <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, а не операторы <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>. Обратите внимание на то, что `AnalyzeNode` подчеркивается красной волнистой линией, так как код, который вы только что вставили, ссылается на метод `AnalyzeNode`, который еще не объявлен. Объявите этот метод, используя приведенный ниже код:

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

В файле **MakeConstAnalyzer.cs** измените `Category` на Usage (Использование), как показано ниже:

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a>Поиск локальных объявлений, которые могут быть константами

Теперь мы напишем первую версию метода `AnalyzeNode`. Он должен найти одно локальное объявление, которое может быть `const`, но таковым не является. Пример приведен ниже:

```csharp
int x = 0;
Console.WriteLine(x);
```

Сначала найдите локальные объявления. Добавьте приведенный ниже код в `AnalyzeNode` в файле **MakeConstAnalyzer.cs**:

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

Это приведение всегда завершается успешно, так как ваш анализатор зарегистрирован для отслеживания изменений только локальных объявлений. Другие типы узлов не вызывают метод `AnalyzeNode`. Затем проверьте объявление на наличие модификаторов `const`. Если они есть, сразу же выполните возврат. Приведенный ниже код ищет модификаторы `const` в локальном объявлении:

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

В конце проверьте, может ли переменная быть `const`. Это означает, что она не может быть назначена после инициализации.

Выполните семантический анализ с помощью <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>. Используйте аргумент `context`, чтобы определить, можно ли объявление локальной переменной сделать `const`. <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> представляет все семантические сведения в одном исходном файле. См. дополнительные сведения о [семантических моделях](../work-with-semantics.md). С помощью <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> выполните анализ потока данных на операторе локального объявления. Затем, используя результаты этого анализа потока данных, убедитесь, что в локальную переменную не записывается новое значение где-либо еще. Вызовите метод расширения <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A>, чтобы извлечь <xref:Microsoft.CodeAnalysis.ILocalSymbol> переменной и убедиться, что она не содержится в коллекции <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> из анализа потока данных. Добавьте в конце метода `AnalyzeNode` приведенный ниже код:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

Этот код гарантирует, что переменная не изменена и может быть `const`. Теперь мы активируем диагностику. Добавьте приведенный ниже код в последнюю строку метода `AnalyzeNode`:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

Чтобы проверить состояние, запустите анализатор, нажав клавишу **F5**. Загрузите консольное приложение, созданное ранее, и добавьте приведенный ниже код теста:

```csharp
int x = 0;
Console.WriteLine(x);
```

Появится лампочка и анализатор выдаст отчет с диагностическими сведениями. При этом поведение лампочки по-прежнему основано на исправлении кода, сгенерированном шаблоном, указывая на то, что можно использовать буквы верхнего регистра. В следующем разделе показано, как написать исправление кода.

## <a name="write-the-code-fix"></a>Написание исправления кода

Анализатор поддерживает одно или несколько исправлений кода. Исправление кода определяет, какие правки нужно внести для решения обнаруженной проблемы. Исправление кода вашего анализатора предоставляет код с ключевым словом const:

```csharp
const int x = 0;
Console.WriteLine(x);
```

Пользователь выбирает исправление в интерфейсе лампочки в редакторе, а Visual Studio изменяет код.

Откройте файл **MakeConstCodeFixProvider.cs**, добавленный шаблоном.  Это исправление уже привязано к идентификатору диагностики вашего анализатора, но оно пока не реализует преобразование кода. Сначала удалите часть кода шаблона. Измените строку заголовка на Make constant (Сделать константой):

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

Затем удалите метод `MakeUppercaseAsync`. Он больше не применяется.

Все поставщики исправлений кода являются производными от <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>. и переопределяют <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> на сообщение о доступных исправлениях. В <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> измените тип узла-предка на `RegisterCodeFixesAsync` в соответствии с диагностикой:

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

Затем, чтобы зарегистрировать исправление кода, измените последнюю строку. Исправление создаст документ, полученный после добавления модификатора `const` к существующему объявлению:

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

Под символом `MakeConstAsync` появятся красные волнистые линии. Добавьте объявление в `MakeConstAsync`, например как указано ниже:

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

Новый метод `MakeConstAsync` преобразует <xref:Microsoft.CodeAnalysis.Document> исходного файла пользователя в новый экземпляр <xref:Microsoft.CodeAnalysis.Document>, содержащий объявление `const`.

Создайте новый токен ключевого слова `const` и вставьте его перед оператором объявления. Не забудьте сначала удалить все элементы trivia из первого оператора объявления и подключить к токену `const`. Добавьте следующий код в метод `MakeConstAsync`:

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

Затем добавьте токен `const` к объявлению с помощью приведенного ниже кода:

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

Отформатируйте новое объявление в соответствии с правилами форматирования C#. Форматирование изменений в соответствии с существующим кодом упрощает работу. Добавьте приведенный ниже оператор сразу после существующего кода:

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

Для выполнения этого кода требуется новое пространство имен. Добавьте следующий оператор `using` в начало файла:

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

В конце нужно внести правки. Для этого выполните эти три шага:

1. Получите дескриптор существующего документа.
1. Создайте документ, заменив существующее объявление на новое.
1. Верните новый документ.

Добавьте в конце метода `MakeConstAsync` приведенный ниже код:

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

Ваше исправление кода готово.  Нажмите клавишу F5, чтобы запустить проект анализатора во втором экземпляре Visual Studio. Во втором экземпляре Visual Studio создайте проект C# консольного приложения и добавьте несколько объявлений локальной переменной, инициализированных со значениями константы в методе main. Они будут отмечены как предупреждения. См. пример ниже.

![Предупреждение о назначении константы](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

Мы уже много сделали. Объявления, которые могут быть `const`, подчеркнуты волнистой линией. Но нам еще нужно с ними поработать. Здесь следует добавить `const` в объявления `i`, затем `j` и `k`. Но если вы добавите модификатор `const` в обратном порядке, начиная с `k`, анализатор выдаст ошибки: `k` не может быть объявлен как `const`, пока `i` и `j` не являются `const`. Нужно выполнить дополнительный анализ, чтобы убедиться, что переменные можно объявить и инициализировать различными путями.

## <a name="build-data-driven-tests"></a>Выполнение теста, управляемого данными

Анализатор и исправление кода работают на простом примере одного объявления, которое может быть константой. Есть множество возможных операторов объявления, где они выдают ошибки. В этих ситуациях можно обратиться к библиотеке модульных тестов, созданной шаблоном. Это гораздо быстрее, чем каждый раз запускать вторую копию Visual Studio.

Откройте файл **MakeConstUnitTests.cs** в проекте модульного теста. В нем созданы два теста по общим шаблонам для анализатора и для модульного теста исправления кода. Метод `TestMethod1` гарантирует, что анализатор не выдаст отчет о диагностике, когда это не нужно. Метод `TestMethod2` выдает отчет о диагностике и запускает исправление кода.

Код почти каждого теста вашего анализатора работает по одному из этих шаблонов. Сначала переделайте эти тесты в тесты, управляемые данными. Так будет проще создавать новые тесты, добавляя новые строковые константы для представления различных входных данных.

Для повышения эффективности сначала выполните рефакторинг двух тестов в тесты, управляемые данными. Затем можно определять несколько строковых констант для каждого нового теста. Во время рефакторинга переименуйте оба метода. Замените `TestMethod1` тестом, который гарантирует отсутствие диагностики:

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

Вы можете создать новую строку данных для теста. Для этого определите фрагмент кода, который не должен вызывать предупреждение диагностики. Эта перегрузка `VerifyCSharpDiagnostic` передается, если для фрагмента исходного кода диагностика не вызывалась.

Затем замените `TestMethod2` этим тестом, который гарантирует вызов диагностики, а также то, что исправление применяется к этому фрагменту исходного кода:

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

Приведенный выше код также вносит изменения в код, который компилирует ожидаемый результат диагностики. Для этого используются открытые константы, зарегистрированные в анализаторе `MakeConst`. Также используются две строковые константы для введенного и исправленного источника. Добавьте приведенные ниже строковые константы в класс `UnitTest`:

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

Чтобы убедиться в том, что они переданы, запустите оба теста. Откройте **обозреватель тестов** в Visual Studio, последовательно выбрав **Тест** > **Windows** > **Обозреватель тестов**.  Щелкните ссылку **Выполнить все**.

## <a name="create-tests-for-valid-declarations"></a>Создание тестов для допустимых объявлений

Как правило, анализаторы должны завершать работу как можно быстрее, выполняя минимум операций. Когда пользователь правит код, Visual Studio вызывает зарегистрированные анализаторы. Основным требованием здесь является скорость реагирования. Существует несколько тестовых случаев для кода, который не должен вызывать диагностику. Анализатор уже обрабатывает один из них — тот, при котором переменная присваивается после инициализации. Чтобы воспроизвести этот случай, добавьте приведенную ниже строковую константу в тест:

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

Затем добавьте строку данных, как показано во фрагменте ниже:

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Этот тест также проходит. Далее добавьте константы для условий, которые еще не обработаны:

- Объявления, которые представляют `const`, так как они уже являются константами:

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- Объявления, у которых нет инициализатора, так как нет соответствующего значения:

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- Объявления, у которых инициализатор не является константой, так как они не могут быть константами времени компиляции:

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

Трудность заключается еще в том, что в C# допускается несколько объявлений, работающих как один оператор. Рассмотрите приведенную ниже строковую константу тестового случая:

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

Переменная `i` может быть константой, а переменная `j` — нет. Поэтому этот оператор не может быть объявлением константы. Добавьте объявления `DataRow` для всех тестов:

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Снова запустите тесты. Произойдет сбой в новых тестовых случаях.

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a>Обновление анализатора для пропуска верных объявлений

Чтобы отфильтровать код, который соответствует условиям, необходимо преобразовать метод `AnalyzeNode` анализатора. Эти условия связаны между собой, и изменения в одном из них будут применены ко всем. Внесите следующие изменения в `AnalyzeNode`:

- Для объявления одной переменной был выполнен семантический анализ. Этот код должен находиться в цикле `foreach`, который проверяет все переменные, объявленные в одном и том же операторе.
- Каждая объявленная переменная должна иметь инициализатор.
- Каждый инициализатор переменной должен быть константой времени компиляции.

В методе `AnalyzeNode` замените исходный семантический анализ:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

приведенным ниже фрагментом кода:

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

Первый цикл `foreach` проверяет каждое объявление переменной с помощью синтаксического анализа. В первой проверке подтверждается наличие инициализатора. Во второй — что этот инициализатор является константой. Во втором цикле запускается исходный семантический анализ. Семантические проверки проходят в отдельных циклах, так как они серьезно влияют на производительность. Снова запустите тест. Все проверки должны быть пройдены.

## <a name="add-the-final-polish"></a>Финальные штрихи

Вы почти у цели. Анализатор должен обработать еще несколько условий. Пока пользователь пишет код, Visual Studio вызывает анализаторы. Часто бывает так, что анализатор вызван для кода, который не компилируется. Метод `AnalyzeNode` диагностического анализатора не проверяет, можно ли преобразовать значение константы в тип переменной. Поэтому в текущей реализации все неверные объявления, такие как int i = "abc", преобразуются в локальные константы. Добавьте исходную строковую константу в это условие:

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

Кроме того, ссылочные типы обрабатываются неправильно. Единственное допустимое значение константы для ссылочного типа — `null`, кроме случаев с <xref:System.String?displayProperty=nameWithType>, в которых работают строковые литералы. Другими словами, `const string s = "abc"` является допустимым, а `const object s = "abc"` — нет. Этот фрагмент кода проверяет это условие:

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

Чтобы убедиться в том, что можно создать объявление константы для строки, добавьте еще один тест. В приведенным ниже фрагменте кода определен как код, вызывающий диагностику, так и код после исправления:

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

Если переменная объявлена с ключевым словом `var`, исправление выдает объявление `const var`, которое не поддерживается в C#. Чтобы исправить эту ошибку, исправление должно заменить ключевое слово `var` именем выведенного типа:

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

Эти изменения обновят объявления строк данных для обоих тестов. В приведенном ниже коде показаны тесты со всеми атрибутами строк данных:

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

К счастью, все вышеперечисленные ошибки можно устранить с помощью методов, которые вы только что изучили.

Чтобы исправить первую ошибку, сначала откройте файл **DiagnosticAnalyzer.cs** и найдите цикл foreach, в котором проверяются инициализаторы локальных объявлений. Им должны быть назначены значения констант. Сразу же, _до_ выполнения цикла foreach, вызовите `context.SemanticModel.GetTypeInfo()`, чтобы извлечь подробные сведения об объявленном типе из локального объявления:

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

Затем проверьте каждый инициализатор внутри цикла `foreach`, чтобы убедиться в том, что его можно преобразовать в тип переменной. Убедившись в том, что инициализатор является константой, добавьте приведенную ниже проверку:

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

Следующее изменение основано на последнем. Перед закрывающей фигурной скобкой первого цикла foreach добавьте приведенный ниже код. Он проверит тип локального объявления, когда константа является строкой или имеет значение null.

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

Необходимо заменить ключевое слово var правильным именем типа в вашем поставщике исправлений кода. Вернитесь к файлу **CodeFixProvider.cs**. Код, который вы добавите, выполняет следующие шаги:

- Проверяет, является ли объявление `var`, если да:
- Создает тип для выводимого типа.
- Проверяет, что объявление типа не является псевдонимом. Если это так, можно объявить `const var`.
- Проверяет, что `var` не является именем типа в программе (если это так, `const var` является допустимым).
- Упрощает полное имя типа.

Кажется, что здесь довольно много кода. Но это не так. Замените строку, которая объявляет и инициализирует `newLocal` приведенным ниже кодом. Он выполняется сразу после инициализации `newModifiers`:

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

Чтобы использовать тип <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>, потребуется добавить один оператор `using`:

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

Запустите тесты. Они все должны быть пройдены. Можете поздравить себя, запустив готовый анализатор. Чтобы запустить проект анализатора во втором экземпляре Visual Studio с загруженным расширением предварительной версии Roslyn, нажмите клавиши Ctrl+F5.

- Во втором экземпляре Visual Studio создайте новый проект C# консольного приложения и добавьте `int x = "abc";` в метод main. Так как первая ошибка была исправлена, для объявления локальной переменной не должно выдаваться предупреждение (хотя есть ошибка компилятора, как и предполагалось).
- Затем добавьте `object s = "abc";` в метод main. Так как вторая ошибка была исправлена, не должно быть никаких предупреждений.
- Наконец, добавьте другую локальную переменную, использующую ключевое слово `var`. Внизу слева появится предупреждение и предложение исправлений.
- Наведите курсор редактора на волнистую линию и нажмите клавиши Ctrl+. Отобразятся предложенные исправления. Обратите внимание, что после выбора исправления ключевое слово var теперь обрабатывается правильно.

В конце добавьте приведенный ниже код:

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

После этого только две переменные будут подчеркнуты красными волнистыми линиями. Добавьте `const` в `i` и `j`. Появится предупреждение, указывающее на то, что `k` может быть `const`.

Поздравляем! Вы создали свое первое расширение .NET Compiler Platform, которое выполняет анализ кода в режиме реального времени, находит проблемы и быстро их исправляет. Кроме того, вы изучили множество API, входящих в пакет SDK .NET Compiler Platform (API Roslyn). Вы можете сравнить результат своей работы с [готовым примером](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) в нашем репозитории в GitHub.

## <a name="other-resources"></a>Другие источники

- [Начало работы с функциями синтаксического анализа](../get-started/syntax-analysis.md)
- [Начало работы с семантическим анализом](../get-started/semantic-analysis.md)
