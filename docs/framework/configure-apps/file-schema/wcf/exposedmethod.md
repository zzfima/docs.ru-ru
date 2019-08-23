---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 032139b714aa11079c7ee8610c332e404b3981ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918999"
---
# <a name="exposedmethod"></a>\<exposedMethod >
Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.  
  
 \<системой. > ServiceModel  
\<comContracts >  
\<Комконтракт >  
\<методы >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Експоседмесодс >](exposedmethods.md)|[ Коллекция\<элементов > exposedMethod](exposedmethod.md) .|  
  
## <a name="remarks"></a>Примечания  
 Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.  
  
 Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 При запуске файла ComSvcConfig. exe он создает следующий контракт службы с перечнем упомянутых выше методов как [ \<exposedMethod >](exposedmethod.md) элементов.  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 Во время инициализации службы среда выполнения пытается создать контракт службы, отражая и добавляя только методы, входящие в список [ \<элементов exposedMethod >](exposedmethod.md) . Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts >](comcontracts.md)
- [Интеграция с приложениями COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Практическое руководство. Настройка параметров службы COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
