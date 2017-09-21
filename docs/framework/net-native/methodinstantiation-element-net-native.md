---
title: "Элемент &lt;MethodInstantiation&gt; (машинный код .NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d247b2ea8a1b6a908e3eee5082638813545f144d
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="ltmethodinstantiationgt-element-net-native"></a>Элемент &lt;MethodInstantiation&gt; (машинный код .NET)
Применяет политику отражения среды выполнения к сконструированному универсальному методу.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общие правила|Обязательный атрибут. Задает имя метода.|  
|`Signature`|Общие|Необязательный атрибут. Определяет именованные параметры метода. Несколько именованных параметров разделяются запятыми. Атрибут `Signature` позволяет различать перегруженные методы.|  
|`Arguments`|Общие|Обязательный атрибут. Задает аргументы универсального типа. При наличии нескольких аргументов, они разделяются запятыми.|  
|`Browse`|Отражение|Необязательный атрибут. Определяет запрос для получения сведений о методе или перечисляет методы, но не включает динамический вызов во время выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструктору или методу для включения динамического программирования. Эта политика гарантирует, что член может быть вызван динамически во время выполнения.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|*method_name*|Имя метода. Тип метода определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).|  
  
## <a name="signature-attribute"></a>Сигнатура атрибута  
  
|Значение|Описание|  
|-----------|-----------------|  
|*method_signature*|Определяет именованные параметры метода. При наличии нескольких параметров, они разделяются запятыми.|  
  
## <a name="arguments-attribute"></a>Атрибут аргументов  
  
|Значение|Описание|  
|-----------|-----------------|  
|*method_arguments*|Задает аргументы универсального типа. При наличии нескольких аргументов, они разделяются запятыми. Каждый аргумент должен содержать полное имя типа.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Параметр, применяемый к этому типу политики для метода. Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику отражения к типу и всем его членам.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<MethodInstantiation>`  переопределяет политику отражения среды выполнения его соответствующего открытого универсального метода.  
  
## <a name="see-also"></a>См. также  
 [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Элемент \<Method>](../../../docs/framework/net-native/method-element-net-native.md)

