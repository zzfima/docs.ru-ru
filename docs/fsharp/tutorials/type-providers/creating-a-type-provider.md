---
title: Учебник. Создание поставщика типов
description: Узнайте, как создавать собственные F# поставщики типов в F# 3,0, изучив несколько поставщиков простых типов, чтобы продемонстрировать основные понятия.
ms.date: 11/04/2019
ms.openlocfilehash: 8df893669b8ee04bad366dbe42a55c83d1f5a8fe
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968374"
---
# <a name="tutorial-create-a-type-provider"></a>Учебник. Создание поставщика типов

Механизм поставщика типов в F# является важной частью поддержки многофункционального программирования информации. В этом учебнике объясняется, как создавать собственные поставщики типов, проследуя разработку нескольких поставщиков простых типов, чтобы продемонстрировать основные понятия. Дополнительные сведения о механизме поставщика типов в см F#. в разделе [Поставщики типов](index.md).

F# Экосистема содержит ряд поставщиков типов для часто используемых служб Интернет-и корпоративных данных. Пример:

- [FSharp. Data](https://fsharp.github.io/FSharp.Data/) включает поставщики типов для форматов документов JSON, XML, CSV и HTML.

- [Дескриптора SqlProvider](https://fsprojects.github.io/SQLProvider/) обеспечивает строго типизированный доступ к базам данных SQL с помощью сопоставления объектов F# и запросов LINQ к этим источникам данных.

- [FSharp. Data. SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) имеет набор поставщиков типов для внедрения T-SQL во F#время компиляции.

- [FSharp. Data. TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) — это старый набор поставщиков типов для использования только с .NET Frameworkным программированием для доступа к службам данных SQL, Entity Framework, ODATA и WSDL.

При необходимости можно создавать пользовательские поставщики типов или ссылаться на поставщики типов, созданные другими пользователями. Например, в Организации может быть служба данных, предоставляющая большое и увеличивающееся количество именованных наборов данных, каждый из которых имеет собственную стабильную схему данных. Можно создать поставщик типов, который считывает схемы и представляет текущие наборы данных программисту строго типизированным способом.

## <a name="before-you-start"></a>Прежде чем начать

Механизм поставщика типов в основном предназначен для внедрения стабильных данных и пространств сведений о службе в процесс F# программирования.

Этот механизм не предназначен для внедрения информационных пространств, изменения схемы которых производятся во время выполнения программы, в целях, относящихся к логике программы. Кроме того, механизм не предназначен для мета-программирования внутри языка, хотя этот домен содержит некоторые допустимые варианты использования. Этот механизм следует использовать только в том случае, если это необходимо, а разработка поставщика типов дает очень высокое значение.

Не следует писать поставщик типов, если схема недоступна. Аналогично, следует избегать написания поставщика типов, где достаточно обычной (или даже существующей) библиотеки .NET.

Прежде чем начать, вы можете задать следующие вопросы:

- У вас есть схема для источника информации? Если да, то каково сопоставление в системе F# типов .NET и?

- Можно ли использовать существующий (динамически типизированный) API в качестве отправной точки для реализации?

- Будет ли ваша организация иметь достаточный объем использования поставщика типов, чтобы писать его целесообразным? Будет ли нормальная библиотека .NET соответствовать вашим потребностям?

- Сколько будет изменено в схеме?

- Будет ли оно изменяться во время кодирования?

- Будет ли он изменяться между сеансами кодирования?

- Будет ли оно изменяться во время выполнения программы?

Поставщики типов лучше всего подходят для ситуаций, когда схема является стабильной во время выполнения и в течение времени существования скомпилированного кода.

## <a name="a-simple-type-provider"></a>Поставщик простых типов

Этот пример — Samples. хелловорлдтипепровидер, аналогичный образцам в каталоге `examples` в [ F# пакете SDK поставщика типов](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Поставщик предоставляет доступ к "пространству типов", который содержит 100 удаленных типов, как показано в следующем примере кода с F# использованием синтаксиса Signature и пропуск сведений для всех, кроме `Type1`. Дополнительные сведения о стирании типов см. Далее в подразделе [сведения о стирании указанных типов](#details-about-erased-provided-types) .

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

Обратите внимание, что набор типов и членов является статически известным. Этот пример не использует возможности поставщиков для предоставления типов, зависящих от схемы. Реализация поставщика типов описана в следующем коде, а сведения приведены в последующих разделах этой статьи.

> [!WARNING]
> Между этим кодом и примерами в сети могут быть различия.

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

Чтобы использовать этот поставщик, откройте отдельный экземпляр Visual Studio, создайте F# скрипт, а затем добавьте ссылку на поставщик из скрипта с помощью #r, как показано в следующем коде:

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

Затем найдите типы в пространстве имен `Samples.HelloWorldTypeProvider`, созданном поставщиком типов.

Перед повторной компиляцией поставщика убедитесь, что закрыты все экземпляры Visual Studio и F# Interactive, использующие библиотеку DLL поставщика. В противном случае произойдет ошибка сборки, так как выходная библиотека DLL будет заблокирована.

Чтобы отладить этот поставщик с помощью инструкций Print, создайте сценарий, который предоставляет проблему с поставщиком, а затем используйте следующий код:

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Чтобы отладить этот поставщик с помощью Visual Studio, откройте Командная строка разработчика для Visual Studio с учетными данными администратора и выполните следующую команду:

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

В качестве альтернативы откройте Visual Studio, откройте меню Отладка, выберите `Debug/Attach to process…`и подключитесь к другому `devenv` процесса, в котором редактируется скрипт. С помощью этого метода можно легко ориентироваться на определенную логику в поставщике типов путем интерактивного ввода выражений во второй экземпляр (с полной технологией IntelliSense и другими функциями).

Можно отключить отладку Только мой код для лучшего обнаружения ошибок в созданном коде. Сведения о том, как включить или отключить эту функцию, см. [в разделе Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger). Кроме того, можно также задать перехват первого шанса исключений, открыв меню `Debug`, выбрав `Exceptions` или нажав клавиши CTRL + ALT + E, чтобы открыть диалоговое окно `Exceptions`. В этом диалоговом окне в разделе `Common Language Runtime Exceptions`установите флажок `Thrown`.

### <a name="implementation-of-the-type-provider"></a>Реализация поставщика типов

В этом разделе описываются основные разделы реализации поставщика типов. Сначала необходимо определить тип самого поставщика пользовательского типа:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Этот тип должен быть открытым, и его необходимо пометить атрибутом [типепровидер](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) , чтобы компилятор распознал поставщик типов, когда отдельный F# проект ссылается на сборку, содержащую тип. Параметр *config* является необязательным, и, если он F# имеется, содержит контекстные сведения о конфигурации для экземпляра поставщика типов, создаваемого компилятором.

Далее вы реализуете интерфейс [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) . В этом случае используется тип `TypeProviderForNamespaces` из API `ProvidedTypes` в качестве базового типа. Этот вспомогательный тип может предоставить конечную коллекцию предопределенных пространств имен, каждый из которых непосредственно содержит конечное количество фиксированных, предпредоставленных типов. В этом контексте поставщик *заранее* создает типы, даже если они не нужны или не используются.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Затем определите локальные закрытые значения, задающие пространство имен для указанных типов, и найдите саму сборку поставщика типов. В дальнейшем эта сборка используется как логический тип родительского объекта для указанных удаленных типов.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Затем создайте функцию для предоставления каждого типа Type1... Type100. Эта функция более подробно описана далее в этом разделе.

```fsharp
let makeOneProvidedType (n:int) = …
```

Затем создайте типы, предоставленные 100:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Затем добавьте типы в качестве предоставленного пространства имен:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Наконец, добавьте атрибут сборки, указывающий, что создается библиотека DLL поставщика типов:

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>Предоставление одного типа и его членов

Функция `makeOneProvidedType` выполняет реальную работу по предоставлению одного из типов.

```fsharp
let makeOneProvidedType (n:int) =
…
```

Этот шаг описывает реализацию этой функции. Сначала создайте предоставленный тип (например, тип1, если n = 1 или Type57, если n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Обратите внимание на следующие моменты:

- Указанный тип стерт.  Так как вы указываете, что базовый тип `obj`, экземпляры будут отображаться в виде значений типа [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) в скомпилированном коде.

- При указании невложенного типа необходимо указать сборку и пространство имен. Для удаленных типов сборка должна быть самой сборкой поставщика типов.

Затем добавьте XML-документацию в тип. Эта документация является отложенной, то есть вычисленной по запросу, если она требуется компилятору узла.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Далее вы добавите в тип предоставленное статическое свойство:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

При получении этого свойства всегда будет вычислена строка "Hello!". `GetterCode` для свойства использует F# предложение, представляющее код, формируемый компилятором хоста для получения свойства. Дополнительные сведения о предложениях см. в разделе [цитирование кодаF#()](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Добавьте XML-документацию в свойство.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Теперь присоедините предоставленное свойство к предоставленному типу. Необходимо присоединить предоставленный элемент к одному и только одному типу. В противном случае член никогда не будет доступен.

```fsharp
t.AddMember staticProp
```

Теперь создайте предоставленный конструктор, не принимающий параметров.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

`InvokeCode` для конструктора возвращает F# предложение, представляющее код, создаваемый компилятором хоста при вызове конструктора. Например, можно использовать следующий конструктор:

```fsharp
new Type10()
```

Экземпляр предоставленного типа будет создан с базовыми данными "данные объекта". Код в кавычках включает преобразование в [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) , так как этот тип является очистки данного предоставленного типа (как указано при объявлении предоставленного типа).

Добавьте XML-документацию в конструктор и добавьте предоставленный конструктор в предоставленный тип:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Создайте второй предоставленный конструктор, который принимает один параметр:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

`InvokeCode` для конструктора снова возвращает F# предложение, представляющее код, созданный компилятором узла для вызова метода. Например, можно использовать следующий конструктор:

```fsharp
new Type10("ten")
```

Экземпляр предоставленного типа создается с базовыми данными «десять». Возможно, вы уже заметили, что функция `InvokeCode` Возвращает предложение. Входными данными для этой функции является список выражений, по одному на каждый параметр конструктора. В этом случае выражение, представляющее одно значение параметра, доступно в `args.[0]`. Код для вызова конструктора приводит возвращаемое значение к удаленному типу `obj`. После добавления второго предоставленного конструктора к типу вы создадите предоставленное свойство экземпляра:

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Получение этого свойства возвратит длину строки, которая является объектом представления. Свойство `GetterCode` возвращает F# предложение, которое указывает код, формируемый компилятором узла для получения свойства. Как и `InvokeCode`, функция `GetterCode` Возвращает предложение. Компилятор узла вызывает эту функцию со списком аргументов. В этом случае аргументы включают только одно выражение, представляющее экземпляр, на основе которого вызывается метод получения, к которому можно получить доступ с помощью `args.[0]`. Реализация `GetterCode` присоединение к результирующей цитате на удаленном типе `obj`, а приведение используется для обеспечения механизма компилятора для проверки типов, которые объект является строковым. Следующая часть `makeOneProvidedType` предоставляет метод экземпляра с одним параметром.

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

Наконец, создайте вложенный тип, содержащий 100 вложенных свойств. Создание этого вложенного типа и его свойств отложено, то есть вычисленное по запросу.

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i
    
              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))
    
              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)
    
              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>Сведения о стирании указанных типов

Пример в этом разделе содержит только *Удаленные предоставленные типы*, которые особенно полезны в следующих ситуациях.

- При создании поставщика для информационного пространства, содержащего только данные и методы.

- При написании поставщика, где точная семантика типа среды выполнения не критична для практического использования информационного пространства.

- При написании поставщика для информационного пространства настолько крупным и взаимосвязанным, что не рекомендуется создавать реальные типы .NET для информационного пространства.

В этом примере каждый предоставленный тип удаляется в тип `obj`, и все типы использования типа будут отображаться в скомпилированном коде как тип `obj`. Фактически, базовые объекты в этих примерах являются строками, но тип будет выглядеть как `System.Object` в скомпилированном коде .NET. Как и при использовании типа очистки, можно использовать явную упаковку, распаковку и приведение к обходят удаленным типам. В этом случае при использовании объекта может возникнуть исключение приведения, которое является недопустимым. Среда выполнения поставщика может определять собственный частный тип представления для защиты от ложных представлений. Нельзя определять стертые типы в F# самом себе. Только указанные типы могут быть стерты. Необходимо понимать последствия, как практичные, так и семантические, используя либо стертые типы для поставщика типов, либо поставщик, предоставляющий стертые типы. У стирания типа нет действительного типа .NET. Таким образом, невозможно выполнить точное отражение для типа, и вы можете обходят стереть типы при использовании приведений во время выполнения и других методов, зависящих от семантики типов среды выполнения. Подверсия стертых типов часто приводит к исключениям приведения типов во время выполнения.

### <a name="choosing-representations-for-erased-provided-types"></a>Выбор представлений для удаленных предоставленных типов

Для некоторых применений удаленных предоставленных типов представление не требуется. Например, стертный предоставленный тип может содержать только статические свойства и члены без конструкторов, а методы и свойства не возвращают экземпляр типа. Если можно достичь экземпляров удаленных предоставленных типов, необходимо учитывать следующие вопросы.

**Что такое очистки указанного типа?**

- Очистки предоставленного типа — это то, как тип отображается в скомпилированном коде .NET.

- Очистки указанного типа очищенного класса всегда является первым нестертым базовым типом в цепочке наследования типа.

- Очистки указанного типа удаленных интерфейсов всегда `System.Object`.

**Какие представления предоставленного типа?**

- Набор возможных объектов для очищенного предоставленного типа называется его представлениями. В примере в этом документе представления всех удаленных предоставленных типов `Type1..Type100` всегда являются строковыми объектами.

Все представления указанного типа должны быть совместимы с очистки указанного типа. (В противном случае F# либо компилятор выдаст ошибку для использования поставщика типов, либо будет создан недопустимый недействительный код .NET. Поставщик типов является недопустимым, если он возвращает код, предоставляющий Недопустимое представление.)

Можно выбрать представление для предоставленных объектов с помощью любого из следующих подходов, которые являются очень распространенными:

- Если вы просто предоставляете строго типизированную оболочку для существующего типа .NET, часто имеет смысл стереть этот тип, использовать экземпляры этого типа как представления или и то, и другое. Этот подход подходит, если большинство существующих методов этого типа все еще имеет смысл при использовании строго типизированной версии.

- Если вы хотите создать API, который значительно отличается от существующего API-интерфейса .NET, имеет смысл создать типы среды выполнения, которые будут очистки типа и представления для предоставленных типов.

В примере в этом документе строки используются как представления предоставленных объектов. Часто может быть целесообразно использовать другие объекты для представления. Например, словарь можно использовать в качестве контейнера свойств:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

В качестве альтернативы можно определить тип в поставщике типов, который будет использоваться во время выполнения для формирования представления, а также одной или нескольких операций среды выполнения:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

Указанные члены могут затем создавать экземпляры этого типа объектов:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

В этом случае вы можете (необязательно) использовать этот тип в качестве типа очистки, указав этот тип в качестве `baseType` при создании `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Ключевые уроки

В предыдущем разделе было объяснено, как создать простой поставщик типов стирания, предоставляющий ряд типов, свойств и методов. В этом разделе также объяснено понятие типа очистки, в том числе некоторые преимущества и недостатки предоставления удаленных типов от поставщика типов и обсуждаются представления удаленных типов.

## <a name="a-type-provider-that-uses-static-parameters"></a>Поставщик типов, использующий статические параметры

Возможность параметризации поставщиков типов статическими данными позволяет реализовать множество интересных сценариев, даже если поставщику не требуется доступ к локальным или удаленным данным. В этом разделе вы узнаете о некоторых основных методах совместного размещения таких поставщиков.

### <a name="type-checked-regex-provider"></a>Тип проверенного поставщика регулярных выражений

Представьте, что необходимо реализовать поставщик типов для регулярных выражений, которые создают оболочку для библиотек .NET <xref:System.Text.RegularExpressions.Regex> в интерфейсе, который предоставляет следующие гарантии времени компиляции:

- Проверка того, является ли регулярное выражение допустимым.

- Предоставление именованных свойств в совпадениях, основанных на именах групп в регулярном выражении.

В этом разделе показано, как использовать поставщики типов для создания `RegexTyped` типа, который параметризация шаблона регулярного выражения предоставляет эти преимущества. Компилятор сообщит об ошибке, если предоставленный шаблон недействителен, и поставщик типов может извлекать группы из шаблона, чтобы к ним можно было обращаться с помощью именованных свойств в совпадениях. При проектировании поставщика типов следует учитывать, как предоставляемый API должен выглядеть для конечных пользователей и как этот проект будет преобразован в код .NET. В следующем примере показано, как использовать такой API для получения компонентов кода области:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

В следующем примере показано, как поставщик типов преобразует эти вызовы:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Обратите внимание на следующие моменты.

- Стандартный тип Regex представляет параметризованный `RegexTyped` тип.

- Конструктор `RegexTyped` приводит к вызову конструктора Regex, передавая аргумент статического типа для шаблона.

- Результаты метода `Match` представлены стандартным типом <xref:System.Text.RegularExpressions.Match>.

- Каждая именованная группа приводит к предоставленному свойству, а доступ к свойству приводит к использованию индексатора для коллекции `Groups` совпадений.

Следующий код является основой логики для реализации такого поставщика, и в этом примере Добавление всех элементов к предоставленному типу не производится. Сведения о каждом добавленном члене см. в соответствующем разделе далее в этом разделе. Чтобы получить полный код, Скачайте пример из [ F# примера пакета 3,0](https://archive.codeplex.com/?p=fsharp3sample) на веб-сайте CodePlex.

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

Обратите внимание на следующие моменты.

- Поставщик типов принимает два статических параметра: `pattern`, обязательный, и `options`, которые являются необязательными (поскольку предоставляется значение по умолчанию).

- После того как будут указаны статические аргументы, создается экземпляр регулярного выражения. Этот экземпляр вызывает исключение, если регулярное выражение имеет неправильный формат, и эта ошибка будет передана пользователям.

- В обратном вызове `DefineStaticParameters` определяется тип, который будет возвращен после указания аргументов.

- Этот код задает для `HideObjectMethods` значение true, чтобы технология IntelliSense оставалась оптимизированной. Этот атрибут приводит к подавлению членов `Equals`, `GetHashCode`, `Finalize`и `GetType` из списков IntelliSense для предоставленного объекта.

- В качестве базового типа метода используется `obj`, но в качестве представления времени выполнения для этого типа используется объект `Regex`, как показано в следующем примере.

- Вызов конструктора `Regex` вызывает исключение <xref:System.ArgumentException>, если регулярное выражение является недопустимым. Компилятор перехватывает это исключение и сообщает пользователю сообщение об ошибке во время компиляции или в редакторе Visual Studio. Это исключение позволяет проверять регулярные выражения без запуска приложения.

Указанный выше тип не полезен, так как он не содержит значимых методов или свойств. Сначала добавьте статический метод `IsMatch`:

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

Предыдущий код определяет метод `IsMatch`, который принимает строку в качестве входных данных и возвращает `bool`. Единственная сложная часть — использование аргумента `args` в определении `InvokeCode`. В этом примере `args` представляет собой список предложений, представляющих аргументы для этого метода. Если метод является методом экземпляра, первый аргумент представляет `this` аргумент. Однако для статического метода аргументы являются только явными аргументами метода. Обратите внимание, что тип значения в кавычках должен соответствовать указанному возвращаемому типу (в данном случае `bool`). Также обратите внимание, что этот код использует метод `AddXmlDoc`, чтобы убедиться, что предоставленный метод также имеет полезную документацию, которую можно передать с помощью IntelliSense.

Затем добавьте метод Match для экземпляра. Однако этот метод должен возвращать значение предоставленного типа `Match`, чтобы обеспечить доступ к группам строго типизированным способом. Поэтому сначала объявите тип `Match`. Поскольку этот тип зависит от шаблона, который был передан как статический аргумент, этот тип должен быть вложен в определение параметризованного типа:

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

Затем добавьте одно свойство в тип сопоставления для каждой группы. Во время выполнения сопоставление представляется в виде <xref:System.Text.RegularExpressions.Match> значения, поэтому для получения соответствующей группы в предложении, определяющем свойство, необходимо использовать <xref:System.Text.RegularExpressions.Match.Groups> индексированное свойство.

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

Обратите внимание, что вы добавляете XML-документацию к предоставленному свойству. Также обратите внимание, что свойство может быть считано, если предоставлена функция `GetterCode`, а свойство может быть записано, если предоставлена функция `SetterCode`, поэтому полученное свойство доступно только для чтения.

Теперь можно создать метод экземпляра, возвращающий значение этого типа `Match`:

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

Поскольку создается метод экземпляра, `args.[0]` представляет экземпляр `RegexTyped`, для которого вызывается метод, а `args.[1]` является входным аргументом.

Наконец, предоставьте конструктор, чтобы можно было создать экземпляры указанного типа.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Конструктор просто удаляется до создания стандартного экземпляра Regex .NET, который снова упаковывается в объект, так как `obj` очистки предоставленного типа. С этим изменением пример использования API, указанный ранее в разделе, работает должным образом. Следующий код является полным и окончательным:

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a>Ключевые уроки

В этом разделе описано, как создать поставщик типов, который работает с его статическими параметрами. Поставщик проверяет статический параметр и предоставляет операции на основе его значения.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Поставщик типов, который поддерживается локальными данными

Зачастую может потребоваться, чтобы поставщики типов представим интерфейсы API на основе не только статических параметров, но и информации из локальных или удаленных систем. В этом разделе обсуждаются поставщики типов, основанные на локальных данных, например локальные файлы данных.

### <a name="simple-csv-file-provider"></a>Поставщик простых CSV-файлов

В качестве простого примера рассмотрим поставщик типов для доступа к научных данным в формате CSV (с разделителями-запятыми). В этом разделе предполагается, что CSV-файлы содержат строку заголовка, за которой следуют данные с плавающей запятой, как показано в следующей таблице.

|Расстояние (счетчик)|Время (секунд)|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

В этом разделе показано, как предоставить тип, который можно использовать для получения строк со свойством `Distance` типа `float<meter>` и свойством `Time` типа `float<second>`. Для простоты выполняются следующие предположения.

- Имена заголовков не должны содержать запятые или имеют форму "имя (единица)".

- Единицы — это все системные международные (Si) единицы, которые определяются модулем [Microsoft. FSharp. Data. унитсистемс.F#Si. UnitNames Module ()](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) .

- Все единицы являются простыми (например, счетчик), а не составными (например, измерение/секунда).

- Все столбцы содержат данные с плавающей запятой.

Более полный поставщик расставит эти ограничения.

Первый шаг — определить, как должен выглядеть API. При наличии файла `info.csv` с содержимым из предыдущей таблицы (в формате с разделителями-запятыми) Пользователи поставщика должны иметь возможность написать код, похожий на следующий пример:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

В этом случае компилятор должен преобразовать эти вызовы в что-то, как показано в следующем примере:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

Оптимальный перевод требует, чтобы поставщик типов определял реальный тип `CsvFile` в сборке поставщика типов. Поставщики типов часто используют несколько вспомогательных типов и методов для создания оболочки для важной логики. Поскольку меры удаляются во время выполнения, можно использовать `float[]` в качестве стирания типа для строки. Компилятор будет обрабатывать различные столбцы с разными типами мер. Например, первый столбец в нашем примере имеет тип `float<meter>`, а второй — `float<second>`. Однако удаленное представление может остаться довольно простым.

В следующем коде показано ядро реализации.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

Обратите внимание на следующие моменты реализации:

- Перегруженные конструкторы позволяют считывать либо исходный файл, либо тот, который имеет идентичную схему. Этот шаблон часто используется при написании поставщика типов для локальных или удаленных источников данных, и этот шаблон позволяет использовать локальный файл в качестве шаблона для удаленных данных.

- Значение [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) , передаваемое в конструктор поставщика типов, можно использовать для разрешения относительных имен файлов.

- Для определения расположения предоставленных свойств можно использовать метод `AddDefinitionLocation`. Поэтому, если вы используете `Go To Definition` для указанного свойства, CSV-файл будет открыт в Visual Studio.

- Тип `ProvidedMeasureBuilder` можно использовать для поиска единиц СИ и создания соответствующих типов `float<_>`.

### <a name="key-lessons"></a>Ключевые уроки

В этом разделе описано, как создать поставщик типов для локального источника данных с простой схемой, содержащейся в самом источнике данных.

## <a name="going-further"></a>Дальнейшие переходы

В следующих разделах приведены рекомендации для дальнейшего изучения.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Взгляните на скомпилированный код для удаленных типов

Чтобы получить представление о том, как использование поставщика типов соответствует выданному коду, рассмотрим следующую функцию, используя `HelloWorldTypeProvider`, которая используется ранее в этом разделе.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Ниже приведен образ результирующего кода, декомпилированного с помощью Ildasm. exe:

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

Как показано в примере, все упоминания типа `Type1` и свойство `InstanceProperty` были удалены, в результате чего в них будут находиться только операции с задействованными типами среды выполнения.

### <a name="design-and-naming-conventions-for-type-providers"></a>Соглашения о проектировании и именовании для поставщиков типов

При создании поставщиков типов Обратите внимание на следующие соглашения.

**Поставщики протоколов подключения** Как правило, имена большинства библиотек DLL поставщика для протоколов подключения к данным и служб, таких как подключения OData или SQL, должны заканчиваться `TypeProvider` или `TypeProviders`. Например, используйте имя библиотеки DLL, которое напоминает следующую строку:

`Fabrikam.Management.BasicTypeProviders.dll`

Убедитесь, что предоставленные типы являются членами соответствующего пространства имен, и укажите протокол подключения, который вы реализовали:

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Поставщики служебных программ для общего программирования**.  Для поставщика типов служебной программы, например для регулярных выражений, поставщик типов может быть частью базовой библиотеки, как показано в следующем примере:

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

В этом случае предоставленный тип будет отображаться в соответствующей точке в соответствии с обычными соглашениями проектирования .NET:

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**Одноэлементные источники данных**. Некоторые поставщики типов подключаются к одному выделенному источнику данных и предоставляют только данные. В этом случае следует удалить суффикс `TypeProvider` и использовать обычные соглашения для именования .NET:

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Дополнительные сведения см. в описании `GetConnection`ного соглашения о проектировании, которое описано далее в этом разделе.

### <a name="design-patterns-for-type-providers"></a>Конструктивные шаблоны для поставщиков типов

В следующих разделах описываются шаблоны разработки, которые можно использовать при создании поставщиков типов.

#### <a name="the-getconnection-design-pattern"></a>Шаблон проектирования соединения

Большинство поставщиков типов должны быть написаны для использования шаблона `GetConnection`, используемого поставщиками типов в FSharp. Data. TypeProviders. dll, как показано в следующем примере:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Поставщики типов, которые поддерживают удаленные данные и службы

Перед созданием поставщика типов, обеспечиваемого удаленными данными и службами, необходимо учитывать ряд проблем, связанных с подключенным программированием. Ниже приведены рекомендации по следующим вопросам.

- сопоставление схем

- динамическое и недействительность при изменении схемы

- кэширование схемы

- асинхронные реализации операций доступа к данным

- Поддержка запросов, включая запросы LINQ

- учетные данные и проверка подлинности

В этом разделе больше не рассматриваются эти проблемы.

### <a name="additional-authoring-techniques"></a>Дополнительные методы разработки

При написании собственных поставщиков типов может потребоваться использовать следующие дополнительные методы.

### <a name="creating-types-and-members-on-demand"></a>Создание типов и членов по запросу

API Провидедтипе имеет отложенные версии Аддмембер.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Эти версии используются для создания пробелов по запросу типов.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Предоставление типов массивов и создание экземпляров универсальных типов

Вы предоставили члены (чьи подписи включают типы массивов, типы ByRef и экземпляры универсальных типов), используя обычные `MakeArrayType`, `MakePointerType`и `MakeGenericType` в любом экземпляре <xref:System.Type>, включая `ProvidedTypeDefinitions`.

> [!NOTE]
> В некоторых случаях может потребоваться использовать вспомогательный метод в `ProvidedTypeBuilder.MakeGenericType`.  Дополнительные сведения см. в [документации по поставщику типов SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) .

### <a name="providing-unit-of-measure-annotations"></a>Предоставление заметок единиц измерения

API Провидедтипес предоставляет вспомогательные методы для предоставления заметок мер. Например, чтобы указать тип `float<kg>`, используйте следующий код:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Чтобы указать тип `Nullable<decimal<kg/m^2>>`, используйте следующий код:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Доступ к локальным ресурсам проекта или локальному сценарию

Каждому экземпляру поставщика типов может быть предоставлено `TypeProviderConfig` значение во время создания. Это значение содержит "папку разрешения" для поставщика (то есть папка проекта для компиляции или каталога, содержащего скрипт), список сборок, на которые имеются ссылки, и другие сведения.

### <a name="invalidation"></a>Недействительности

Поставщики могут создавать сигналы недействительности для уведомления F# языковой службы о том, что предположения схемы могли измениться. При возникновении недействительности типечекк выполняется повторно, если поставщик размещается в Visual Studio. Этот сигнал будет проигнорирован при размещении поставщика в F# интерактивном режиме или F# компиляторе (FSC. exe).

### <a name="caching-schema-information"></a>Кэширование сведений о схеме

Поставщики часто должны кэшировать доступ к сведениям о схеме. Кэшированные данные должны храниться с использованием имени файла, заданного статическим параметром или в виде пользовательских данных. Примером кэширования схемы является параметр `LocalSchemaFile` в поставщиках типов в сборке `FSharp.Data.TypeProviders`. В реализации этих поставщиков этот статический параметр направляет поставщику типов сведения о схеме в указанный локальный файл, а не на доступ к источнику данных по сети. Чтобы использовать кэшированные данные схемы, необходимо также задать для параметра static `ForceUpdate` значение `false`. Аналогичную методику можно использовать для включения доступа к данным в сети и автономном режиме.

### <a name="backing-assembly"></a>Резервная сборка

При компиляции файла `.dll` или `.exe` файл. dll для созданных типов статически связывается с результирующей сборкой. Эта ссылка создается путем копирования определений типов промежуточного языка (IL) и всех управляемых ресурсов из резервной сборки в окончательную сборку. При использовании F# интерактивного файла резервная копия DLL не копируется, а загружается непосредственно в F# интерактивный процесс.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Исключения и диагностика из поставщиков типов

Все варианты использования всех членов предоставленных типов могут вызывать исключения. Во всех случаях, если поставщик типов создает исключение, компилятор узла сообщает об ошибке конкретному поставщику типов.

- Исключения поставщика типов не должны приводить к внутренним ошибкам компилятора.

- Поставщики типов не могут сообщать о предупреждениях.

- Если поставщик типов размещается в F# компиляторе, в F# среде разработки или F# интерактивном режиме, все исключения из этого поставщика перехватываются. Свойство Message всегда является текстом ошибки, и трассировка стека не отображается. Если будет создано исключение, можно создать следующие примеры: `System.NotSupportedException`, `System.IO.IOException``System.Exception`.

#### <a name="providing-generated-types"></a>Предоставление созданных типов

На данный момент в этом документе было объяснено, как предоставить удаленные типы. Можно также использовать механизм поставщика типов в F# для предоставления сформированных типов, которые добавляются как реальные определения типов .NET в программу пользователя. Необходимо обращаться к созданным предоставленным типам с помощью определения типа.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Вспомогательный код Провидедтипес-0,2, который является частью выпуска F# 3,0, имеет ограниченную поддержку для предоставления сформированных типов. Для созданного определения типа должны быть справедливы следующие инструкции:

- для `isErased` необходимо задать значение `false`.

- Созданный тип должен быть добавлен к вновь созданной `ProvidedAssembly()`, которая представляет контейнер для созданных фрагментов кода.

- Поставщик должен иметь сборку, имеющую фактический резервный файл .NET. dll с совпадающим DLL-файлом на диске.

## <a name="rules-and-limitations"></a>Правила и ограничения

При записи поставщиков типов учитывайте следующие правила и ограничения.

### <a name="provided-types-must-be-reachable"></a>Предоставленные типы должны быть доступны

Все предоставленные типы должны быть доступны из невложенных типов. Невложенные типы задаются в вызове конструктора `TypeProviderForNamespaces` или вызове `AddNamespace`. Например, если поставщик предоставляет тип `StaticClass.P : T`, необходимо убедиться, что T является либо невложенным типом, либо вложенным в него.

Например, некоторые поставщики имеют статический класс, например `DataTypes`, содержащие эти типы `T1, T2, T3, ...`. В противном случае ошибка говорит о том, что обнаружена ссылка на тип T в сборке A, но тип не найден в этой сборке. Если возникает эта ошибка, убедитесь, что все подтипы доступны из типов поставщиков. Примечание. Эти типы `T1, T2, T3...` называются типами *на лету* . Не забудьте разместить их в доступном пространстве имен или родительском типе.

### <a name="limitations-of-the-type-provider-mechanism"></a>Ограничения механизма поставщика типов

Механизм поставщика типов в F# имеет следующие ограничения.

- Базовая инфраструктура для поставщиков типов в F# не поддерживает предоставленные универсальные типы или предоставленные универсальные методы.

- Механизм не поддерживает вложенные типы со статическими параметрами.

## <a name="development-tips"></a>Советы по разработке

Во время разработки могут оказаться полезными следующие советы:

### <a name="run-two-instances-of-visual-studio"></a>Запуск двух экземпляров Visual Studio

Вы можете разработать поставщик типов в одном экземпляре и протестировать его в другом, так как тестовая среда IDE заблокирует DLL-файл, который предотвращает перестроение поставщика типов. Поэтому необходимо закрыть второй экземпляр Visual Studio, пока поставщик построен в первом экземпляре, а затем повторно открыть второй экземпляр после сборки поставщика.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Отладка поставщиков типов с помощью вызовов FSC. exe

Поставщики типов можно вызывать с помощью следующих средств:

- FSC. exe (компилятор F# командной строки)

- FSI. exe ( F# интерактивный компилятор)

- devenv. exe (Visual Studio)

Часто отладку поставщиков типов можно упростить с помощью FSC. exe в файле скрипта теста (например, Script. fsx). Отладчик можно запустить из командной строки.

```console
devenv /debugexe fsc.exe script.fsx
```

  Можно использовать ведение журнала печати в stdout.

## <a name="see-also"></a>См. также

- [Поставщики типов](index.md)
- [Пакет SDK поставщика типов](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
