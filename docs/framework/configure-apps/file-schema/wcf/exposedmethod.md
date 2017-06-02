---
title: "&lt;exposedMethod&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;exposedMethod&gt;
Представляет метод COM\+, предоставляемый, когда интерфейс компонента COM\+ предоставляется как веб\-служба.  
  
## Синтаксис  
  
```  
  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Строка, которая содержит метод COM\+, предоставляемый, когда интерфейс компонента COM\+ предоставляется как веб\-служба.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<exposedMethods\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Коллекция элементов [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md).|  
  
## Заметки  
 Средство конфигурации интеграции COM\+ \(ComSvcConfig.exe\) может применяться для добавления определенных методов COM\-интерфейса для использования в созданном контракте службы.  
  
 Например, для добавления в созданный контракт службы трех именованных методов из COM\-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 При запуске средства ComSvcConfig.exe также создается следующий контракт службы, в котором указанные выше методы перечислены в виде элементов [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md).  
  
```  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 Во время инициализации службы среда выполнения пытается создать контракт службы, отображая и добавляя только те методы, которые включены в список элементов [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md).  Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>   
 <xref:System.ServiceModel.Configuration.ComMethodElement>   
 [\<comContracts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)   
 [Интеграция с приложениями COM\+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Практическое руководство. Настройка параметров службы COM\+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)