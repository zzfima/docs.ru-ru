---
title: Параметры политики директив среды выполнения
ms.date: 03/30/2017
ms.assetid: cb52b1ef-47fd-4609-b69d-0586c818ac9e
ms.openlocfilehash: 7a8933decaec45e8000f3f3d1717847f333deddd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738506"
---
# <a name="runtime-directive-policy-settings"></a>Параметры политики директив среды выполнения

> [!NOTE]
> В этом разделе рассматривается предварительная версия программного обеспечения для разработчиков машинного кода .NET. Предварительную версию можно скачать на [веб-сайте Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (требуется регистрация).

Параметры политики директив среды выполнения для машинного кода .NET определяют доступность метаданных для типов и членов типов во время выполнения. Без необходимых метаданных операции, зависящие от отражения, сериализации и десериализации или маршалинга типов платформы .NET Framework в COM или среду выполнения Windows, могут быть не выполнены, в результате чего создается исключение. Наиболее общие исключения, [MissingMetadataException](missingmetadataexception-class-net-native.md) и (в случае взаимодействия) [MissingInteropDataException](missinginteropdataexception-class-net-native.md).

Параметры политики среды выполнения управляются файлом директив среды выполнения (. rd.xml). Каждая директива среды выполнения определяет политику для определенного программного элемента, например сборки (элемент [\<Assembly>](assembly-element-net-native.md)), типа (элемент [\<Type>](type-element-net-native.md)) или метода (элемент [\<Method>](method-element-net-native.md)). Директива включает один или несколько атрибутов, которые определяют типы политики отражения, типы политик сериализации и типы политик взаимодействия, описанных в следующем разделе. Значение атрибута определяет параметр политики.

## <a name="policy-types"></a>Типы политик

Файлы директив среды выполнения распознают три типа политик: отражение, сериализация и взаимодействие.

- Типы политики отражения определяют, какие метаданные доступны во время выполнения для отражения:

  - `Activate` управляет доступом среды выполнения к конструкторам для включения активации экземпляров.

  - `Browse` управляет запросами информации о программных элементах.

  - `Dynamic` управляет доступом среды выполнения ко всем типам и членам для включения динамического программирования.

  В следующей таблице перечислены типы политики отражения, а также программные элементы, с которыми они могут использоваться.

  |Элемент|Активировать|Обзор|Динамический|
  |-------------|--------------|------------|-------------|
  |[\<Application>](application-element-net-native.md)|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)||✔️|✔️|
  |[\<Field>](field-element-net-native.md)||✔️|✔️|
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)||✔️|✔️|
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)||✔️|✔️|
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)||✔️|✔️|
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|

- Типы политики сериализации определяют, какие метаданные доступны во время выполнения для сериализации и десериализации:

  - `Serialize` управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек сторонних поставщиков, как сериализатор Newtonsoft JSON.

  - `DataContractSerializer` управляет доступом среды выполнения к конструкторам, полям и свойствам, чтобы включить сериализацию экземпляров типов с помощью класса <xref:System.Runtime.Serialization.DataContractSerializer>.

  - `DataContractJsonSerializer` управляет доступом среды выполнения к конструкторам, полям и свойствам, чтобы включить сериализацию экземпляров типов с помощью класса <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

  - `XmlSerializer` управляет доступом среды выполнения к конструкторам, полям и свойствам, чтобы включить сериализацию экземпляров типов с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.

  В следующей таблице перечислены типы политики сериализации, а также программные элементы, с которыми они могут использоваться.

  |Элемент|Сериализация|DataContractSerializer|DataContractJsonSerializer|XmlSerializer|
  |-------------|---------------|----------------------------|--------------------------------|-------------------|
  |[\<Application>](application-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)|||||
  |[\<Field>](field-element-net-native.md)|✔️||||
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)|||||
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|||||
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)|✔️||||
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|✔️|

- Типы политики взаимодействия определяют, какие метаданные доступны во время выполнения для передачи ссылочных типов, типов значений и указателей функций в COM и среду выполнения Windows:

  - `MarshalObject` управляет внутренним маршалингом в COM и среду выполнения Windows для ссылочных типов.

  - `MarshalDelegate` управляет внутренним маршалингом типов делегатов в качестве указателей функций.

  - `MarshalStructure` управляет внутренним маршалингом в COM и среду выполнения Windows для типов значений.

  В следующей таблице перечислены типы политики взаимодействия, а также программные элементы, с которыми они могут использоваться.

  |Элемент|MarshalObject|MarshalDelegate|MarshalStructure|
  |-------------|-------------------|---------------------|----------------------|
  |[\<Application>](application-element-net-native.md)|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)||||
  |[\<Field>](field-element-net-native.md)||||
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)||||
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)||||
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)||||
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|

## <a name="policy-settings"></a>Параметры политики

Каждый типу политики может быть задано одно из значений, перечисленных в следующей таблице. Обратите внимание, что элементы, представляющие члены типов поддерживают иной набор параметров политики, чем другие элементы.

|Параметр политики|Description|Элементы `Assembly`, `Namespace`, `Type` и `TypeInstantiation`|Элементы `Event`, `Field`, `Method`, `MethodInstantiation` и `Property`|
|--------------------|-----------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|
|`All`|Включает политику для всех типов и членов, которые цепочка инструментов машинного кода .NET не удаляет.|✔️||
|`Auto`|Задает использование политики по умолчанию для типа политики для данного программного элемента. Это аналогично пропуску политики для этого типа политики. `Auto` обычно используется для указания того, что политика наследуется от родительского элемента.|✔️|✔️|
|`Excluded`|Указывает, что политика отключена для определенного программного элемента. Например, директива среды выполнения:<br /><br /> `<Type Name="BusinessClasses.Person" Browse="Excluded" Dynamic="Excluded" />`<br /><br /> Указывает, что метаданные для класса `BusinessClasses.Person` недоступны либо для обзора, либо для создания динамического экземпляра и изменения объектов `Person`.|✔️|✔️|
|`Included`|Включает политику, если доступны метаданные для родительского типа.||✔️|
|`Public`|Включает политику для открытых типов или членов, если только цепочка инструментов не определяет, что тип или член является необязательным и поэтому удаляет его. Этот параметр отличается от `Required Public`, который гарантирует, что метаданные для открытых типов и членов всегда доступны, даже если цепочка инструментов определяет, что они не нужны.|✔️||
|`PublicAndInternal`|Включает политику для открытых и внутренних типов или членов, если только цепочка инструментов не определяет, что тип или член является необязательным и поэтому удаляет его. Этот параметр отличается от `Required PublicAndInternal`, который гарантирует, что метаданные для открытых и внутренних типов и членов всегда доступны, даже если цепочка инструментов определяет, что они не нужны.|✔️||
|`Required`|Указывает, что политика для члена включена, и эти метаданные будут доступны, даже если член встречается для использования.||✔️|
|`Required Public`|Включает политику для открытых типов и членов и гарантирует, что эти метаданные для открытых типов и членов всегда доступен. Этот параметр отличается от `Public`, который делает метаданные для открытых типов и членов доступными, только если цепочка инструментов определяет, что это необходимо.|✔️||
|`Required PublicAndInternal`|Включает политику для открытых и внутренних типов или членов и гарантирует, что эти метаданные для открытых и внутренних типов и членов всегда доступны. Этот параметр отличается от `PublicAndInternal`, который делает метаданные для открытых и внутренних типов и членов доступными, только если цепочка инструментов определяет, что это необходимо.|✔️||
|`Required All`|Требует, чтобы цепочка инструментов сохранила все типы и члены, независимо то того, используются они или нет, и включает политику для них.|✔️||

## <a name="see-also"></a>См. также раздел

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
