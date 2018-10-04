---
title: '&lt;NET.TCP&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: c67aeca183eb476460fa0be2c6dcd9c6077165d8
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48579347"
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
|`teredoEnabled`|Логическое значение, указывающее, использует ли служба совместного использования портов службу Microsoft Teredo для прослушивания TCP-портов от имени служб WCF. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<allowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Коллекция элементов конфигурации, которые содержат `securityIdentifier` атрибут для указания учетных записей пользователей для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о совместное использование порта, см. в разделе [совместного использования портов Net.TCP](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md). Чтобы понять, как настроить службы совместного использования портов, см. в разделе [Настройка службы совместного использования портов Net.TCP](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Совместное использование портов Net.TCP](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [Настройка службы совместного использования портов Net.TCP](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
