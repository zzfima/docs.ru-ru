---
title: "&lt;add&gt; для &lt;entries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b01ad9e608fca669c28124cf5a68781d86058308
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a>&lt;add&gt; для &lt;entries&gt;
Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента. Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.  
  
 \<system.serviceModel >  
\<Маршрутизация >  
\<routingTables >  
\<Таблица >  
\<записи >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|backupList|Строка, указывающая ссылку на резервный список конечных точек.|  
|конечная точка|Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.|  
|filterName|Строка, в которой указана ссылка на элемент фильтра.|  
|priority|Целое число, задающее приоритет этой записи.<br /><br /> Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом. Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.<br /><br /> Это значение является необязательным.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
