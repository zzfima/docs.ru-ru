---
title: "Элемент &lt;Namespace&gt; (машинный код .NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Элемент &lt;Namespace&gt; (машинный код .NET)
Применяет политику отражения среды выполнения ко всем типам в указанном пространстве имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<Namespace Name="namespace_name"   
           Activate="policy_type"   
           Browse="policy_type" />  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
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
|`Name`|Общие правила|Обязательный атрибут. Указывает имя пространства имен.|  
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
|*namespace_name*|Имя пространства имен. Если <> \> является дочерним элементом [ <> \</> \> ](../../../docs/framework/net-native/application-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/library-element-net-native.md), или [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) элемент, *namespace_name* должно быть полным именем пространства имен. Если <> \> является дочерним элементом другого <> \> элемент, *namespace_name* должен быть относительным именем пространства имен.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Значение для этого типа политики для всех типов в пространстве имен. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<Namespace>`|Применяет политику отражения среды выполнения для всех типов в родительском пространстве имен.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к типу.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения. [ <> \> ](../../../docs/framework/net-native/application-element-net-native.md) Элемент может иметь ноль, один или более [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) элементы.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Применяет политику отражения среды выполнения ко всем типам в указанной сборке.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения. [ <> \> ](../../../docs/framework/net-native/library-element-net-native.md) Элемент может иметь ноль или один [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) элемента.|  
|`<Namespace>`|Применяет политику отражения для всех типов в родительском пространстве имен.|  
  
## <a name="remarks"></a>Примечания  
 Атрибуты `Activate`, `Browse`, `Dynamic` и `Serialize` необязательны. Если таковые отсутствуют, элемент `<Namespace>` используется только как контейнер для дочерних элементов. Если они присутствуют, элемент `<Namespace>` применяет политика отражения среды выполнения ко всем типам в указанном пространстве имен.  
  
 Если он является дочерним элементом [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) элемент, `<Namespace>` переопределяет политику отражения среды выполнения, определяется [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) элемента.  
  
## <a name="see-also"></a>См. также  
 [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Ссылка на файл конфигурации директив (rd.xml) среды выполнения](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)