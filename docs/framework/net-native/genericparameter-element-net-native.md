---
title: Элемент <GenericParameter> (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf2b06b14252f152c1eece6f9c0d317482a24b27
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039517"
---
# <a name="genericparameter-element-net-native"></a>Элемент \<GenericParameter > (.NET Native)
Применяет политику к параметру типа универсального типа или метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общее|Обязательный атрибут. Имя универсального параметра. Например, для универсального делегата <xref:System.Func%603>, значение атрибута `Name` равно «TResult» для применения политики среды выполнения к возвращаемому значению делегата.|  
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
  
|значения|Описание|  
|-----------|-----------------|  
|*generic_parameter_name*|Обязательный атрибут. Имя универсального параметра типа. Например, для универсального делегата <xref:System.Func%603> значение *generic_parameter_name*, равное "TResult", применяет политику среды выполнения к возвращаемому значению делегата.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|значения|Описание|  
|-----------|-----------------|  
|*policy_setting*|Параметр, применяемый для этого типа политики. Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|Применяет политику отражения среды выполнения к конструктору или методу.|  
|[\<Type>](type-element-net-native.md)|Применяет политику отражения среды выполнения для конкретного типа, например, класса или структуры.|  
  
## <a name="remarks"></a>Заметки  
 Элемент `<GenericParameter>` является дочерним для элемента [\<Method>](method-element-net-native.md) или [\<Type>](type-element-net-native.md) и используется для применения политики к определенному параметру универсального типа, который задается его именем в сигнатуре универсального типа или метода.  
  
 Элемент `<GenericParameter>` особенно полезен при использовании сериализаторов. В следующем примере используется элемент `<GenericParameter>`, который позволяет применить политику к типу `T` в вызовах к перегрузкам метода [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) сериализатора NewtonSoft JSON.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a>См. также

- [Элемент \<Method>](method-element-net-native.md)
- [Элемент > типа\<](type-element-net-native.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
