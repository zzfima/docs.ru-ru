---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940407"
---
# <a name="webscriptendpoint"></a>\<Вебскриптендпоинт >
Этот элемент конфигурации определяет стандартную конечную точку с [ \<](webhttpbinding.md) фиксированной привязкой > WebHttpBinding [ \<](enablewebscript.md) , которая автоматически добавляет енаблевебскрипт поведение >. Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.  
  
\<системой. > ServiceModel  
\<Стандардендпоинтс >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|webEndpointType|Строка, указывающая тип конечной точки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Стандардендпоинтс >](standardendpoints.md)|Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
