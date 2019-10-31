---
title: Ссылка на файл конфигурации директив среды выполнения (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: f4c51dc269775d14d395cb464b3787cc987e086d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128126"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a>Ссылка на файл конфигурации директив среды выполнения (rd.xml)

Файл директив среды выполнения (. rd.xml) — это файл конфигурации XML, который определяет, доступны ли элементы в указанной программе для отражения. Ниже приведен пример файла директив среды выполнения:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a>Структура файла директив среды выполнения

Файл директив среды выполнения использует пространство имен `http://schemas.microsoft.com/netfx/2013/01/metadata`.

Корневой элемент — элемент [Directives](directives-element-net-native.md). Он может содержать ноль или больше элементов [Library](library-element-net-native.md) и ноль или один элемент [Application](application-element-net-native.md), как показано в следующей структуре. Атрибуты элемента [Application](application-element-net-native.md) могут определять политику отражения среды выполнения для приложения или служить контейнером для дочерних элементов. Элемент [Library](library-element-net-native.md), с другой стороны, это просто контейнер. Дочерние элементы элементов [Application](application-element-net-native.md) и [Library](library-element-net-native.md) определяют типы, методы, поля, свойства и события, доступные для отражения.

Для получения справочной информации выберите элементы из приведенной ниже структуры или см. раздел [Элементы директив среды выполнения](runtime-directive-elements.md). В следующей иерархии многоточие отмечает рекурсивную структуру. Информация в скобках указывает, является этот элемент необязательным или обязательным, и если он используется, сколько экземпляров (один или несколько) разрешено.

[Директивы](directives-element-net-native.md) [1:1] [приложение](application-element-net-native.md) [0:1] [Сборка](assembly-element-net-native.md) [0: m] [пространство имен](namespace-element-net-native.md) [0: m]. . .
[Введите](type-element-net-native.md) [0: M]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[Пространство имен](namespace-element-net-native.md) [0: m], [пространство имен](namespace-element-net-native.md) [0: m]. . .
[Введите](type-element-net-native.md) [0: M]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[Введите](type-element-net-native.md) [0: m] [подтипы](subtypes-element-net-native.md) (подклассы содержащего типа) [O:1] [Type](type-element-net-native.md) [0: M]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[AttributeImplies](attributeimplies-element-net-native.md) (вмещающий тип является атрибутом) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0: m] [метод](method-element-net-native.md) [0: m], [параметр](parameter-element-net-native.md) [0: m] [typeparameter находится вне](typeparameter-element-net-native.md) [0: m] [GenericParameter](genericparameter-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) ( сконструированный универсальный метод) [0: M] [свойство](property-element-net-native.md) [0: m] [поле](field-element-net-native.md) [0: m] [событие](event-element-net-native.md) [0: m] [TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: m], [тип](type-element-net-native.md) [0: m]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[Метод](method-element-net-native.md) [0: m] [параметр](parameter-element-net-native.md) [0: m] [typeparameter находится вне](typeparameter-element-net-native.md) [0: M] [GenericParameter](genericparameter-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: m] [свойство](property-element-net-native.md) [0: m] [поле](field-element-net-native.md) [0: m], [событие](event-element-net-native.md) [0: m] [ Библиотека](library-element-net-native.md) [0: m] [Сборка](assembly-element-net-native.md) [0: m], [пространство имен](namespace-element-net-native.md) [0: m]. . .
[Введите](type-element-net-native.md) [0: M]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[Пространство имен](namespace-element-net-native.md) [0: m], [пространство имен](namespace-element-net-native.md) [0: m]. . .
[Введите](type-element-net-native.md) [0: M]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[Введите](type-element-net-native.md) [0: m] [подтипы](subtypes-element-net-native.md) (подклассы содержащего типа) [O:1] [Type](type-element-net-native.md) [0: M]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[AttributeImplies](attributeimplies-element-net-native.md) (вмещающий тип является атрибутом) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0: m] [метод](method-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: m] [свойство](property-element-net-native.md) [0: m], [поле](field-element-net-native.md) [0: m], [событие](event-element-net-native.md) [0 : M] [TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: m], [Тип](type-element-net-native.md) [0: m]. . .
[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M]. . .
[Метод](method-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: m] [свойство](property-element-net-native.md) [0: M] [поле](field-element-net-native.md) [0: m], [событие](event-element-net-native.md) [0: m]

Элемент [Application](application-element-net-native.md) может не иметь атрибутов или иметь атрибуты политики, рассмотренные в разделе [Директивы и политика среды выполнения](#Directives).

Элемент [Library](library-element-net-native.md) имеет один атрибут `Name`, который определяет имя библиотеки или сборки без расширения файла. Например, следующий элемент [Library](library-element-net-native.md) применяется к сборке с именем Extensions.dll.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a>Директивы и политики среды выполнения

Сам элемент [Application](application-element-net-native.md), а также дочерние элементы элементов [Library](library-element-net-native.md) и [Application](application-element-net-native.md) определяют политику, то есть способ, с помощью которого приложение может применять отражение к программному элементу. Тип политики определяется с помощью атрибута элемента (например, `Serialize`). Значение политики определяется значением атрибута (например, `Serialize="Required"`).

Любая политика, заданная с помощью атрибута элемента применяется ко всем дочерним элементам, которые не определяют значение этой политики. Например, если политика определяется элементом [Type](type-element-net-native.md), эта политика применяется для всех вложенных типов и членов, для которых политика не указана явно.

Политика, которая может быть определена элементами [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) и [Type](type-element-net-native.md), отличается от политики, которая может быть определена для отдельных членов (элементами [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) и [Event](event-element-net-native.md)).

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a>Задание политики для сборок, пространств имен и типов

Элементы [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) и [Type](type-element-net-native.md) поддерживают следующие типы политик:

- `Activate` Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.

- `Browse` Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.

- `Dynamic` Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.

- `Serialize` Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек сторонних поставщиков, как сериализатор Newtonsoft JSON.

- `DataContractSerializer` Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.

- `DataContractJsonSerializer` Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.

- `XmlSerializer` Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.

- `MarshalObject` Определяет политику для маршалинга ссылочных типов в WinRT и COM.

- `MarshalDelegate` Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.

- `MarshalStructure` . Определяет политику для маршалинга структуры в машинный код.

Параметры, связанные с этими типами политики:

- `All` Включить политику для всех типов и членов, которые не удаляет цепочка инструментов.

- `Auto` Использовать поведение по умолчанию. (Отсутствие назначения политики эквивалентно установке политики `Auto`, если только эта политика не переопределяется, например, родительским элементом.)

- `Excluded` Выключить политику для программного элемента.

- `Public` Включить политику для открытых типов и членов, если только цепочка средство не определяет, что элемент является необязательным и поэтому удаляет его. (В последнем случае необходимо использовать `Required Public` чтобы обеспечить сохранение элемента с возможностями отражения.)

- `PublicAndInternal` Включить политику для открытых и внутренних типов и членов, если цепочка инструментов не удаляет их.

- `Required Public` Требует, чтобы цепочка инструментов поддерживала открытые типы и члены, независимо то того, используются они или нет, и включала для них политику.

- `Required PublicAndInternal` Требует, чтобы цепочка инструментов поддерживала открытые и закрытые типы и члены, независимо то того, используются они или нет, и включала для них политику.

- `Required All` Требует, чтобы цепочка инструментов поддерживала все типы и члены, независимо то того, используются они или нет, и включала для них политику.

Например, следующий файл директив среды выполнения определяет политику для всех типов и членов в сборке DataClasses.dll. Он включает отражение для сериализации все открытых свойств, обзор для всех типов и членов типа, активацию для всех типов (из-за атрибута `Dynamic` атрибут), а также отражение для всех открытых типов и членов.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a>Задание политики для членов

Элементы [Property](property-element-net-native.md) и [Field](field-element-net-native.md) поддерживают следующие типы политик:

- `Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.

- `Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование. Также управляет запросами сведений о содержащем типе.

- `Serialize` — Управляет доступом среды выполнения к членам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON. Эта политика может применяться для конструкторов, полей и свойств.

Элементы [Method](method-element-net-native.md) и [Event](event-element-net-native.md) поддерживают следующие типы политик:

- `Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.

- `Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование. Также управляет запросами сведений о содержащем типе.

 Параметры, связанные с этими типами политики:

- `Auto` — Использовать поведение по умолчанию. (Отсутствие назначения политики эквивалентно установке политики `Auto`, если только что-то ее не переопределяет.)

- `Excluded` — никогда не включать метаданные для члена.

- `Included`- включить политику, если родительский тип присутствует в выходных данных.

- `Required` — Требует, чтобы цепочка инструментов поддерживала этот член, даже если он не используется, и включала для него политику.

## <a name="runtime-directives-file-semantics"></a>Семантика файла директив среды выполнения

Политики могут быть определены одновременно для элементов более высокого уровня и более низкого уровня. Например, можно определить политики для сборки, а также для некоторых типов, содержащегося в этой сборке. Если конкретный элемент нижнего уровня не представлен, он наследует политику родительского элемента. Например, если элемент `Assembly` присутствует, а элементы `Type` нет, то политика, указанная в элементе `Assembly`, применяется для каждого типа в сборке. Несколько элементов могут также применить политику к одному и тому же программному элементу. Например, отдельные элементы [Assembly](assembly-element-net-native.md) могут определять один и тот же элемент политики для одной сборки по-разному. В следующих разделах объясняется, как политики для конкретного типа разрешается в таких случаях.

Элемент [Type](type-element-net-native.md) или [Method](method-element-net-native.md) универсального типа или метода применяет свою политику для всех экземпляров, которые не имеют собственной политики. Например, элемент `Type`, который определяет политику для <xref:System.Collections.Generic.List%601>, применяется для всех сконструированных экземпляров универсального типа, если только он переопределяется для определенного сконструированного универсального типа (например, `List<Int32>`) элементом `TypeInstantiation` . В противном случае, элементы определяют политику для именованного программного элемента.

Если элемент является неоднозначным, ядро ищет совпадения и при обнаружении точного совпадения, будет ее использовать. При обнаружении нескольких совпадений будет предупреждение или ошибка.

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a>Если две директивы применяют политику к одному и тому же программному элементу

Если два элемента в разных файлах директив среды выполнения пытаются установить один и тот же тип политики для одного программного элемента (например, сборки или типа) в разные значения, конфликт разрешается следующим образом:

1. Если элемент `Excluded` присутствует, он имеет приоритет.

2. `Required`имеет приоритет над не `Required`.

3. `All`имеет приоритет перед `PublicAndInternal`, который имеет приоритет над `Public`.

4. Любой явный параметр имеет приоритет над `Auto`.

Например, если один проект включает следующие два файла директив среды выполнения, устанавливается политика сериализации для DataClasses.dll на `Required Public` и `All`. В этом случае политика сериализации будет разрешаться как `Required All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

Однако, если две директивы в файле директив среды выполнения пытаются задать один и тот же тип политики одному программному элементу, то инструмент определения схемы XML отображает сообщение об ошибке.

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a>Если один и тот же тип политики применяется дочерними и родительскими элементами

Дочерние элементы переопределяют свои родительские элементы, в том числе параметр `Excluded`. Переопределение — основная причина, по которой требуется указать `Auto`.

В следующем примере параметр политики сериализации для значения everything в `DataClasses`, который не находится в`DataClasses.ViewModels`, был бы `Required Public`, а значение everything в `DataClasses` и `DataClasses.ViewModels` было бы `All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a>Если открытые универсальные типы и элементы экземпляра применяют один и тот же тип политики

В следующем примере `Dictionary<int,int>` назначается как политика  `Browse`, только если ядро имеет еще одну причину присвоить политику `Browse` (что было бы в противном случае поведением по умолчанию); В каждом экземпляре <xref:System.Collections.Generic.Dictionary%602> все члены будут доступны для просмотра.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a>Как определяется политика

Каждый тип политики имеет разный набор правил, определяющих, как присутствие этого типа политики влияет на другие конструкции.

#### <a name="the-effect-of-browse-policy"></a>Эффект политики Browse (Просмотр)

Применение политики `Browse` для типа включает в себя следующие изменения политики:

- Базовый тип типа помечается политикой `Browse`.

- Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.

- Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.

- Каждый интерфейс типа помечается политикой `Browse`.

- Тип каждого атрибута примененного к типу помечается политикой `Browse`.

- Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.

- Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.

Применение политики `Browse` для метода включает в себя следующие изменения политики:

- Каждый тип параметра метода помечается политикой `Browse`.

- Возвращаемый тип метода помечается политикой `Browse`.

- Содержащий тип метода помечается политикой `Browse`.

- Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.

- Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.

- Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.

- Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.

Применение политики `Browse` для поля включает в себя следующие изменения политики:

- Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.

- Тип поля помечается политикой `Browse`.

- Тип, к которому принадлежит поле помечается политикой `Browse`.

#### <a name="the-effect-of-dynamic-policy"></a>Эффект политики Dynamic (Динамическая)

Применение политики `Dynamic` для типа включает в себя следующие изменения политики:

- Базовый тип типа помечается политикой `Dynamic`.

- Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Dynamic`.

- Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.

- Каждый интерфейс типа помечается политикой `Browse`.

- Тип каждого атрибута примененного к типу помечается политикой `Browse`.

- Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.

- Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.

Применение политики `Dynamic` для метода включает в себя следующие изменения политики:

- Каждый тип параметра метода помечается политикой `Browse`.

- Возвращаемый тип метода помечается политикой `Dynamic`.

- Содержащий тип метода помечается политикой `Dynamic`.

- Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.

- Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.

- Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.

- Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.

- Этот метод может вызываться `MethodInfo.Invoke`, а создание делегата становится возможным с помощью <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.

Применение политики `Dynamic` для поля включает в себя следующие изменения политики:

- Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.

- Тип поля помечается политикой `Dynamic`.

- Тип, к которому принадлежит поле помечается политикой `Dynamic`.

#### <a name="the-effect-of-activation-policy"></a>Эффект от политики Activation (активация)

Применение политики Activation для типа включает в себя следующие изменения политики:

- Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.

- Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.

- Конструкторы типа помечаются политикой `Activation`.

Применение политики `Activation` для метода включает в себя следующие изменения политики:

- Конструктор может вызываться методами <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> и <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>. Для методов политика `Activation` оказывает действие только на конструкторы.

Применение политики `Activation` к полю не оказывает влияния.

#### <a name="the-effect-of-serialize-policy"></a>Эффект политики Serialize (сериализация)

Политика `Serialize` позволяет использовать общие сериализаторы, основанные на отражении. Тем не менее, поскольку точные шаблоны доступа к отражению сериализаторов сторонних разработчиков неизвестны Microsoft, эта политика может оказаться не совсем эффективной.

Применение политики `Serialize` для типа включает в себя следующие изменения политики:

- Базовый тип типа помечается политикой `Serialize`.

- Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.

- Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.

- Если тип является перечислением, массив типа помечается политикой `Serialize`.

- Если тип реализует <xref:System.Collections.Generic.IEnumerable%601>, `T` помечается политикой `Serialize`.

- Если тип является типом <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> или <xref:System.Collections.Generic.IReadOnlyList%601>, тогда `T[]` и <xref:System.Collections.Generic.List%601> помечаются политикой `Serialize`, однако ни один из членов типа интерфейса не помечаются политикой `Serialize`.

- Если тип является типом <xref:System.Collections.Generic.List%601>, то его члены не помечаются политикой `Serialize`.

- Если тип является типом <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> помечается политикой `Serialize`. Но члены типа не помечаются политикой `Serialize`.

- Если тип является типом <xref:System.Collections.Generic.Dictionary%602>, то его члены не помечаются политикой `Serialize`.

- Если тип реализует <xref:System.Collections.Generic.IDictionary%602>, `TKey` и `TValue` помечаются политикой `Serialize`.

- Каждый конструктор, каждый метод доступа к свойству и каждое поле помечается политикой `Serialize`.

Применение политики `Serialize` для метода включает в себя следующие изменения политики:

- Содержащий тип помечается политикой `Serialize`.

- Возвращаемый тип метода помечается политикой `Serialize`.

Применение политики `Serialize` для поля включает в себя следующие изменения политики:

- Содержащий тип помечается политикой `Serialize`.

- Тип поля помечается политикой `Serialize`.

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a>Воздействие политик XmlSerializer, DataContractSerializer и DataContractJsonSerializer

В отличие от политики `Serialize`, которая предназначена для сериализаторов на основе отражения, политики <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используются для включения набора сериализаторов, известных цепочке инструментов .NET Native. Эти сериализаторы не реализуются с помощью отражения, но наборы типов, которые могут быть сериализованы во время выполнения определяются так же, как типы, которые могут отражаться.

Применение одной из этих политик для типа позволяет сериализовать тип с помощью соответствующего сериализатора. Все типы, которые обработчик сериализации может статически определить, как нуждающиеся в сериализации, будут также сериализуемыми.

Эти политики не оказывают влияния на методы или поля.

Подробнее см. в подразделе "Различия в сериализаторах" раздела [Миграция приложения для Магазина Windows в .NET Native](migrating-your-windows-store-app-to-net-native.md).

## <a name="see-also"></a>См. также

- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Отражение и .NET Native](reflection-and-net-native.md)
