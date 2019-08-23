---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940500"
---
# <a name="webhttp"></a>\<> http
Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации. Это поведение при использовании в сочетании с [ \<привязкой WebHttpBinding >](webhttpbinding.md) Standard включает модель веб-программирования для службы Windows Communication Foundation (WCF).  
  
 \<системой. > ServiceModel  
\<> поведения  
\<endpointBehaviors >  
\<> поведения  
\<> http  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования. Автоматический выбор формата отключен по умолчанию в целях обратной совместимости. Автоматический выбор формата можно включить программно или через конфигурацию.|  
|defaultBodyStyle|Задает стиль по умолчанию для текста возвращаемых сообщений. Дополнительные сведения см. в <xref:System.ServiceModel.Web.WebMessageBodyStyle> разделе и [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Определяет формат ответа по умолчанию для исходящих сообщений. Дополнительные сведения см. в разделе [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Получает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).|  
|helpEnabled|Возвращает или задает значение, определяющее, будет ли включена страница справки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> поведения](behavior-of-endpointbehaviors.md)|Задает набор поведений конечной точки.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Интеграция с AJAX и поддержка JSON](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
