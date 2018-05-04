---
title: '&lt;NET.TCP&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9312d5f7544a794f036f0a623df0d537eb96d145
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltnettcpgt"></a>&lt;NET.TCP&gt;
Задает параметры конфигурации для службы общего доступа к портам Net.Tcp, которая позволяет нескольким процессам совместно использовать один и тот же порт протокола TCP.  
  
 \<system.serviceModel.activation >  
\<NET.TCP >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`listenBacklog`|Целое число, указывающее максимальное количество необработанных соединений, принятых от общего соединения, но еще не переданных службам Windows Communication Foundation (WCF). Значение по умолчанию — 10.|  
|`maxPendingAccepts`|Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы. Значение по умолчанию — 2.|  
|`MaxPendingConnections`|Максимальное число подключений, принятия которых приложением может ожидать прослушиватель. После превышения значения этой квоты новые входящие подключения сбрасываются, а не ожидают принятия. Функции подключения (такие как безопасность сообщения) могут вынудить клиента открыть несколько подключений. При установке значения квоты администраторы службы должны учитывать возможность установления дополнительных подключений. Значение по умолчанию — 10.|  
|`receiveTimeout`|Значение `TimeSpan`, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений. Значение по умолчанию - 00:00:10.|  
|`teredoEnabled`|Логическое значение, которое указывает, использует ли служба общего доступа к портам службу Microsoft Teredo для прослушивания TCP портов от имени службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<allowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Коллекция элементов конфигурации, которые содержат атрибут `securityIdentifier`, указывающий учетные записи пользователей для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения на совместное использование порта см. в разделе [общего доступа к портам Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded). Настройка службы совместного использования портов см [Настройка доступа к портам NET.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Совместное использование портов Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Настройка службы совместного использования портов Net.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
