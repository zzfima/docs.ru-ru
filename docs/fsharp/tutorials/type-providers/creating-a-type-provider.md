---
title: 'Учебник: Создание поставщика типов (F #)'
description: 'Сведения о создании собственных поставщиков типов F # в F # 3.0, изучив несколько поставщиков простого типа, чтобы продемонстрировать основные понятия.'
ms.date: 05/16/2016
ms.openlocfilehash: 3c998377b2c3a408d536ef416f3799bf7f04b6bd
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275513"
---
# <a name="tutorial-create-a-type-provider"></a>Учебник: Создание поставщика типов

Механизм поставщиков типов в F # является значительную часть поддержка возможности программирования сведения. Этом руководстве описывается создание собственных поставщиков типов посредством разработки из нескольких поставщиков простого типа, чтобы продемонстрировать основные понятия. Дополнительные сведения о механизме поставщика типов в F # см. в разделе [поставщиков типов](index.md).

В экосистеме F # содержит широкий набор поставщиков типов для часто используемых Интернет и enterprise data services. Пример:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) включает поставщиков типов для форматы документов JSON, XML, CSV и HTML.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) предоставляет строго типизированный доступ к базам данных SQL через сопоставление объектов и F # LINQ запросы к источникам данных.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) набор поставщиков типов для компиляции проверен внедрение T-SQL, в F #.

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) — старые набор поставщиков типов для использования только с программированием для платформы .NET Framework для доступа к службам данных SQL, Entity Framework, OData и WSDL.

При необходимости, можно создать пользовательские поставщики типов, или вы можете ссылаться на поставщиков типов, созданных другими пользователями. Например ваша организация может иметь службу данных, которая предоставляет большого и постоянно растущего ряд именованных наборов данных, каждый из которых свой собственный стабильная схема данных. Можно создать поставщик типов, который считывает схемы и представляет текущее наборов данных на программиста в строго типизированным способом.

## <a name="before-you-start"></a>Прежде чем начать

Механизм поставщика типа в основном предназначен для внесения неизменных данных и службы информационных пространств в программирования на языке F #.

Этот механизм не поддерживает внедрение информационных пространств, схема которой изменяется во время выполнения программы, одним из способов, которые подходят для логики программы. Кроме того механизм не поддерживает intra межъязыкового метапрограммирования, несмотря на то, что этот домен содержит некоторые допустимые варианты использования. Этот механизм следует использовать только в том случае, если необходимо, и где разработки поставщик типа выдает очень большое значение.

Старайтесь не писать поставщик типа, где схема недоступна. Аналогично, старайтесь не писать поставщик типа там, где обычный (или даже существующего) было бы достаточно библиотеки .NET.

Прежде чем начать, можно задать следующие вопросы:

- У вас есть схемы для источника сведения? Если это так, что такое сопоставление в F # и системе типов .NET?

- Можно использовать интерфейс API (динамической типизацией) в качестве отправной точки для реализации?

- Вам и вашей организации будет недостаточно использует поставщик типов для облегчения написания его оправданной? Обычной библиотеки .NET удовлетворят потребности?

- Насколько изменится схемы?

- Изменится во время кодирования?

- Изменится между семинары по программированию?

- Изменится во время выполнения программы?

Поставщики типов являются наилучшим образом подходит для ситуаций, где схема стабильна, во время выполнения и в течение времени существования скомпилированного кода.

## <a name="a-simple-type-provider"></a>Поставщик простой тип

Этот пример представляет Samples.HelloWorldTypeProvider, аналогичную в примерах `examples` каталог [пакета SDK поставщика типа F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Поставщик делает доступными «тип space», содержащий 100 удаленных типов, как показано в следующем коде с помощью F # signature syntax и пропуск сведения для всех, кроме `Type1`. Дополнительные сведения об удаленных типах см. в разделе [сведения о удалены предоставляемые типы](#details-about-erased-provided-types) далее в этом разделе.

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

Обратите внимание на то, что статически известен набор типов и членов, которые предоставляются. В этом примере не использовать возможности поставщиков для предоставления типов, которые зависят от схемы. Реализация поставщика типов описан в следующем коде, и подробности этого охвачены в следующих разделах этой статьи.

>[!WARNING]
Возможно, различия между этим кодом и примеров в сети.

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

Чтобы использовать этот поставщик, откройте отдельный экземпляр Visual Studio, создать скрипт F # и затем добавьте ссылку на службу из скрипта с помощью #r, как показано в следующем коде:

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

Проверьте типы в разделе `Samples.HelloWorldTypeProvider` пространства имен, вызвавшего поставщика типов.

Перед перекомпиляцией поставщика, убедитесь, что вы уже закрыли все экземпляры Visual Studio и F # Interactive, использующих DLL-Библиотека поставщика. В противном случае ошибка сборки произойдет, так как выходной библиотеке DLL будет заблокирована.

Чтобы отладить этот поставщик с помощью выражения print, создание сценария, указывающий на проблему с поставщиком и затем используйте следующий код:

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Чтобы отладить этот поставщик с помощью Visual Studio, откройте командную строку Visual Studio от имени администратора и выполните следующую команду:

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Кроме того, откройте Visual Studio откройте меню "Отладка", выберите `Debug/Attach to process…`и подключить к другой `devenv` процесса, где вы редактируете скрипта. С помощью этого метода, можно точнее указывать определенной логики у поставщика типов, введя интерактивно выражения в второй экземпляр (с полной поддержкой IntelliSense и других функций).

Можно отключить только мой код отладки, чтобы выявить ошибки в сформированном коде. Сведения о том, как включить или отключить эту функцию, см. в разделе [Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger). Кроме того, можно также задать исключения первого шанса, перехват, открыв `Debug` меню и выбрав `Exceptions` или нажав клавиши Ctrl + Alt + E, чтобы открыть `Exceptions` диалоговое окно. В этом диалоговом окне в разделе `Common Language Runtime Exceptions`выберите `Thrown` "флажок".

### <a name="implementation-of-the-type-provider"></a>Реализация поставщика типов

В этом разделе пошагово части реализации поставщика типа. Во-первых вы определите тип поставщика пользовательского типа самой:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Этот тип должен быть открытым и должен отметить его атрибутом [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) таким образом, чтобы компилятор распознает поставщика типов, когда отдельный проект F # ссылается на сборку, содержащую тип. *Config* параметр является необязательным и, при его наличии, содержит сведения о контекстных конфигурации для экземпляра поставщика типов, который создает компилятор F #.

Далее необходимо реализовать [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) интерфейс. В этом случае используется `TypeProviderForNamespaces` тип из `ProvidedTypes` API в качестве базового типа. Этот вспомогательный тип можно заранее предоставить конечную коллекцию, предоставляется пространства имен, непосредственно каждый из которых содержит конечное количество исправлена, заранее типов. В этом контексте, поставщик *заранее* создает типы, даже если они не требуется или не используется.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Определение локальной частной значения, которые определяют пространство имен для существующих затем найти саму сборку поставщика типа. Эта сборка используется как логический родительский тип удаленных типов, которые предоставляются для более поздней версии.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Создайте функцию для предоставления каждого из типов Type1... Type100. Эта функция является более подробно далее в этом разделе.

```fsharp
let makeOneProvidedType (n:int) = …
```

Далее создайте 100 указанными типами:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Добавьте типы как указанное пространство имен:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Наконец добавьте атрибут сборки, которое указывает, что вы создаете поставщик типа библиотеки DLL:

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a>Предоставление одного типа и его членов

`makeOneProvidedType` Функция не работает один из типов предоставления.

```fsharp
let makeOneProvidedType (n:int) = 
…
```

На этом шаге описывается реализация этой функции. Во-первых, создайте предоставленный тип (например, тип 1, когда n = 1 или Type57, когда n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Следует отметить следующие моменты:

- Это, если тип удаляется.  Так как можно указать, что базовый тип является `obj`, экземпляров будет отображаться в виде значения типа [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) в скомпилированный код.

- При указании типа, невложенными, необходимо указать сборку и пространство имен. Для удаленных типов сборка должна быть самой сборки типа поставщика.

Добавьте XML-документации к типу. Эта документация задерживается, то есть, вычисляется по запросу, если компилятор узла должен его.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Затем следует добавить указанный статическое свойство типа:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

При получении этого свойства всегда будет оцениваться как строка «Hello!». `GetterCode` Для F # предложение, которое представляет код, который создает компилятор узла для получения свойства используют свойство. Дополнительные сведения о предложениях см. в разделе [Цитирование кода (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Добавьте XML-документации к свойству.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Теперь подключите указанного свойства в указанный тип. Указанный член необходимо присоединить к только один тип. В противном случае член никогда не будут доступны.

```fsharp
t.AddMember staticProp
```

Теперь создайте предоставленный конструктор, который не принимает никаких параметров.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

`InvokeCode` Для завершения работы конструктор возвращает F # предложение, которое представляет код, который создает компилятор узла, при вызове конструктора. Например можно использовать следующий конструктор:

```fsharp
new Type10()
```

Экземпляр указанного типа создается с базовыми данными «Данные объекта». Заключенные в кавычки кода включает в себя преобразование [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) поскольку этот тип стирания это обеспечило тип (как вы указали при объявлении предоставленного типа).

Добавьте XML-документации в конструктор и добавьте в предоставленный тип предоставленного конструктора:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Создайте второй предоставленный конструктор, принимающий один параметр:

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

`InvokeCode` Для конструктора снова возвращает F # предложение, которое представляет код, созданный в компиляторе базовой для вызова метода. Например можно использовать следующий конструктор:

```fsharp
new Type10("ten")
```

Экземпляр указанного типа создается с базовыми данными «10». Вы уже могли заметить, `InvokeCode` функция возвращает предложения. Входные данные для этой функции — это список выражений, по одному на параметра конструктора. В этом случае выражение, которое представляет одно значение параметра доступно в `args.[0]`. Код для вызова конструктора приводит возвращаемое значение к типу удаленных `obj`. После добавления второй конструктор указанного типа, можно создать свойство предоставленный экземпляр:

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

При получении данного свойства возвращается длина строки, который является объектом представления. `GetterCode` Свойство возвращает F # предложение, которое указывает код, который создает компилятор узла для получения свойства. Как и `InvokeCode`, `GetterCode` функция возвращает предложения. В компиляторе базовой вызывает эту функцию с помощью списка аргументов. В этом случае аргументы включают только одно выражение, представляющее экземпляр, на котором вызывается метод получения значения, к которому можно получить с помощью `args.[0]`. Реализация `GetterCode` затем получает эту предложениям результат в удаленных введите `obj`, и использовать приведение типов для удовлетворения компилятора механизм для проверки типов, что объект представляет собой строку. В следующей части `makeOneProvidedType` предоставляет метод экземпляра с одним параметром.

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

Наконец создайте вложенный тип, содержащий 100 вложенных свойств. Создание это вложенные типа и его свойства откладывается, то есть, вычисляется по запросу.

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>Дополнительные сведения о типах удаленных предоставленный

В примере в этом разделе приводятся только *удалены указанные типы*, которая особенно полезны в следующих ситуациях:

- При написании поставщика для информационное пространство, который содержит только данные и методы.

- При написании поставщика, где семантику точных типов среды выполнения не являются критически важными для практического использования информационное пространство.

- При написании поставщика для информационное пространство, который является слишком большим, взаимосвязанных, что это не технически возможно, для создания реальных типов .NET для, информационное пространство.

В этом примере каждый предоставленный тип удаляется, чтобы ввести `obj`, и все случаи использования тип отображается как тип `obj` в скомпилированный код. На самом деле, базовых объектов в этих примерах являются строками, но тип будет отображаться как `System.Object` в .NET, скомпилированного кода. Как и с все случаи использования стирания типа явная упаковка, распаковка-преобразование и приведение к увенчается успехом удалены типов. В этом случае исключение приведения, которое является недопустимой, может привести к при использовании объекта. Поставщик среды выполнения можно определить свой собственный тип частного представления для защиты от false представления. Невозможно определить удаленных типов в F #. Только в том случае, если типы могут быть удалены. Необходимо понимать последствия, оба practical и семантике, с помощью удаленных типов для поставщика тип или поставщик, который предоставляет удалены типов. Удаленный тип не имеет реальной .NET типа. Таким образом невозможно выполнить точное отражение на тип, и может подвергнуть опасности удаленных типов при использовании приведений среды выполнения и другие технологии, использующие семантику типа точное время выполнения. Subversion удаленных типов часто приводит к исключениям приведения типа во время выполнения.

### <a name="choosing-representations-for-erased-provided-types"></a>Выбор представления, для удаления предоставляемые типы

Некоторые примеры использования удаленных указанными типами нет представления не требуется. Например удаленных в тип может содержать только статические свойства и члены и конструкторы не, и возвращает экземпляр типа отсутствуют методы и свойства. Если вы можете связаться удаленных экземпляров указан тип, необходимо учитывать следующие вопросы:

**Что такое стирания предоставленного типа?**

- Стирание предоставленного типа — как тип отображается в скомпилированном коде .NET.

- Стирания типа предоставленный класс удаленных всегда является первой не удалены базового типа в цепочке наследования типа.

- Всегда является стирания типа предоставленный интерфейс удаленных `System.Object`.

**Что такое представления предоставленного типа**

- Набор возможных объектов для удаленных указан тип, называются его представления. В примере в этом документе, типы представлений всех удаленных предоставленный `Type1..Type100` всегда являются строковых объектов.

Все представления, предоставленного типа должен быть совместим с стирания предоставленного типа. (В противном случае компилятор F # вызывает эту ошибку для использования поставщика типа, или создается непроверяемый код .NET, который недопустим. Поставщик типов не является допустимым, если он возвращает код, который предоставляет представление, которое является недопустимым.)

Это представление для предоставленных объектов можно выбрать с помощью любого из следующих методов, каждый из которых является очень распространенным:

- Если просто строго типизированную оболочку подается на существующий тип .NET, часто имеет смысл для типа, чтобы стереть к этому типу, используйте экземпляры этого типа представления, или в виде. Этот подход используется, когда большинство существующих методов этого типа по-прежнему имеет смысла при использовании строго типизированной версии.

- Если вы хотите значительно создания API, который отличается от любого существующего API .NET, имеет смысл создать типы среды выполнения, которые будут стирания типа и представления для существующих.

В примере в этом документе используются строки для представления предоставленных объектов. Часто возможно, можно использовать другие объекты, для представления. Например словарь можно использовать как контейнер свойств:

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

Кроме того может определить тип в ваш поставщик типов, который будет использоваться во время выполнения для формирования представления, а также один или несколько операций среды выполнения:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

Если элементы затем можно создать экземпляры этого типа объектов:

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

В этом случае может (необязательно) служит этот тип стирания типа, указав этот тип как `baseType` при создании `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Полученный опыт

Выше было рассмотрено, как создать простой поставщик стирания типа, который предоставляет широкий набор типов, свойства и методы. В этом разделе также объясняется понятие стирания типа, включая некоторые преимущества и недостатки предоставления удаленных типов от поставщика тип и обсуждается представления удаленных типов.

## <a name="a-type-provider-that-uses-static-parameters"></a>Тип поставщика, использующего статические параметры

Возможность параметризовать поставщиков типов, статических данных делает возможными интересные ситуации, даже в случаях, когда поставщик не требуется доступ к любым локальным или удаленным данным. В этом разделе вы узнаете некоторые основные методы объединения такой поставщик.

### <a name="type-checked-regex-provider"></a>Тип проверки регулярного выражения поставщика

Представьте, что вы хотите реализовать поставщик типов для регулярных выражений, который создает оболочку .NET <xref:System.Text.RegularExpressions.Regex> библиотеки в интерфейсе, который предоставляет следующие гарантии времени компиляции:

- Проверка того, является ли допустимым регулярным выражением.

- Задание именованных свойств, основываясь на все имена групп в регулярном выражении.

В этом разделе показано, как создать с помощью поставщиков типов `RegexTyped` введите параметризует что шаблон регулярного выражения и обеспечивает следующие преимущества. Компилятор сообщит об ошибке, если указанный шаблон не является допустимым, и поставщика типов можно извлечь группы из шаблона, таким образом, они будут доступны с помощью именованных свойств на совпадения. При разработке поставщика типов, следует учитывать, как должен выглядеть его предоставленным API для конечных пользователей и как такая схема будет преобразовано в код .NET. Приведенный ниже показано, как использовать такой API для получения компонентов области кода:

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

Обратите внимание на следующие моменты:

- Стандартный тип Regex представляет параметризованного `RegexTyped` типа.

- `RegexTyped` Конструктор приводит к вызову конструктора Regex, передавая статический тип аргумента для шаблона.

- Результаты `Match` метод представлены стандартные <xref:System.Text.RegularExpressions.Match> типа.

- Каждой именованной группы приводит к указанного свойства, и обращение к свойству приводит к использованию индексатора при совпадении `Groups` коллекции.

Следующий код является основной логики для реализации такой поставщик, и в этом примере не включает добавление всех элементов в указанный тип. Сведения о каждой добавлен элемент см. соответствующий раздел далее в этом разделе. Полный текст кода, загрузите образец с [F # 3.0 образец пакета](https://fsharp3sample.codeplex.com) на веб-сайте Codeplex.

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

Обратите внимание на следующие моменты:

- Поставщик типа принимает два параметра статического: `pattern`, который является обязательным и `options`, какие — дополнительными (так как значения по умолчанию).

- Когда статические аргументы указаны, можно создать экземпляр регулярного выражения. Этот экземпляр будет создания исключения, если регулярное выражение имеет неправильный формат, и эта ошибка будет выводиться пользователям.

- В рамках `DefineStaticParameters` обратного вызова, определите тип, который будет возвращаться после аргументов.

- Этот код задает `HideObjectMethods` значение true, чтобы возможности IntelliSense будет оставаться упрощенный. Этот атрибут приводит к `Equals`, `GetHashCode`, `Finalize`, и `GetType` члены для подавления из списка IntelliSense для предоставленного объекта.

- Использовании `obj` как базовый тип метода, но вы будете использовать `Regex` объект как представление времени выполнения этого типа, как показано в следующем примере.

- Вызов `Regex` конструктор вызывает <xref:System.ArgumentException> при регулярное выражение является недопустимым. Компилятор перехватывает это исключение и сообщает пользователю сообщение об ошибке, во время компиляции, а также в редакторе Visual Studio. Это исключение позволяет регулярные выражения для проверки без запуска приложения.

Так как она не содержит все значимые методы и свойства типа, определенного выше еще не полезно. Сначала добавьте статический `IsMatch` метод:

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

Предыдущий код определяет метод `IsMatch`, который принимает в качестве входных данных строку и возвращает `bool`. Единственной сложностью является использование `args` аргумент `InvokeCode` определения. В этом примере `args` является список предложений, который представляет аргументы для этого метода. Если метод является методом экземпляра, первый аргумент представляет `this` аргумент. Тем не менее для статического метода, перечислены все, что явные аргументы метода. Обратите внимание, что тип значения, заключенные в кавычки должен совпадать с заданным типом возвращаемого значения (в этом случае `bool`). Также Обратите внимание, что этот код использует `AddXmlDoc` метод, чтобы убедиться в том, что указанный метод также имеет полезные документации, можно указать через IntelliSense.

Добавьте экземпляр метода Match. Тем не менее, этот метод должен возвращать значение заданного `Match` так, чтобы группы может осуществляться в сильно типизированной форме. Таким образом, сперва надо объявить `Match` типа. Так как этот тип зависит от шаблона, переданному как статический аргумент, этот тип должен быть вложен в определении параметризованного типа:

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

Затем добавьте одно свойство в тип соответствия для каждой группы. Во время выполнения, соответствие представляется в виде <xref:System.Text.RegularExpressions.Match> значение, поэтому необходимо использовать предложение, которое определяет свойство <xref:System.Text.RegularExpressions.Match.Groups> индексированное свойство, чтобы получить соответствующую группу.

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

Опять же Обратите внимание на то, что вы добавляете XML-документации для указанного свойства. Также Обратите внимание, что можно прочитать свойство, если `GetterCode` предоставляются функции и свойства могут записываться таким образом, если `SetterCode` функция предоставляется, поэтому результирующее свойство доступно только для чтения.

Теперь вы можете создать метод экземпляра, который возвращает значение данного `Match` типа:

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

Так как вы создаете методом экземпляра `args.[0]` представляет `RegexTyped` экземпляр, на котором вызывается метод, и `args.[1]` является входного аргумента.

Наконец Предоставьте конструктор для создания экземпляров предоставленного типа.

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Конструктор просто стирает для создания стандартного экземпляра регулярных выражений .NET, который упаковывается в объект еще раз, так как `obj` является стирания предоставленного типа. После этого изменения пример использования API, который указан выше работает ожидаемым образом. Ниже приведен полный и последнее:

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
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

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

### <a name="key-lessons"></a>Полученный опыт

В этом разделе описано создание поставщика типов, которая работает на его статические параметры. Поставщик проверяет параметр static и предоставляет операции, основанные на его значение.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Поставщик типа, который поддерживается службой локальных данных

Часто можно поставщиков типов для представления API, основываясь на не только статические параметры, но данные из локальных или удаленных систем. В этом разделе рассматриваются поставщиков типов, основанных на локальные данные, такие как локальные файлы данных.

### <a name="simple-csv-file-provider"></a>Поставщик простой CSV-файлов

В качестве простого примера рассмотрим поставщик типов для доступа к научных данных в формате с разделителями разделенных запятыми (CSV). В этом разделе предполагается, что CSV-файлы содержат строку заголовка, следуют данных с плавающей запятой, как показано в следующей таблице:

|Расстояние (счетчик)|Время (секунды)|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

В этом разделе показано, как указать тип, который можно использовать для получения строк с `Distance` свойство типа `float<meter>` и `Time` свойство типа `float<second>`. Для простоты предполагается следующее:

- Имена заголовков делятся без единицы измерения или в формате «Имя (единицы)» и не содержать запятые.

- Единицы — все единицы международной Systeme (SI) в качестве [модуль Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) модуль определяет.

- Единицы просты (например, вести учет), а не составные (например, счетчик в секунду).

- Все столбцы содержат данных с плавающей запятой.

Более полный поставщик может ослабить эти ограничения.

Еще раз первым делом необходимо учитывать, как должен выглядеть интерфейс API. Учитывая `info.csv` файл с содержимым из предыдущей таблицы (в формате с разделителями запятыми), пользователи поставщика, должны иметь возможность писать код, аналогичный приведенному ниже:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

В этом случае компилятор должен преобразовать эти вызовы во что-то, как в следующем примере:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

Оптимальной перевод потребуется поставщик типов для определения настоящие `CsvFile` типа в сборке поставщика типов. Поставщики типов часто используют несколько вспомогательные типы и методы для создания оболочки важных логических. Поскольку меры будут удалены во время выполнения, можно использовать `float[]` как удаленный тип, для строки. Компилятор будет рассматривать разные столбцы как разные меры типа. Например, первый столбец в нашем примере имеет тип `float<meter>`, а второй — `float<second>`. Тем не менее вместо удаленных представление может оставаться довольно просто.

В следующем коде показано ядро реализации.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

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

Обратите внимание на следующие аспекты реализации:

- Перегруженные конструкторы позволяют исходный файл или ту, которая имеет идентичные схемы для чтения. Этот шаблон является наиболее распространенным, при написании поставщика типа для источников данных локальным или удаленным, и этот шаблон позволяет локального файла для использования в качестве шаблона для удаленных данных.

- Можно использовать [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) значение, которое передается в конструктор поставщика типа для разрешения относительных имен файла.

- Можно использовать `AddDefinitionLocation` метод для определения местоположения указанные свойства. Таким образом Если вы используете `Go To Definition` указанное свойство CSV-файл откроется в Visual Studio.

- Можно использовать `ProvidedMeasureBuilder` типов для поиска SI единицы измерения и создания соответствующего `float<_>` типов.

### <a name="key-lessons"></a>Полученный опыт

В этом разделе описано создание поставщика типов для локальный источник данных с простой схемой, содержащийся в самого источника данных.

## <a name="going-further"></a>Продвигаясь дальше

В следующих разделах приведены рекомендации для дальнейшего изучения.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Рассмотрим скомпилированный код для удаленных типов

Чтобы получить некоторое представление о том, как использование поставщика типов соответствует код, который создается, рассмотрим следующую функцию с помощью `HelloWorldTypeProvider` , используемый этой статьи.

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Вот изображение декомпилированным с помощью ildasm.exe результирующий код:

```
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

Как показано в примере, все упоминания типа `Type1` и `InstanceProperty` свойства были удалены, оставляя участвующие только операции с типами среды выполнения.

### <a name="design-and-naming-conventions-for-type-providers"></a>Проектирование и соглашения об именовании для поставщиков типов

Следует соблюдайте следующие соглашения, при разработке поставщиков типов.

**Поставщики для подключения к протоколов** в общем случае имена большинство библиотек DLL поставщика для данных и служб подключения протоколов, таких как OData или SQL-подключений, должны заканчиваться `TypeProvider` или `TypeProviders`. Например используйте имя библиотеки DLL, которое примерно следующего вида:

```
  Fabrikam.Management.BasicTypeProviders.dll
```

Убедитесь, что предоставленный типы являются членами соответствующего пространства имен и указывает реализуемый протокол подключения:

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Программа поставщиков для общего кода**.  Для программы поставщика типов, например для регулярных выражений поставщик типов может быть частью базовой библиотеки, как показано в следующем примере:

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

В этом случае предоставленный тип будет выглядеть в соответствующий момент в соответствии с соглашениями разработки обычных .NET:

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

**Источники данных одноэлементный**. Некоторые поставщики типов и предоставлять только данные, так как к одного выделенного источника данных. В этом случае следует удалить `TypeProvider` суффикс и используйте соглашения об обычном для .NET:

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Дополнительные сведения см. в разделе `GetConnection` разработать соглашение, которое описано далее в этом разделе.

### <a name="design-patterns-for-type-providers"></a>Конструктивные шаблоны для поставщиков типов

В следующих разделах шаблоны проектирования, которые можно использовать при разработке поставщиков типов.

#### <a name="the-getconnection-design-pattern"></a>Шаблон разработки GetConnection

Большинство поставщиков типов должен быть записан использовать `GetConnection` шаблон, который используется поставщиками типов в FSharp.Data.TypeProviders.dll, как показано в следующем примере:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Поставщики типов с удаленным данным и службам

Перед созданием поставщик типа, который поддерживается службой удаленным данным и службам, необходимо учитывать ряд проблем, свойственных подключенных программирования. Эти проблемы включают следующее:

- Сопоставление схем

- жизнеспособность и недействительности при наличии изменений схемы

- Кэширование схем

- асинхронные реализации операций доступа к данным

- Поддержка запросов, включая запросы LINQ

- учетные данные и проверки подлинности

В этом разделе не рассматриваются эти дополнительные проблемы.

### <a name="additional-authoring-techniques"></a>Дополнительные методы разработки

При написании собственных поставщиков типов, можно использовать из следующих способов.

### <a name="creating-types-and-members-on-demand"></a>Создание типов и членов по запросу

ProvidedType API откладывала версиях AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Эти версии используются для создания пространств по запросу типов.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Типы массивов и экземпляров универсального типа

Предоставленные члены, (, подписи включают типы массивов, типы byref и упрощено создание экземпляров универсальных типов), внесенные с помощью обычного `MakeArrayType`, `MakePointerType`, и `MakeGenericType` на любом экземпляре <xref:System.Type>, в том числе `ProvidedTypeDefinitions`.

> [!NOTE]
> В некоторых случаях может потребоваться использовать вспомогательный модуль `ProvidedTypeBuilder.MakeGenericType`.  См. в разделе [документации по пакету SDK поставщика типа](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) для получения дополнительных сведений.

### <a name="providing-unit-of-measure-annotations"></a>Предоставляя единицы измерения заметок

ProvidedTypes API предоставляет вспомогательные методы для предоставления мер заметок. Например, чтобы указать тип `float<kg>`, используйте следующий код:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Для обеспечения типа `Nullable<decimal<kg/m^2>>`, используйте следующий код:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Доступ к ресурсам локальной скрипт или локальной для проекта

Каждый экземпляр поставщика типа может быть задан `TypeProviderConfig` значение во время построения. Это значение содержит «разрешение папку» для поставщика (то есть папка проекта для компиляции или каталог, содержащий сценарий), список сборок, на которые имеются ссылки и другие сведения.

### <a name="invalidation"></a>Недействительность

Поставщики могут вызывать недействительности сигналов, чтобы уведомить службу F #, которая предположения схемы может изменяться. В случае аннулирования typecheck Повторено, если поставщик находится в Visual Studio. Этот сигнал будет игнорироваться, если поставщик размещается в F # Interactive или компилятором F # (fsc.exe).

### <a name="caching-schema-information"></a>Кэширование сведений о схеме

Поставщики часто необходимо кэшировать доступ к информации схемы. Кэшированные данные должны храниться с помощью имени файла, которое задано как параметр статического или сведений о пользователях. Пример кэширования схемы — `LocalSchemaFile` параметра в тип поставщиков в `FSharp.Data.TypeProviders` сборки. В реализации этих поставщиков этот статический параметр указывает поставщика типов для использования данных схемы в указанный локальный файл вместо обращения к источнику данных по сети. Для использования кэшированных данных схемы, необходимо также задать параметр static `ForceUpdate` для `false`. Похожий прием можно использовать для доступа к данным сетевой и автономный режим.

### <a name="backing-assembly"></a>Резервная сборка

При компиляции `.dll` или `.exe` файл, DLL-файл резервного для создаваемых типов статически связываются с итоговой сборки. Эта ссылка создается путем копирования определения типов промежуточного языка (IL) и все управляемые ресурсы из находится резервная сборка, в окончательную сборку. При использовании F # Interactive, DLL-файла, резервное, не будут копироваться и вместо этого загружаются непосредственно в F # Interactive процесс.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Исключения и диагностики из поставщиков типов

Все случаи использования все элементы из существующих может вызывать исключения. Во всех случаях если поставщик типа создает исключение, компилятор узла атрибуты ошибку поставщику определенного типа.

- Тип поставщика исключения никогда не должно приводить внутренних ошибках компилятора.

- Поставщики типов не может сообщать об ошибках.

- Если поставщик типа размещается в компилятор F #, среды разработки F # или F # Interactive, перехватываются все исключения из этого поставщика. Свойство сообщения всегда текст ошибки, и появляется не выполняется трассировка стека. Если вы собираетесь исключение, можно создавать следующие примеры: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.

#### <a name="providing-generated-types"></a>Предоставляя созданных типов

На данный момент в этом документе показано, как обеспечить удаленных типов. Также можно использовать механизм поставщика типа в F # для предоставления созданных типов, которые добавляются в качестве реальной определениях типов .NET в программу пользователей. Вы должны ссылаться на созданный предоставляемые типы с помощью определения типа.

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

0,2 ProvidedTypes вспомогательный код, который является частью выпуска F # 3.0 имеет только ограниченную поддержку для предоставления созданных типов. Следующие инструкции должны выполняться условия для определения создаваемого типа.

- `isErased` должно быть присвоено `false`.

- Необходимо добавить созданный тип для заново созданного `ProvidedAssembly()`, который представляет контейнер для созданного кода фрагментов.

- Поставщик должен иметь сборку, которая содержит фактический резервного .NET DLL-файл, соответствующий файл DLL-файл на диске.

## <a name="rules-and-limitations"></a>Правила и ограничения

При написании поставщиков типов, примите во внимание следующие правила и ограничения.

### <a name="provided-types-must-be-reachable"></a>Указанные типы должен быть доступен

Все входящие типы должны быть доступны с невложенными типы. Типы невложенными предоставляется в вызове `TypeProviderForNamespaces` конструктор или вызов `AddNamespace`. Например, если поставщик предоставляет тип `StaticClass.P : T`, необходимо убедиться, что T является типом невложенными или вложенными в один.

Например, некоторые поставщики имеют статический класс, такие как `DataTypes` , содержащие такие `T1, T2, T3, ...` типов. В противном случае ошибка сообщает, что была обнаружена ссылка на тип "T" в сборке A, но не удалось найти тип в этой сборке. При появлении этой ошибки убедитесь, что все подтипы можно получить доступ из поставщика типов. Примечание: Эти `T1, T2, T3...` типы называются *на лету* типов. Не забудьте поместить их в пространство имен доступны или родительского типа.

### <a name="limitations-of-the-type-provider-mechanism"></a>Ограничения механизма тип поставщика

Механизм поставщиков типов в F # имеет следующие ограничения:

- Базовая инфраструктура для поставщиков типов в F # не поддерживает универсальные типы или предоставленный универсальных методов.

- Механизм не поддерживает вложенные типы с статические параметры.

## <a name="development-tips"></a>Советы по разработке

Следующие советы могут оказаться полезными в процессе разработки.

### <a name="run-two-instances-of-visual-studio"></a>Запустите два экземпляра Visual Studio

Можно разрабатывать в один экземпляр поставщика типов и проверьте его поставщик в другой, так как тест интегрированная среда разработки будет установить блокировку на DLL-файл, который предотвращает перестраивается поставщика типов. Таким образом при создании поставщика в первом экземпляре, а затем необходимо повторно открыть второй экземпляр после построения поставщика необходимо закрыть второй экземпляр Visual Studio.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Отладка с помощью вызовов fsc.exe поставщиков типов

Поставщики типов можно вызвать с помощью следующих средств:

- fsc.exe (компилятор командной строки F #)

- fsi.exe (F # Interactive компилятора)

- devenv.exe (Visual Studio)

Поставщики типов часто можно отлаживать проще всего с помощью fsc.exe в файл тестового скрипта (например, файл script.fsx). Можно запустить отладчик из командной строки.

```
  devenv /debugexe fsc.exe script.fsx
```

  Можно использовать ведение журнала печать в stdout.

## <a name="see-also"></a>См. также

- [Поставщики типов](index.md)
- [Тип поставщика SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
