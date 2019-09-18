---
title: <Type>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ffe37540fe089bfd1e0eca1958498e725eb9b5b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049154"
---
# <a name="type-element-net-native"></a>\<Элемент > типа (.NET Native)

Применяет политику выполнения для конкретного типа, например класса или структуры.

## <a name="syntax"></a>Синтаксис

```xml
<Type Name="type_name"
      Activate="policy_type"
      Browse="policy_type"
      Dynamic="policy_type"
      Serialize="policy_type"
      DataContractSerializer="policy_setting"
      DataContractJsonSerializer="policy_setting"
      XmlSerializer="policy_setting"
      MarshalObject="policy_setting"
      MarshalDelegate="policy_setting"
      MarshalStructure="policy_setting" />
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Тип атрибута|Описание|
|---------------|--------------------|-----------------|
|`Name`|Общее|Обязательный атрибут. Задает имя типа.|
|`Activate`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.|
|`Browse`|Отражение|Необязательный атрибут. Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.|
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.|
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.|
|`DataContractSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|
|`DataContractJsonSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|
|`XmlSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|
|`MarshalObject`|Interop|Необязательный атрибут. Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.|
|`MarshalDelegate`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.|
|`MarshalStructure`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов значений в машинный код.|

## <a name="name-attribute"></a>Name - атрибут

|Значение|Описание|
|-----------|-----------------|
|*type_name*|Имя типа. Если этот элемент `<Type>` является дочерним элементом [\<Namespace>](namespace-element-net-native.md) или другого элемента `<Type>`, то атрибут *type_name* может содержать имя типа без его пространства имен. В противном случае атрибут *type_name* должен содержать полное имя типа.|

## <a name="all-other-attributes"></a>Все остальные атрибуты

|Значение|Описание|
|-----------|-----------------|
|*policy_setting*|Параметр, применяемый для этого типа политики. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<AttributeImplies>](attributeimplies-element-net-native.md)|Если содержащий тип является атрибутом, определяет политику выполнения для элементов кода, к которым применяется этот атрибут.|
|[\<Event>](event-element-net-native.md)|Применяет политику отражения события, относящегося к этому типу.|
|[\<Field>](field-element-net-native.md)|Применяет политику отражения поля, относящегося к этому типу.|
|[\<GenericParameter>](genericparameter-element-net-native.md)|Применяет политику к типу параметра универсального типа.|
|[\<ImpliesType>](impliestype-element-net-native.md)|Применяет политику к типу, если политика была применена для типа, представленного содержащим элементом `<Type>`.|
|[\<Method>](method-element-net-native.md)|Применяет политику отражения метода, относящегося к этому типу.|
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному методу, относящемуся к этому типу.|
|[\<Property>](property-element-net-native.md)|Применяет политику отражения к свойству, относящемуся к этому типу.|
|[\<Subtypes>](subtypes-element-net-native.md)|Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.|
|`<Type>`|Применяет политику отражения к вложенному типу.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<Application>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения.|
|[\<Assembly>](assembly-element-net-native.md)|Применяет политику отражения ко всем типам в указанной сборке.|
|[\<Library>](library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.|
|[\<Namespace>](namespace-element-net-native.md)|Применяет политику отражения ко всем типам в пространстве имен.|
|`<Type>`|Применяет политику отражения к типу и всем его членам.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|

## <a name="remarks"></a>Примечания

Атрибуты отражения, сериализации и взаимодействия являются необязательными. Если таковые отсутствуют, элемент `<Type>` служит в качестве контейнера, чьи дочерние типы определяют политику для отдельных элементов.

Если элемент `<Type>` является дочерним элементом [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), `<Type>` или [\<TypeInstantiation>](typeinstantiation-element-net-native.md), он переопределяет параметры политики, определенные в родительском элементе.

Элемент `<Type>` универсального типа применяет свою политику для всех экземпляров, которые не имеют собственной политики. Политика сконструированных универсальных типов определяется элементом [\<TypeInstantiation>](typeinstantiation-element-net-native.md).

Если тип является универсальным типом, к его имени добавляется символ апострофа (\`), за которым следует его число универсальных параметров. Например, атрибут `Name` элемента `<Type>` для класса <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> отображается как ``Name="System.Collections.Generic.List`1"``.

## <a name="example"></a>Пример

В следующем примере отражение используется для отображения сведений о полях, свойствах и методах класса <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Переменная `b` в примере <xref:Windows.UI.Xaml.Controls.TextBlock> является элементом управления. Так как просто извлекаются сведения о типе, доступность метаданных определяется параметром политики `Browse`.

 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]

 Так как метаданные для <xref:System.Collections.Generic.List%601> класса не включаются автоматически в цепочку инструментов .NET Native, в примере не отображаются сведения о запрашиваемом элементе во время выполнения. Для обеспечения необходимыми метаданными, добавьте следующий элемент `<Type>` в файл директивы среды выполнения. Обратите внимание, что поскольку мы предоставляем родительский элемент [<Namespace\>](namespace-element-net-native.md), нам не требуется указывать полное имя в элементе `<Type>`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="*Application*" Dynamic="Required All" />
      <Namespace Name ="System.Collections.Generic" >
        <Type Name="List`1" Browse="Required All" />
     </Namespace>
   </Application>
</Directives>
```

## <a name="example"></a>Пример
 В следующем примере отражение используется для получения объекта <xref:System.Reflection.PropertyInfo>, представляющего свойство <xref:System.String.Chars%2A?displayProperty=nameWithType>. Затем он использует метод <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> для извлечения значения седьмого знака в строке и для отображения всех символов в строке. Переменная `b` в примере <xref:Windows.UI.Xaml.Controls.TextBlock> является элементом управления.

 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]

 Поскольку метаданные для <xref:System.String> объекта недоступны, вызов <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> метода вызывает <xref:System.NullReferenceException> исключение во время выполнения при компиляции с помощью цепочки инструментов .NET Native. Чтобы избежать исключений и предоставить необходимые метаданные, добавьте следующий элемент `<Type>` элемент в файл директив среды выполнения:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
    <Type Name="System.String" Dynamic="Required Public"/> -->
  </Application>
</Directives>
```

## <a name="see-also"></a>См. также

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
