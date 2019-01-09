---
title: '&lt;BackupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 1a6a7ac42b379dd8fb2ba80cf6a3a38998c26a59
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146554"
---
# <a name="ltbackuplistgt"></a>&lt;BackupList&gt;
Представляет раздел конфигурации для определения резервного списка, который перечисляет набор конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной. Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.  Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.  
  
 \<system.serviceModel >  
\<Маршрутизация >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Строка, в которой приведено имя, используемое для указания этого списка конечных точек.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Список резервных конечных точек.|  
  
## <a name="remarks"></a>Примечания  
 Этот раздел содержит упорядоченную коллекцию конечных точек, в которые будет передаваться сообщение в случае, если при отправке в основную конечную точку возникает исключение связи.  
  
 Если отправка в основную конечную точку в списке в `endpointName` атрибут [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) завершается ошибкой с исключением связи, служба маршрутизации попытается отправить сообщение в первую конечную точку в этом раздел конфигурации. Если эта отправка также приведет к возникновению исключения связи, служба маршрутизации попытается отправить сообщение в следующую точку, указанную в этом разделе, пока отправка не завершится успешно или не возвратит ошибку, не связанную с исключением связи, либо пока ошибки не будут возвращены для всех конечных точек из коллекции.  
  
 В следующем примере Если отправка в основную конечную точку с именем «Destination» возвращает исключение связи, служба попытается отправить сообщение в alternateServiceQueue «». Если эта попытка также возвращает исключение связи, то служба маршрутизации попытается отправить сообщение в следующую конечную точку в коллекции.  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
