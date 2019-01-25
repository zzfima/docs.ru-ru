---
title: '&lt;exposedMethod&gt;'
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 0bfb56395217283eeba69c2f3b7569a89f576423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702045"
---
# <a name="ltexposedmethodgt"></a>&lt;exposedMethod&gt;
Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.  
  
 \<system.ServiceModel>  
\<comContracts >  
\<comContract >  
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
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<exposedMethods >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Коллекция [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.|  
  
## <a name="remarks"></a>Примечания  
 Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.  
  
 Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 При запуске ComSvcConfig.exe также создается следующий контракт службы, в котором указанные выше методы как [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 Во время инициализации службы среда выполнения пытается создать контракт службы, отображая и добавляя только те методы, которые включены в список [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов. Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Интеграция с приложениями COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Практическое руководство. Настройка параметров службы COM +](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
