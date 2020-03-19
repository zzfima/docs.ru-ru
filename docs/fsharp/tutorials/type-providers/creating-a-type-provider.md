---
title: 'Учебник: Создание поставщика типов'
description: Узнайте, как создать свои собственные поставщики типов F-типа в F-3.0, изучив несколько простых поставщиков типов, чтобы проиллюстрировать основные концепции.
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186123"
---
# <a name="tutorial-create-a-type-provider"></a>Учебник: Создание поставщика типов

Механизм поставщика типов в F-фондявляется значительной частью его поддержки программирования, богатого информацией. В этом учебнике объясняется, как создать свой собственный тип поставщиков, прогуливаясь вас через развитие нескольких простых поставщиков типа, чтобы проиллюстрировать основные понятия. Для получения дополнительной информации о механизме [Type Providers](index.md)поставщика типов в F-сообщении см.

Экосистема F-класса содержит ряд поставщиков типовых услуг для широко используемых интернет- и корпоративных служб передачи данных. Пример:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) включает в себя поставщиков типов для форматов JSON, XML, CSV и HTML-документов.

- [СЗЛ-Провайдер](https://fsprojects.github.io/SQLProvider/) обеспечивает сильно набрасываемый доступ к базам данных СЗЛ с помощью картирования объектов и запросов f- LIN' с этими источниками данных.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) имеет набор поставщиков типов для компиляции времени проверенного встраивания T-S'L в F.

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) — это старый набор поставщиков типов для использования только с помощью программ .NET Framework для доступа к услугам данных S'L, Entity Framework, OData и WSDL.

При необходимости можно создавать поставщиков пользовательских типов или ссылаться на поставщиков типов, созданных другими пользователями. Например, в вашей организации может быть служба данных, которая обеспечивает большое и растущее число названных наборов данных, каждый из которых имеет свою собственную стабильную схему данных. Можно создать поставщика типов, который считывает схемы и представляет текущие наборы данных программисту в сильно набранном виде.

## <a name="before-you-start"></a>Перед началом работы

Механизм поставщика типов в первую очередь предназначен для внедрения стабильных информационных пространств данных и услуг в опыт программирования F.

Этот механизм не предназначен для инъекционных информационных пространств, схема которых изменяется при выполнении программы способами, относящимися к логике программы. Кроме того, механизм не предназначен для внутриязыкового метапрограммирования, даже если этот домен содержит некоторые допустимые применения. Этот механизм следует использовать только в тех случаях, когда это необходимо и в тех случаях, когда разработка поставщика типа дает очень высокую ценность.

Следует избегать написания поставщика типов, где схема недоступна. Аналогичным образом следует избегать написания поставщика типов, в котором достаточно обычной (или даже существующей) библиотеки .NET.

Перед началом вы можете задать следующие вопросы:

- У вас есть схема для вашего источника информации? Если да, то что такое отображение в системе типов F и .NET?

- Можно ли использовать существующий (динамически набранный) API в качестве отправной точки для реализации?

- Будете ли вы и ваша организация имеют достаточно использует тип поставщика, чтобы сделать написание его стоит? Удовлетворит ли нормальная библиотека .NET ваши потребности?

- Насколько изменится ваша схема?

- Изменится ли она во время кодирования?

- Изменится ли она между сеансами кодирования?

- Изменится ли она во время выполнения программы?

Поставщики типов лучше всего подходят для ситуаций, когда схема стабильна во время выполнения и в течение всего срока службы компилированного кода.

## <a name="a-simple-type-provider"></a>Поставщик простого типа

Этот образец Sample.HelloWorldTypeProvider, похожий `examples` на образцы в каталоге [поставщика F' Type SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Поставщик предоставляет "пространство типа", которое содержит 100 стертых типов, как показано в следующем коде, используя `Type1`синтаксис подписи F и опуская детали для всех, кроме. Для получения дополнительной информации о стертых типах смотрите [Подробная информация о стыковых предоставленных типах](#details-about-erased-provided-types) позже в этой теме.

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

Обратите внимание, что набор представленных типов и элементов статично известен. Этот пример не использует способность провайдеров предоставлять типы, зависят от схемы. Реализация поставщика типов изложена в следующем коде, а детали описаны в более поздних разделах этой темы.

> [!WARNING]
> Между этим кодом и онлайн-образцами могут быть различия.

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

Чтобы использовать этот провайдер, откройте отдельный экземпляр Visual Studio, создайте скрипт F,, а затем добавьте ссылку на провайдера из вашего скрипта, используя #r как показано следующее код:

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

Затем ищите типы в пространстве `Samples.HelloWorldTypeProvider` имен, генерируемые поставщиком типов.

Перед тем, как переоставить поставщика на перекомпилировать, убедитесь, что вы закрыли все экземпляры Visual Studio и F-Interactive, использующие поставщика DLL. В противном случае произойдет ошибка сборки, поскольку вывод DLL будет заблокирован.

Чтобы отладить этот провайдер с помощью печатных заявлений, сделайте сценарий, который разоблачает проблему с поставщиком, а затем используйте следующий код:

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Чтобы отладить этого поставщика с помощью Visual Studio, откройте командный запрос разработчика для Visual Studio с административными учетными данными и запустите следующую команду:

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

В качестве альтернативы откройте Visual Studio, откройте меню Debug, выберите `Debug/Attach to process…`и приложите к другому `devenv` процессу, где вы редактируете свой сценарий. Используя этот метод, можно с легкостью настроить таргетинг на конкретную логику в поставщике типов, интерактивно введя выражения во второй экземпляр (с полным IntelliSense и другими функциями).

Можно отключить отладку Just My Code, чтобы лучше выявлять ошибки в генерируемом коде. Для получения информации о том, как включить или отключить эту функцию, [см. Навигация по Коду с Debugger.](/visualstudio/debugger/navigating-through-code-with-the-debugger) Кроме того, вы также можете установить `Debug` первое исключение, открыв меню, а затем `Exceptions` выбрав `Exceptions` или выбрав ключи Ctrl-Alt-E, чтобы открыть диалоговую коробку. В этом диалоговом `Common Language Runtime Exceptions`поле, `Thrown` под , выберите флажок.

### <a name="implementation-of-the-type-provider"></a>Внедрение поставщика типов

Этот раздел проведет вас по основным разделам реализации поставщика типов. Во-первых, вы определяете тип для самого поставщика пользовательского типа:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Этот тип должен быть общедоступным, и вы должны пометить его атрибутом [TypeProvider,](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) чтобы компилятор распознавал поставщика типа, когда отдельный проект F's ссылается на сборку, содержащую тип. Параметр *конфигурации* является необязательным и, если он присутствует, содержит контекстную информацию о конфигурации для экземпляра типа поставщика, который создает компилятор F-формата.

Далее вы реализуете интерфейс [ITypeProvider.](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) В этом случае тип `TypeProviderForNamespaces` из `ProvidedTypes` API используется в качестве базового. Этот тип помощника может обеспечить конечную коллекцию охотно предоставленных названий, каждое из которых непосредственно содержит конечное количество фиксированных, охотно предоставленных типов. В этом контексте поставщик *охотно* генерирует типы, даже если они не нужны или используются.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Затем определите локальные частные значения, определяющие пространство имен для предоставленных типов, и найдите саму сборку поставщика типов. Эта сборка позже используется в качестве логического родительского типа предоставленных типов.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Затем создайте функцию для предоставления каждого из типов Type1... Тип100. Эта функция объясняется более подробно позже в этой теме.

```fsharp
let makeOneProvidedType (n:int) = …
```

Далее, создайте 100 предоставленных типов:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Далее добавьте типы в виде предоставленного пространства имен:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Наконец, добавьте атрибут сборки, указывающий на то, что поставщик DLL создает тип:

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

Этот шаг объясняет реализацию этой функции. Во-первых, создайте предоставленный тип (например, Type1, когда n No 1 или Type57, когда n no 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Вы должны отметить следующие моменты:

- Этот при условии, что тип стирается.  Поскольку в компилированном коде указывается, что базовый тип — экземпляры `obj`будут отображаться как значения типа [obj.](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)

- При указании невложенного типа необходимо указать пространство сборки и имя. Для стертых типов сборка должна быть самой сборкой поставщика типов.

Затем добавьте документацию XML в тип. Эта документация задерживается, т.е. вычисляется по требованию, если она нужна компилятору хоста.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Далее вы добавляете предоставленное статическое свойство к типу:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

Получение этого свойства всегда будет оценивать строку "Привет!". Для `GetterCode` свойства используется цитата F-кода, которая представляет собой код, генерируемый компилятором хоста для получения свойства. Для получения дополнительной информации [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)о котировках см.

Добавьте в свойство документацию XML.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Теперь приложите предоставленное свойство к предоставленному типу. Вы должны прикрепить предоставленного участника к одному типу. В противном случае участник никогда не будет доступен.

```fsharp
t.AddMember staticProp
```

Теперь создайте предоставленный конструктор, который не принимает никаких параметров.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

Для `InvokeCode` конструктора возвращается цитата F-кода, которая представляет собой код, генерируемый компилятором хоста при вызове конструктора. Например, можно использовать следующий конструктор:

```fsharp
new Type10()
```

Экземпляр предоставленного типа будет создан с базовыми данными "Данные объекта". Указанный код включает в себя преобразование в [obj,](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) потому что этот тип является стиранием этого при условии типа (как вы указали, когда вы объявили предоставленный тип).

Добавьте документацию XML к конструктору и добавьте предоставленный конструктор к предоставленному типу:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Создайте второй при условии, что конструктор принимает один параметр:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

Для `InvokeCode` конструктора снова возвращается цитата F-кода, которая представляет собой код, созданный компилятором узла для вызова к методу. Например, можно использовать следующий конструктор:

```fsharp
new Type10("ten")
```

Экземпляр предоставленного типа создается с базовыми данными "десять". Возможно, вы уже `InvokeCode` заметили, что функция возвращает цитату. Вход в эту функцию представляет собой список выражений, по одному на параметр конструктора. В этом случае в `args.[0]`доступе является выражение, представляющее значение одного параметра. Код для вызова к конструктору принуждает значение возврата к `obj`стертому типу. После добавления второго предоставленного конструктора к типу создается свойство предоставленного экземпляра:

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Получение этого свойства вернет длину строки, которая является объектом представления. Свойство `GetterCode` возвращает цитату F-кода, которая определяет код, который генерирует компилятор хоста для получения свойства. Как, `InvokeCode` `GetterCode` функция возвращает цитату. Компилятор хоста называет эту функцию списком аргументов. В этом случае аргументы включают только одно выражение, представляющее экземпляр, на котором вызывается `args.[0]`геттер, к которому можно получить доступ с помощью . Реализация `GetterCode` затем сращивания в цитату результата в `obj`стертом типе, и литые используется для удовлетворения механизма компилятора для проверки типов, что объект является строкой. Следующая часть `makeOneProvidedType` предоставляет экземплярный метод с одним параметром.

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

Наконец, создайте вложенный тип, содержащий 100 вложенных свойств. Создание этого вложенного типа и его свойства задерживается, то есть вычисляется по требованию.

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

### <a name="details-about-erased-provided-types"></a>Подробная информация о стереть предоставленные типы

Пример в этом разделе предоставляет только *стертые при условии типы,* которые особенно полезны в следующих ситуациях:

- Когда вы пишете поставщику для информационного пространства, содержащего только данные и методы.

- Когда вы пишете провайдера, где точная семантика типа выполнения не критична для практического использования информационного пространства.

- Когда вы пишете поставщику для такого большого и взаимосвязанного информационного пространства, что технически невозможно создать реальные типы .NET для информационного пространства.

В этом примере каждый при `obj`условии, что тип стирается `obj` для ввода, и все виды использования типа будут отображаться как тип в скомпилированном коде. На самом деле, основные объекты в этих примерах `System.Object` являются строками, но тип будет отображаться как в компилированном коде .NET. Как и во всех видах стирания типа, вы можете использовать явный бокс, распаковку и литье, чтобы подорвать стертые типы. В этом случае недопустимое исключение литого, может привести к использованию объекта. Время выполнения поставщика может определить свой собственный тип частного представления, чтобы защититься от ложных представлений. Вы не можете определить стертые типы в самом F-из. Только при условии, что типы могут быть удалены. Вы должны понимать последствия, как практические, так и семантические, использования либо стертых типов для поставщика типов, либо поставщика, предоставляющего стертые типы. Стертый тип не имеет реального типа .NET. Таким образом, вы не можете сделать точное отражение типа, и вы можете подорвать стертые типы, если вы используете отливки времени выполнения и другие методы, которые полагаются на точную семантику типа выполнения. Подрыв стертых типов часто приводит к исключениям в водах во время выполнения.

### <a name="choosing-representations-for-erased-provided-types"></a>Выбор представлений для удаленных предоставленных типов

Для некоторых видов удалений, предоставленных, представление не требуется. Например, вытиснутый при условии тип может содержать только статические свойства и элементы и отсутствие конструкторов, и никакие методы или свойства не возвращают экземпляр типа. Если вы можете достичь экземпляров стертого предоставленного типа, необходимо рассмотреть следующие вопросы:

**Что такое стирание предоставленного типа?**

- Стирание предоставленного типа — это то, как тип отображается в компилированном коде .NET.

- Удаление предоставленного стертого типа класса всегда является первым нестерированным базовым типом в цепочке наследования типа.

- Удаление предоставленного стертого типа интерфейса `System.Object`всегда.

**Каковы представления предоставленного типа?**

- Набор возможных объектов для стертого при условии типа называется его представлениями. В примере в этом документе представления всех стертых предоставленных типов `Type1..Type100` всегда являются объектами строки.

Все представления предоставленного типа должны быть совместимы с стиранием предоставленного типа. (В противном случае, либо компилятор F's даст ошибку для использования поставщика типа, либо будет сгенерирован непроверяемый код .NET, который недействителен. Поставщик типа не действителен, если он возвращает код, который дает представление, которое не является действительным.)

Вы можете выбрать представление для предоставленных объектов, используя любой из следующих подходов, оба из которых очень распространены:

- Если вы просто предоставляете сильно набранную обертку по существующему типу .NET, часто имеет смысл, чтобы ваш тип стирал в этот тип, использовал экземпляры этого типа в качестве представлений или и то, и другое. Этот подход является целесообразным, когда большинство существующих методов этого типа все еще имеет смысл при использовании сильно набранной версии.

- Если требуется создать API, который значительно отличается от любого существующего API .NET, имеет смысл создать типы времени выполнения, которые будут стиранием типа и представлениями для предоставленных типов.

Пример в этом документе использует строки в качестве представления предоставленных объектов. Часто может быть целесообразным использовать другие объекты для представлений. Например, вы можете использовать словарь в качестве пакета свойств:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

В качестве альтернативы можно определить тип поставщика типов, который будет использоваться во время выполнения для формирования представления, а также одну или несколько операций выполнения:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

Предоставленные участники могут построить экземпляры этого типа объекта:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

В этом случае этот тип может использоваться в качестве стирания типа, указывая этот тип как `baseType` при `ProvidedTypeDefinition`построении:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Основные уроки

В предыдущем разделе объяснялось, как создать простой поставщик типов стирания, который предоставляет ряд типов, свойств и методов. В этом разделе также разъясняется концепция стирания типов, включая некоторые преимущества и недостатки предоставления стертых типов от поставщика типа, а также обсуждаются представления стертых типов.

## <a name="a-type-provider-that-uses-static-parameters"></a>Поставщик типов, который использует статические параметры

Возможность параметризации поставщиков типов статичными данными позволяет использовать множество интересных сценариев, даже в тех случаях, когда поставщику не требуется доступ к каким-либо локальным или удаленным данным. В этом разделе вы узнаете некоторые основные методы для воедино такой поставщик.

### <a name="type-checked-regex-provider"></a>Тип Проверенный поставщик Regex

Представьте, что вы хотите реализовать поставщик типов для регулярных <xref:System.Text.RegularExpressions.Regex> выражений, который обертывает библиотеки .NET в интерфейс, который предоставляет следующие гарантии времени компиляции:

- Проверка допустимого регулярного выражения.

- Предоставление названных свойств на совпадениях, основанных на любых именах групп в обычном выражении.

В этом разделе показано, как использовать `RegexTyped` поставщиков типов для создания типа, который параметры шаблона обычного выражения для предоставления этих преимуществ. Компилятор сообщит об ошибке, если поставляемый шаблон недействителен, а поставщик типов может извлечь группы из шаблона, чтобы можно было получить к ним доступ с помощью именных свойств на совпадениях. При проектировании поставщика типов следует учитывать, как его открытый API должен выглядеть для конечных пользователей и как этот дизайн будет переведен на код .NET. В следующем примере показано, как использовать такой API для получения компонентов кода области:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

Ниже приводится следующий пример, как поставщик типов переводит эти вызовы:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Обратите внимание на следующие моменты.

- Стандартный тип Regex представляет `RegexTyped` параметризированный тип.

- Конструктор `RegexTyped` приводит к вызову к конструктору Regex, переходя в аргумент статического типа для шаблона.

- Результаты метода `Match` представлены стандартным <xref:System.Text.RegularExpressions.Match> типом.

- Каждая названная группа приводит к предоставленному свойству, а доступ к свойству `Groups` приводит к использованию указателя в коллекции совпадения.

Следующий код является ядром логики для реализации такого поставщика, и этот пример не дает прибавления всех членов к предоставленному типу. Для получения информации о каждом добавленном участнике, см. Для получения полного кода, скачать образец из [F' 3.0 Пример пакета](https://archive.codeplex.com/?p=fsharp3sample) на веб-сайте CodePlex.

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

- Поставщик типа принимает два статических `pattern`параметра: обязательное `options`значение , и необязательное значение (поскольку предусмотрено значение по умолчанию).

- После того, как статические аргументы поставляются, вы создаете экземпляр регулярного выражения. Этот экземпляр будет выкидывать исключение, если Regex недоформирован, и эта ошибка будет сообщена пользователям.

- В `DefineStaticParameters` рамках обратного вызова вы определяете тип, который будет возвращен после поступления аргументов.

- Этот код `HideObjectMethods` соответствует действительности, так что опыт IntelliSense будет оставаться рационализированным. Этот атрибут `Equals`приводит `GetHashCode` `Finalize`к `GetType` тому, что , , и члены будут подавлены из списков IntelliSense для предоставленного объекта.

- Вы `obj` используете в качестве базового типа метода, но вы будете использовать `Regex` объект в качестве представления времени выполнения этого типа, как показано в следующем примере.

- Вызов к `Regex` конструктору бросает, <xref:System.ArgumentException> когда обычное выражение не является действительным. Компилятор ловит это исключение и сообщает сообщение об ошибке пользователю во время компиляции или в редакторе Visual Studio. Это исключение позволяет проверять регулярные выражения без запуска приложения.

Тип, указанный выше, пока не полезен, поскольку не содержит значимых методов или свойств. Во-первых, `IsMatch` добавьте статический метод:

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

Предыдущий код определяет `IsMatch`метод, который принимает строку в `bool`качестве ввода и возвращает . Единственной сложной частью является `args` использование `InvokeCode` аргумента в определении. В этом `args` примере приводится список цитат, представляющих аргументы к данному методу. Если метод является методом экземпляра, `this` первый аргумент представляет аргумент. Однако для статического метода аргументы являются лишь явными аргументами в пользу метода. Обратите внимание, что тип указанного значения должен соответствовать `bool`указанному типу возврата (в данном случае). Также обратите внимание, `AddXmlDoc` что этот код использует метод, чтобы убедиться, что предоставленный метод также имеет полезную документацию, которую можно предоставить через IntelliSense.

Затем добавьте метод матча экземпляра. Однако этот метод должен вернуть `Match` значение предоставленного типа, с тем чтобы к группам можно было получить доступ в строго модном виде. Таким образом, вы `Match` сначала объявляете тип. Поскольку этот тип зависит от шаблона, который был представлен в качестве статического аргумента, этот тип должен быть вложен в определение параметризированного типа:

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

Затем в тип матча добавляется одно свойство для каждой группы. Во время выполнения совпадение представлено как <xref:System.Text.RegularExpressions.Match> значение, поэтому цитата, определяющая свойство, должна использовать <xref:System.Text.RegularExpressions.Match.Groups> индексированное свойство для получения соответствующей группы.

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

Опять же, обратите внимание, что вы добавляете документацию XML в предоставленное свойство. Также обратите внимание, что свойство может быть прочитано, если `GetterCode` `SetterCode` функция предоставлена, и свойство может быть написано, если функция предоставляется, так что полученное свойство читается только.

Теперь можно создать метод экземпляра, `Match` который возвращает значение этого типа:

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

Поскольку вы создаете `args.[0]` метод `RegexTyped` экземпляра, представляет экземпляр, на `args.[1]` котором вызывается метод, и является аргументом ввода.

Наконец, предоставьте конструктор, чтобы можно было создать экземпляры предоставленного типа.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Конструктор просто стирает к созданию стандартного экземпляра .NET Regex, который `obj` снова привозится к объекту, потому что это удаление предоставленного типа. С этим изменением использование API-образца, указанное ранее в теме, работает как ожидалось. Следующий код является полным и окончательным:

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

### <a name="key-lessons"></a>Основные уроки

В этом разделе объясняется, как создать поставщика типов, который работает по его статическим параметрам. Поставщик проверяет статический параметр и предоставляет операции в зависимости от его значения.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Поставщик типов, опирайся на локальные данные

Часто может потребоваться, чтобы поставщики типов представляли AI на основе не только статических параметров, но и информации из локальных или удаленных систем. В этом разделе рассматриваются поставщики типов, основанные на локальных данных, таких как локальные файлы данных.

### <a name="simple-csv-file-provider"></a>Простой поставщик файлов CSV

В качестве простого примера рассмотрим поставщика типов для доступа к научным данным в формате Comma Separated Value (CSV). В этом разделе предполагается, что файлы CSV содержат строку заголовка, за которой следуют данные о плавающей точке, так как следующая таблица иллюстрирует:

|Расстояние (метр)|Время (второй)|
|----------------|-------------|
|50.0|3,7|
|100.0|5,2|
|150.0|6.4|

В этом разделе показано, как предоставить тип, который `Distance` можно `float<meter>` использовать `Time` для получения `float<second>`строк с свойством типа и свойством типа. Для простоты сделаны следующие предположения:

- Имена заголовков либо единицы меньше или имеют форму "Имя (единица)" и не содержат запятых.

- Единицы все системы Международные (SI) единиц, как [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Модуль (F )](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) модуль определяет.

- Единицы все простые (например, метр), а не соединения (например, метр в секунду).

- Все столбцы содержат данные о плавающей точке.

Более полный поставщик ослабит эти ограничения.

Опять же, первый шаг заключается в том, чтобы рассмотреть, как Должен выглядеть API. Учитывая `info.csv` файл с содержимым из предыдущей таблицы (в формате, разделенном запятой), пользователи провайдера должны иметь возможность писать код, напоминающий следующий пример:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

В этом случае компилятор должен преобразовать эти вызовы в нечто вроде следующего примера:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

Оптимальный перевод потребует от поставщика `CsvFile` типа определения реального типа в сборке поставщика типов. Поставщики типов часто полагаются на несколько типов и методов помощника для обертывания важной логики. Поскольку измерения стираются во время `float[]` выполнения, можно использовать в качестве стертого типа для строки. Компилятор будет рассматривать различные столбцы как имеющие различные типы измерений. Например, первый столбец в `float<meter>`нашем примере `float<second>`имеет тип, а второй имеет . Однако стертое представление может оставаться довольно простым.

Следующий код показывает ядро реализации.

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

- Перегруженные конструкторы позволяют читать либо исходный файл, либо тот, который имеет идентичную схему. Этот шаблон является общим, когда вы пишете поставщик типа для локальных или удаленных источников данных, и этот шаблон позволяет использовать локальный файл в качестве шаблона для удаленных данных.

- Для решения относительных имен файлов можно использовать значение [TypeProviderConfig,](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) передаваемые конструктору поставщика типов.

- Этот `AddDefinitionLocation` метод можно использовать для определения местоположения предоставленных свойств. Поэтому, если `Go To Definition` вы используете на предоставленном свойстве, файл CSV откроется в Visual Studio.

- Этот `ProvidedMeasureBuilder` тип можно использовать для поиска единиц СИ `float<_>` и создания соответствующих типов.

### <a name="key-lessons"></a>Основные уроки

В этом разделе объясняется, как создать поставщика типов для локального источника данных с помощью простой схемы, содержащейся в самом источнике данных.

## <a name="going-further"></a>Дальнейшая работа

Следующие разделы содержат предложения по дальнейшему изучению.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Взгляд на составленный код для стертых типов

Чтобы дать вам некоторое представление о том, как использование поставщика типа соответствует испускаемому коду, посмотрите на следующую функцию, используя `HelloWorldTypeProvider` используемую ранее в этой теме.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Вот изображение полученного кода, декомпилированного с помощью ildasm.exe:

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

Как показано в примере, все `Type1` упоминания `InstanceProperty` типа и свойства были удалены, оставляя только операции на типах времени выполнения.

### <a name="design-and-naming-conventions-for-type-providers"></a>Конвенции по проектированию и именованию для поставщиков типов

Соблюдайте следующие конвенции при авторизации поставщиков типов.

**Поставщики протоколов о подключении** Как правило, имена большинства dL-услуг поставщика для протоколов подключения к данным и службам, таких как соединения OData или S'L, должны заканчиваться `TypeProvider` или `TypeProviders`находиться под другими службами. Например, используйте имя DLL, напоминающее следующую строку:

`Fabrikam.Management.BasicTypeProviders.dll`

Убедитесь, что предоставленные типы являются участниками соответствующего пространства имен, и укажите протокол подключения, который вы реализовали:

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Поставщики коммунальных услуг для общего кодирования**.  Для поставщика утилиты типа, например для обычных выражений, поставщик типов может быть частью базовой библиотеки, как показано в следующем примере:

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

В этом случае предоставленный тип будет отображаться в соответствующем месте в соответствии с обычными конвенциями о проектировании .NET:

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**Синглтон Источники данных**. Некоторые поставщики типов подключаются к единому специализированному источнику данных и предоставляют только данные. В этом случае следует `TypeProvider` отказаться от суффикса и использовать обычные условности для именования .NET:

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Для получения дополнительной `GetConnection` информации, см. дизайн конвенции, которые описаны позже в этой теме.

### <a name="design-patterns-for-type-providers"></a>Шаблоны проектирования для поставщиков типов

В следующих разделах описаны шаблоны проектирования, которые можно использовать при авторизации поставщиков типов.

#### <a name="the-getconnection-design-pattern"></a>Шаблон проектирования GetConnection

Большинство поставщиков типов должны быть `GetConnection` написаны для использования шаблона, используемого поставщиками типов в FSharp.Data.TypeProviders.dll, как показано в следующем примере:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Поставщики типов, поддерживаемые удаленными данными и службами

Прежде чем создать поставщика типов, опирайся на удаленные данные и службы, необходимо рассмотреть ряд проблем, присущих подключенному программированию. Эти вопросы включают следующие соображения:

- схемы отображение

- живость и недействительность при наличии изменения схемы

- кэширование схемы

- асинхронные реализации операций доступа к данным

- поддержка запросов, в том числе запросов LIN

- учетные данные и аутентификация

Эта тема не исследует эти вопросы дальше.

### <a name="additional-authoring-techniques"></a>Дополнительные методы авторизации

При написании собственных поставщиков типов можно использовать следующие дополнительные методы.

### <a name="creating-types-and-members-on-demand"></a>Создание типов и участников по запросу

API ProvidedType задержал версии AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Эти версии используются для создания пространств типов по запросу.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Предоставление типов массивов и общих моментов типа

Вы делаете предоставленные члены (чьи подписи включают типы массивов, типы byref `MakeGenericType` и моментности <xref:System.Type>генерических типов) с помощью нормального `MakeArrayType`, `MakePointerType`и на любом экземпляре , включая `ProvidedTypeDefinitions`.

> [!NOTE]
> В некоторых случаях вам, возможно, `ProvidedTypeBuilder.MakeGenericType`придется использовать помощника в .  Для получения более подробной информации можно ознакомиться с [документацией поставщика услуг типа SDK.](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)

### <a name="providing-unit-of-measure-annotations"></a>Предоставление аннотаций единицы измерения

API ProvidedTypes предоставляет помощникам для предоставления аннотаций измерения. Например, чтобы уповатиться в типе, `float<kg>`используйте следующий код:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Чтобы обеспечить `Nullable<decimal<kg/m^2>>`тип, используйте следующий код:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Доступ к ресурсам проекта-локальные или скриптно-локальные ресурсы

Каждому экземпляру поставщика типа `TypeProviderConfig` может быть присвоено значение во время строительства. Это значение содержит папку «разрешение» для поставщика (т.е. папку проекта для компиляции или каталог, содержащий сценарий), список эталонных сборок и другую информацию.

### <a name="invalidation"></a>Недействительности

Поставщики могут поднимать недействительные сигналы, чтобы уведомить языковую службу F's о возможном изменении допущений схемы. При возникновении недействительной проверки проверка типа переиздана, если провайдер размещается в Visual Studio. Этот сигнал будет проигнорирован, когда провайдер размещается в F- Interactive или на F'S Compiler (fsc.exe).

### <a name="caching-schema-information"></a>Кэшинг Схема Информация

Поставщики часто должны кэшировать доступ к информации о схеме. Кэшированные данные должны храниться с помощью имени файла, приведенного в качестве статического параметра или в качестве пользовательских данных. Примером кэширования схемы `LocalSchemaFile` является параметр в поставщике типов в сборке. `FSharp.Data.TypeProviders` При реализации этих поставщиков этот статический параметр направляет поставщика типа на использование информации о схеме в указанном локальном файле вместо доступа к источнику данных по сети. Чтобы использовать кэшированную информацию о схеме, `false`необходимо также установить статический параметр. `ForceUpdate` Можно использовать аналогичный метод для обеспечения доступа к данным в режиме онлайн и в автономном режиме.

### <a name="backing-assembly"></a>Поддержка Ассамблеи

При компилировании файла `.dll` или `.exe` файла резервного копирования .dll для сгенерированных типов статически связан в полученную сборку. Эта ссылка создается путем копирования определений типа промежуточного языка (IL) и любых управляемых ресурсов из резервной сборки в окончательную сборку. При использовании F-Интерактивного файла поддержки .dll не копируется и вместо этого загружается непосредственно в интерактивный процесс F.'.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Исключения и диагностика от поставщиков типов

Все виды использования всех членов из предоставленных типов могут выбросить исключения. Во всех случаях, если поставщик типа бросает исключение, компилятор хоста приписывает ошибку определенному поставщику типа.

- Исключения поставщика типов никогда не должны приводить к внутренним ошибкам компилятора.

- Поставщики типов не могут сообщать о предупреждениях.

- При размещении поставщика типов в компиляторе F-среды, среде разработки F-среды или F-Interactive все исключения из этого поставщика выявляются. Свойство сообщения всегда является текстом ошибки, и не отображается след стека. Если вы собираетесь бросить исключение, вы можете бросить `System.NotSupportedException` `System.IO.IOException`следующие примеры: , `System.Exception`.

#### <a name="providing-generated-types"></a>Предоставление генерируемых типов

До сих пор в этом документе разъяснялось, как предоставлять стертые типы. Вы также можете использовать механизм поставщика типов в F, чтобы обеспечить генерируемые типы, которые добавляются в качестве реальных определений типа .NET в программу пользователей. Вы должны ссылаться на генерируемые типы с помощью определения типа.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Вспомогательный код ProvidedTypes-0.2, врамкахный в выпуске F-3.0, имеет лишь ограниченную поддержку для предоставления генерируемых типов. Следующие утверждения должны быть верны для определения генерируемого типа:

- Для параметра `isErased` нужно задать значение `false`.

- Генерируемый тип должен быть добавлен `ProvidedAssembly()`в недавно построенный, который представляет собой контейнер для сгенерированных фрагментов кода.

- Поставщик должен иметь сборку, которая имеет фактический резервный файл .NET .dll с соответствующим файлом .dll на диске.

## <a name="rules-and-limitations"></a>Правила и ограничения

Когда вы пишете поставщики типов, имейте в виду следующие правила и ограничения.

### <a name="provided-types-must-be-reachable"></a>Предоставляемые типы должны быть доступны

Все предоставленные типы должны быть доступны из невложенных типов. Невложенные типы даются в вызове `TypeProviderForNamespaces` к конструктору `AddNamespace`или вызове. Например, если поставщик предоставляет `StaticClass.P : T`тип, необходимо убедиться, что T является либо невложенным типом, либо вложенным под один.

Например, некоторые поставщики имеют статический `DataTypes` класс, например, который содержит эти `T1, T2, T3, ...` типы. В противном случае ошибка говорит, что была найдена ссылка на тип T в сборке А, но тип не может быть найден в этой сборке. Если эта ошибка появится, убедитесь, что все ваши подтипы могут быть достигнуты из типов поставщиков. Примечание: `T1, T2, T3...` Эти типы называются типами *на лету.* Не забудьте поместить их в доступное пространство имен или тип родительского элемента.

### <a name="limitations-of-the-type-provider-mechanism"></a>Ограничения механизма поставщика типов

Механизм поставщика типов в F-фз имеет следующие ограничения:

- Базовая инфраструктура для поставщиков типов в F-поставщике не поддерживает при условии общих типов или общих методов.

- Механизм не поддерживает вложенные типы со статическими параметрами.

## <a name="development-tips"></a>Советы по разработке

В процессе разработки можно найти следующие советы:

### <a name="run-two-instances-of-visual-studio"></a>Выполнить два экземпляра Visual Studio

Вы можете разработать поставщика типов в одном экземпляре и протестировать поставщика в другом, потому что тестовый IDE возьмет блокировку файла .dll, который предотвращает перестроение поставщика типа. Таким образом, необходимо закрыть второй экземпляр Visual Studio во время построения поставщика в первой инстанции, а затем повторно открыть второй экземпляр после того, как провайдер построен.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Поставщики типа debug с помощью вызовов fsc.exe

Вы можете вызвать поставщиков типов, используя следующие инструменты:

- fsc.exe (компилятор командной строки F')

- fsi.exe (Интерактивный компилятор ФЗ)

- devenv.exe (Визуальная студия)

Вы часто можете отладить тип поставщиков легче всего, используя fsc.exe на файл тестового скрипта (например, script.fsx). Можно запустить отладчик из командного запроса.

```console
devenv /debugexe fsc.exe script.fsx
```

  Вы можете использовать журнал печати до утилиза.

## <a name="see-also"></a>См. также раздел

- [Поставщики типов](index.md)
- [Поставщик типа SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
