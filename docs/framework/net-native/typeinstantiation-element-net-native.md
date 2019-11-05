---
title: Элемент <TypeInstantiation> (.NET Native)
ms.date: 03/30/2017
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
ms.openlocfilehash: 9069856b3d8739724d148b5eea5d4188c8b8b9e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128681"
---
# <a name="typeinstantiation-element-net-native"></a>Элемент \<TypeInstantiation > (.NET Native)
Применяет политику отражения среды применения к сконструированному универсальному типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
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
|`Arguments`|Общее|Обязательный атрибут. Задает аргументы универсального типа. При наличии нескольких аргументов, они разделяются запятыми.|  
|`Activate`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.|  
|`Browse`|Отражение|Необязательный атрибут. Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.|  
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.|  
|`DataContractSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interop|Необязательный атрибут. Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.|  
|`MarshalDelegate`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.|  
|`MarshalStructure`|Interop|Необязательный атрибут. Определяет политику для маршалинга структуры в машинный код.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|значения|Описание|  
|-----------|-----------------|  
|*type_name*|Имя типа. Если этот элемент `<TypeInstantiation>` является дочерним элементом элемента [\<Namespace>](namespace-element-net-native.md), [\<Type>](type-element-net-native.md) или другого элемента `<TypeInstantiation>`, *type_name* может определять имя типа без его пространства имен. В противном случае атрибут *type_name* должен содержать полное имя типа. Имя типа не является внутренним. Например, для объекта <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> элемент `<TypeInstantiation>` может выглядеть следующим образом:<br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a>Атрибут аргументов  
  
|значения|Описание|  
|-----------|-----------------|  
|*type_argument*|Задает аргументы универсального типа. При наличии нескольких аргументов, они разделяются запятыми. Каждый аргумент должен содержать полное имя типа.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|значения|Описание|  
|-----------|-----------------|  
|*policy_setting*|Значение для применения к этому типу политики для сконструированного универсального типа. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Event>](event-element-net-native.md)|Применяет политику отражения события, относящегося к этому типу.|  
|[\<Field>](field-element-net-native.md)|Применяет политику отражения поля, относящегося к этому типу.|  
|[\<ImpliesType>](impliestype-element-net-native.md)|Применяет политику к типу, если политика была применена для типа, представленного содержащим элементом `<TypeInstantiation>`.|  
|[\<Method>](method-element-net-native.md)|Применяет политику отражения метода, относящегося к этому типу.|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному методу, относящемуся к этому типу.|  
|[\<Property>](property-element-net-native.md)|Применяет политику отражения к свойству, относящемуся к этому типу.|  
|[\<Type>](type-element-net-native.md)|Применяет политику отражения к вложенному типу.|  
|`<TypeInstantiation>`|Применяет политику отражения к вложенному сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения.|  
|[\<Assembly>](assembly-element-net-native.md)|Применяет политику отражения ко всем типам в указанной сборке.|  
|[\<Library>](library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.|  
|[\<Namespace>](namespace-element-net-native.md)|Применяет политику отражения ко всем типам в пространстве имен.|  
|[\<Type>](type-element-net-native.md)|Применяет политику отражения к типу и всем его членам.|  
|`<TypeInstantiation>`|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Заметки  
 Атрибуты отражения, сериализации и взаимодействия являются необязательными. Тем не менее, по крайней мере один должен присутствовать.  
  
 Если элемент `<TypeInstantiation>` является дочерним элементом элемента [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md) или [\<Type>](type-element-net-native.md), он переопределяет параметры политики, определенные родительским элементом. Если элемент [\<Type>](type-element-net-native.md) определяет соответствующее определение универсального типа, элемент `<TypeInstantiation>` переопределяет политику отражения среды выполнения только для экземпляров указанного сконструированного универсального типа.  
  
## <a name="example"></a>Пример  
 В следующем примере отражение используется для получения определения универсального типа из сконструированного объекта <xref:System.Collections.Generic.Dictionary%602>. Отражение используется также для отображения сведений об объектах<xref:System.Type>, представляющих сконструированные универсальные типы и определения универсальных типов. Переменная `b` в примере является элементом управления <xref:Windows.UI.Xaml.Controls.TextBlock>.  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 После компиляции с помощью цепочки инструментов .NET Native в примере создается исключение [MissingMetadataException](missingmetadataexception-class-net-native.md) в строке, которая вызывает метод <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType>. Чтобы избежать исключений и предоставить необходимые метаданные, добавьте следующий элемент `<TypeInstantiation>` элемент в файл директив среды выполнения:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>См. также

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
