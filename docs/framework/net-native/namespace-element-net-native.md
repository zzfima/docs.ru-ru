---
title: <Namespace>Элемент (.NET Родной)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: 06d88a7b0f95c7c1dbe98818b847c92e08a57a19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180956"
---
# <a name="namespace-element-net-native"></a>\<Название> элемент (.NET Родной)
Применяет политику отражения среды выполнения ко всем типам в указанном пространстве имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Namespace Name="namespace_name"
           Activate="policy_type"
           Browse="policy_type"  
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
  
|attribute|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общие сведения|Обязательный атрибут. Указывает имя пространства имен.|  
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
  
|Значение|Описание|  
|-----------|-----------------|  
|*namespace_name*|Имя пространства имен. Если \<элемент Namespace> является ребенком [ \<>приложения, ](application-element-net-native.md) [ \<>библиотеки ](library-element-net-native.md)или *namespace_name* [ \<](assembly-element-net-native.md) элемента>сборки, namespace_name должны быть полностью квалифицированным именем пространства имен. Если элемент \<Namespace> является дочерним элементом другого элемента \<Namespace>, то *namespace_name* должно быть относительным именем пространства имен.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Значение для этого типа политики для всех типов в пространстве имен. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<Namespace>`|Применяет политику отражения среды выполнения для всех типов в родительском пространстве имен.|  
|[\<Тип>](type-element-net-native.md)|Применяет политику отражения к типу.|  
|[\<>typeInstantiation](typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Применение>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения. Элемент [ \<приложения>](application-element-net-native.md) может иметь ноль, один или несколько [ \<](assembly-element-net-native.md) элементов сборки>.|  
|[\<>ассамблеи](assembly-element-net-native.md)|Применяет политику отражения среды выполнения ко всем типам в указанной сборке.|  
|[\<Библиотечная>](library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения. Элемент [ \<библиотеки>](library-element-net-native.md) может иметь ноль или один [ \<](assembly-element-net-native.md) элемент>сборки.|  
|`<Namespace>`|Применяет политику отражения для всех типов в родительском пространстве имен.|  
  
## <a name="remarks"></a>Remarks  
 Атрибуты `Activate`, `Browse`, `Dynamic` и `Serialize` необязательны. Если таковые отсутствуют, элемент `<Namespace>` используется только как контейнер для дочерних элементов. Если они присутствуют, элемент `<Namespace>` применяет политика отражения среды выполнения ко всем типам в указанном пространстве имен.  
  
 Когда он является ребенком [ \<Ассамблеи](assembly-element-net-native.md) `<Namespace>`>элементом, этот элемент отменяет политику отражения времени выполнения, определяемую [ \<Ассамблеей>](assembly-element-net-native.md) элементом.  
  
## <a name="see-also"></a>См. также раздел

- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
