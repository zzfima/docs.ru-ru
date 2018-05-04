---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 1dce767d1cb6705084f0776b8ba8a168031fcb04
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebhttpgt"></a>&lt;webHttp&gt;
Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации. Такое поведение, при использовании в сочетании с [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) Стандартная привязка включает модель веб-программирования для службы Windows Communication Foundation (WCF).  
  
 \<система. ServiceModel >  
\<поведения >  
\<endpointBehaviors >  
\<поведение >  
\<webHttp >  
  
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
|defaultBodyStyle|Задает стиль по умолчанию для текста возвращаемых сообщений. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Web.WebMessageBodyStyle> и [WCF Web HTTP форматирование](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Определяет формат ответа по умолчанию для исходящих сообщений. Дополнительные сведения см. в разделе [WCF Web HTTP форматирование](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Возвращает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).|  
|helpEnabled|Возвращает или задает значение, определяющее, будет ли включена страница справки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает набор поведений конечной точки.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [Интеграция с AJAX и поддержка JSON](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
