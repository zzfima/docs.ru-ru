---
title: Элемент <Application> (.NET Native)
ms.date: 03/30/2017
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
ms.openlocfilehash: e26826b3d8674b536ab0897182da58bc02cfd00b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128519"
---
# <a name="application-element-net-native"></a>Элемент > приложения \<(.NET Native)
Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения и применяет политику отражения среды выполнения ко всем программным элементам приложения.  
  
 Элемент \<Directives>  
Элемент \<Application> (rd.xml)  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Application Activate="policy_setting"  
             Browse="policy_setting"  
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
 В следующих разделах описаны атрибуты, дочерние и родительские элементы. В таблице дочерних элементов политика имеет отношение к метаданным, к которым программные элементы получают доступ по время выполнения.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Activate`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.|  
|`Browse`|Отражение|Необязательный атрибут. Определяет запрос для получения сведений о типах или перечисляет типы, но не включает динамический доступ во время выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.|  
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.|  
|`DataContractSerializer`|Сериализация|Необязательный атрибут Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Сериализация|Необязательный атрибут Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Сериализация|Необязательный атрибут Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interop|Необязательный атрибут Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.|  
|`MarshalDelegate`|Interop|Необязательный атрибут Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.|  
|`MarshalStructure`|Interop|Необязательный атрибут Определяет политику для маршалинга структуры в машинный код.|  
  
## <a name="all-attributes"></a>Все атрибуты  
  
|значения|Описание|  
|-----------|-----------------|  
|*policy_setting*|Параметр для этой политики, относящихся к типам в приложении. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|Применяет политику ко всем типам в определенной сборке.|  
|[\<Namespace>](namespace-element-net-native.md)|Применяет политику ко всем типам в определенном пространстве имен.|  
|[\<Type>](type-element-net-native.md)|Применяет политику для конкретного типа, например, класса или структуры.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику к сконструированному универсальному типу. Например, элемент [\<TypeInstantiation>](typeinstantiation-element-net-native.md) можно использовать для определения политики для типа `List<String>`.|  
|[\<Method>](method-element-net-native.md)|Применяет политику к методу определенного типа.|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Применяет политику к сконструированному универсальному методу.|  
|[\<Property>](property-element-net-native.md)|Применяет политику к свойству определенного типа.|  
|[\<Field>](field-element-net-native.md)|Применяет политику к полю определенного типа.|  
|[\<Event>](event-element-net-native.md)|Применяет политику к событию определенного типа.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|Корневой элемент файла директив среды выполнения.|  
  
## <a name="remarks"></a>Заметки  
 Элемент [\<Directives>](directives-element-net-native.md) может содержать ноль или один элемент `<Application>`. Несколько элементов `<Application>` в одном файле директив отражения не поддерживаются.  
  
 Элемент `<Application>` можно использовать одним из двух способов:  
  
- В качестве контейнера для определения программных элементов, метаданные которых требуются во время выполнения. В этом случае элементу `<Application>` необязательно иметь какие-либо атрибуты. Во время компиляции средства компилятора выполняют поиск всех библиотек, в том числе основных библиотек .NET Framework, на наличие программных элементов, определенных дочерними элементами элемента `<Application>`. В отличие от этого, средства компилятора выполняют поиск только тех библиотек, которые назначены элементом [\<Library>](library-element-net-native.md), на наличие программных элементов, определенных дочерними элементами элемента [\<Library>](library-element-net-native.md).  
  
- Как элемент, который задает политику уровня приложения для отражения, сериализации и взаимодействия. Атрибуты элемента `<Application>` определяют политику уровня приложения, которая может быть переопределена дочерними элементами элементов `<Application>` или [\<Library>](library-element-net-native.md).  
  
## <a name="see-also"></a>См. также

- [Элемент > библиотеки \<](library-element-net-native.md)
- [Директивы \<> Element](directives-element-net-native.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
