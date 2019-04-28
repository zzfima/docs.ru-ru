---
title: <Assembly> Элемент (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0788c05edace2142d348c679c73aa1b4404ce75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868866"
---
# <a name="assembly-element-net-native"></a>\<Сборка > элемент (машинный код .NET)
Применяет политику отражения среды выполнения ко всем типам в указанной сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Assembly Name="assembly_name"   
          Activate="policy_setting"  
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
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общие|Обязательный атрибут. Задает простое имя сборки.|  
|`Activate`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.|  
|`Browse`|Отражение|Необязательный атрибут. Определяет запрос для получения сведений о типах или перечисляет типы в сборке, но не включает динамический доступ во время выполнения.|  
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
|*assembly_name*|Простое имя сборки без расширения файла. Этот атрибут соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Например, имя сборки с именем Extensions.dll является «Extensions».<br /><br /> Можно также указать строковый литерал `*Application*` для применения политики ко всем сборкам в пакете приложения, вне зависимости от того, загружены ли эти сборки или нет. `*Application*` никогда не применяет политику к сборкам платформы .NET Framework.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Параметр для этого типа политики для всех типов в сборке. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Применяет политику отражения для всех типов в дочернем пространстве имен.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к типу.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения. Элемент [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) может иметь ноль, один или более элементов `<Assembly>`.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения. Элемент [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) может иметь ноль или один элемент `<Assembly>`.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<Assembly>` определяет политику среды выполнения для всех типов в сборке. Он отличается от элемента [\<Library>](../../../docs/framework/net-native/library-element-net-native.md), который указывает библиотеку, но зависит от его дочерних элементов для определения политики отражения среды выполнения. Элемент `<Assembly>` применяется ко всем типам в сборке, если они не переопределены дочерним элементом.  
  
 В следующем примере показано, как применять политику среды выполнения для всех типов сборки в пакете приложения путем назначения атрибуту `Name` значения "*Application\*". Элемент `<Assembly>` должен быть дочерним для элемента [\<Application>](../../../docs/framework/net-native/application-element-net-native.md).  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">   
  <Application>   
     <Assembly Name="*Application*" Dynamic="Required All" />   
  </Application>   
</Directives>  
```  
  
 Атрибуты `Activate`, `Browse`, `Dynamic` и `Serialize` необязательны. Тем не менее, элемент `<Assembly>` должен содержать хотя бы один из этих атрибутов.  
  
## <a name="see-also"></a>См. также

- [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)
