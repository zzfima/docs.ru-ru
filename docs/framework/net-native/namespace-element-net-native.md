---
title: "Элемент &lt;Namespace&gt; (машинный код .NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
caps.latest.revision: 20
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f92797e9c06762602c30d7c3ed8e6b0d6e579bbf
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="ltnamespacegt-element-net-native"></a>Элемент &lt;Namespace&gt; (машинный код .NET)
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
|`DataContractSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName>.|  
|`DataContractJsonSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName>.|  
|`XmlSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>.|  
|`MarshalObject`|Interop|Необязательный атрибут. Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.|  
|`MarshalDelegate`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.|  
|`MarshalStructure`|Interop|Необязательный атрибут. Определяет политику для маршалинга структуры в машинный код.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|*namespace_name*|Имя пространства имен. Если элемент \<Namespace> является дочерним элементом для элемента [\<Application>](../../../docs/framework/net-native/application-element-net-native.md), [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) или [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), *namespace_name* должно быть полным именем пространства имен. Если элемент \<Namespace> является дочерним элементом другого элемента \<Namespace>, то *namespace_name* должно быть относительным именем пространства имен.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Значение для этого типа политики для всех типов в пространстве имен. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<Namespace>`|Применяет политику отражения среды выполнения для всех типов в родительском пространстве имен.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к типу.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения. Элемент [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) может иметь ноль, один или более элементов [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md).|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Применяет политику отражения среды выполнения ко всем типам в указанной сборке.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения. Элемент [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) может иметь ноль или один элемент [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md).|  
|`<Namespace>`|Применяет политику отражения для всех типов в родительском пространстве имен.|  
  
## <a name="remarks"></a>Примечания  
 Атрибуты `Activate`, `Browse`, `Dynamic` и `Serialize` необязательны. Если таковые отсутствуют, элемент `<Namespace>` используется только как контейнер для дочерних элементов. Если они присутствуют, элемент `<Namespace>` применяет политика отражения среды выполнения ко всем типам в указанном пространстве имен.  
  
 Если это дочерний элемент элемента [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), то элемент `<Namespace>` переопределяет политику отражения среды выполнения, определенную элементом [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md).  
  
## <a name="see-also"></a>См. также  
 [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)

