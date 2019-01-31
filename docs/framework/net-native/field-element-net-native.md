---
title: <Field> Элемент (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4a062e060e7b367f0d56b3633238de74ae8ed88
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281675"
---
# <a name="field-element-net-native"></a>\<Поле > элемент (машинный код .NET)
Применяет политику отражения среды выполнения к полю.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание:|  
|---------------|--------------------|-----------------|  
|`Name`|Общие правила|Обязательный атрибут. Определяет имя поля.|  
|`Browse`|Отражение|Необязательный атрибут. Определяет запрос для получения сведений о поле или перечисляет поле, но не включает динамический доступ во время выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к полю для включения динамического программирования. Эта политика гарантирует, что поле можно задать или получить динамически во время выполнения.|  
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к полю, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как, например, сериализатор Newtonsoft JSON или для привязки данных.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание:|  
|-----------|-----------------|  
|*method_name*|Имя поля. Тип поля определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание:|  
|-----------|-----------------|  
|*policy_setting*|Параметр, применяемый к этому типу политики для поля. Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к типу и всем его членам.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Примечания  
 Если политика поля не определена явно, оно наследует политику среды выполнения своего родительского элемента.  
  
## <a name="see-also"></a>См. также
- [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
