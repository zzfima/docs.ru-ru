---
title: "&lt;маршрутизация&gt; для &lt;serviceBehavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15e46f8d9550d4361ef92c1fa4860f17a2dfd088
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a>&lt;маршрутизация&gt; для &lt;serviceBehavior&gt;
Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.  
  
 \<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<Маршрутизация >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String" 
               routeOnHeadersOnly="Boolean" 
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|filterTable|Строка, в которой указано имя таблицы маршрутизации, содержащей фильтры, вычисляемые службой маршрутизации. Это значение должно соответствовать `name` атрибут [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) элемент в [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) раздела.|  
|routeOnHeaderOnly|Логическое значение, определяющее, какие части сообщения будут изучены фильтром: только заголовок или заголовок и текст сообщения. Значение по умолчанию — `true`.|  
|soapProcessingEnabled|Логическое значение, указывающее, будет ли выполняться обработка SOAP.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 Если добавить к конфигурации поведения службы, этот элемент конфигурации включает маршрутизацию для службы. В этом элементе можно указать фактическую таблицу маршрутизации, которая будет использоваться службой.  
  
 Используя этот раздел конфигурации, можно на лету изменять параметры маршрутизации при изменении шаблона развертывания. Во время выполнения можно зарегистрировать собственный модуль маршрутизации с новыми параметрами. В этом случае служба маршрутизации будет использовать обновленную конфигурацию для новых сеансов и сообщений (для уже запущенных на данных момент сообщений и сеансов будут применяться правила, действовавшие в момент их запуска).  Благодаря этому обеспечивается безопасная для сеансов и не требующая перезапуска повторная настройка службы маршрутизации во время выполнения.  
  
