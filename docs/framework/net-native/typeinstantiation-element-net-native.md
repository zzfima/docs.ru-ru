---
title: "Элемент &lt;TypeInstantiation&gt; (машинный код .NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Элемент &lt;TypeInstantiation&gt; (машинный код .NET)
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
|`Name`|Общие правила|Обязательный атрибут. Задает имя типа.|  
|`Arguments`|Общие|Обязательный атрибут. Задает аргументы универсального типа. При наличии нескольких аргументов, они разделяются запятыми.|  
|`Activate`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.|  
|`Browse`|Отражение|Необязательный атрибут. Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.|  
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.|  
|`DataContractSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации, который использует <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> класса.|  
|`DataContractJsonSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации JSON, который использует <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> класса.|  
|`XmlSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации XML, который использует <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> класса.|  
|`MarshalObject`|Interop|Необязательный атрибут. Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.|  
|`MarshalDelegate`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.|  
|`MarshalStructure`|Interop|Необязательный атрибут. Определяет политику для маршалинга структуры в машинный код.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|*Функция TYPE_NAME*|Имя типа. Если этот `<TypeInstantiation>` является дочерним элементом [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) элемент, [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) или другого `<TypeInstantiation>` элемент, *type_name* можно указать имя типа без его пространства имен. В противном случае — *type_name* должен содержать полное имя типа. Имя типа не является внутренним. Например, для <xref:System.Collections.Generic.List%601?displayProperty=fullName> объекта, `<TypeInstantiation>` элемент может выглядеть следующим образом:<br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a>Атрибут аргументов  
  
|Значение|Описание|  
|-----------|-----------------|  
|*type_argument*|Задает аргументы универсального типа. При наличии нескольких аргументов, они разделяются запятыми. Каждый аргумент должен содержать полное имя типа.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Значение для применения к этому типу политики для сконструированного универсального типа. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|Применяет политику отражения события, относящегося к этому типу.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|Применяет политику отражения поля, относящегося к этому типу.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Применяет политику к типу, если политика была применена для типа, представленного содержащим элементом `<TypeInstantiation>`.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Применяет политику отражения метода, относящегося к этому типу.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному методу, относящемуся к этому типу.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|Применяет политику отражения к свойству, относящемуся к этому типу.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к вложенному типу.|  
|`<TypeInstantiation>`|Применяет политику отражения к вложенному сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Применяет политику отражения ко всем типам в указанной сборке.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Применяет политику отражения ко всем типам в пространстве имен.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к типу и всем его членам.|  
|`<TypeInstantiation>`|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Примечания  
 Атрибуты отражения, сериализации и взаимодействия являются необязательными. Тем не менее, по крайней мере один должен присутствовать.  
  
 Если `<TypeInstantiation>` является дочерним элементом [ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md), или [ <> \</> \> ](../../../docs/framework/net-native/type-element-net-native.md), он переопределяет параметры политики, определенные в родительском элементе. Если [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) элемент определяет соответствующее определение универсального типа, `<TypeInstantiation>` переопределяет политику отражения среды выполнения только для экземпляров указанного сконструированного универсального типа.  
  
## <a name="example"></a>Пример  
 Следующий пример использует отражение для получения определения универсального типа из сконструированного <xref:System.Collections.Generic.Dictionary%602> объекта.</TKey, TValue> Отражение используется также для отображения сведений об <xref:System.Type> объекты, представляющие сконструированных универсальных типов и определений универсальных типов. Переменная `b` в примере является [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) элемента управления.  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 После компиляции с [!INCLUDE[net_native](../../../includes/net-native-md.md)] цепочка инструментов, в примере возникает исключение [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) исключение на строку, которая вызывает <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=fullName> метод. Чтобы избежать исключений и предоставить необходимые метаданные, добавьте следующий элемент `<TypeInstantiation>` элемент в файл директив среды выполнения:  
  
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
 [Ссылка на файл конфигурации директив (rd.xml) среды выполнения](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)