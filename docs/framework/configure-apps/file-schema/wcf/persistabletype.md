---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 3ea99d360ceb1e3fe6e97cbf9c8827dd7c853f63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256528"
---
# <a name="persistabletype"></a>\<persistableType >
Задает все восстанавливаемые типы.  
  
 \<system.ServiceModel>  
\<comContracts >  
\<comContract >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|id|Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.|  
|имя|Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|Коллекция элементов `persistableType`.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Интеграция с приложениями COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Практическое руководство. Настройка параметров службы COM +](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
