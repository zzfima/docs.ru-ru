---
title: Элемент <Namespace> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: b6d7a45de14d0fb8eb2e27a02c86510f630be9e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128263"
---
# <a name="namespace-element-net-native"></a>Элемент > \<namespace (.NET Native)
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
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общее|Обязательный атрибут. Указывает имя пространства имен.|  
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
|*namespace_name*|Имя пространства имен. Если элемент \<Namespace> является дочерним элементом для элемента [\<Application>](application-element-net-native.md), [\<Library>](library-element-net-native.md) или [\<Assembly>](assembly-element-net-native.md), *namespace_name* должно быть полным именем пространства имен. Если элемент \<Namespace> является дочерним элементом другого элемента \<Namespace>, то *namespace_name* должно быть относительным именем пространства имен.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|значения|Описание|  
|-----------|-----------------|  
|*policy_setting*|Значение для этого типа политики для всех типов в пространстве имен. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<Namespace>`|Применяет политику отражения среды выполнения для всех типов в родительском пространстве имен.|  
|[\<Type>](type-element-net-native.md)|Применяет политику отражения к типу.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения. Элемент [\<Application>](application-element-net-native.md) может иметь ноль, один или более элементов [\<Assembly>](assembly-element-net-native.md).|  
|[\<Assembly>](assembly-element-net-native.md)|Применяет политику отражения среды выполнения ко всем типам в указанной сборке.|  
|[\<Library>](library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения. Элемент [\<Library>](library-element-net-native.md) может иметь ноль или один элемент [\<Assembly>](assembly-element-net-native.md).|  
|`<Namespace>`|Применяет политику отражения для всех типов в родительском пространстве имен.|  
  
## <a name="remarks"></a>Заметки  
 Атрибуты `Activate`, `Browse`, `Dynamic` и `Serialize` необязательны. Если таковые отсутствуют, элемент `<Namespace>` используется только как контейнер для дочерних элементов. Если они присутствуют, элемент `<Namespace>` применяет политика отражения среды выполнения ко всем типам в указанном пространстве имен.  
  
 Если это дочерний элемент элемента [\<Assembly>](assembly-element-net-native.md), то элемент `<Namespace>` переопределяет политику отражения среды выполнения, определенную элементом [\<Assembly>](assembly-element-net-native.md).  
  
## <a name="see-also"></a>См. также

- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
