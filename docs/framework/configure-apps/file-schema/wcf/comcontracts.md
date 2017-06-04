---
title: "&lt;comContracts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;comContracts&gt;
Раздел конфигурации `comContracts` содержит элементы, которые позволяют задавать различные свойства контракта службы интеграции COM\+.  
  
## Задание пространства имен и контракта  
 Контракты службы интеграции COM\+ в настоящее время ограничены пространством имен http:\/\/tempuri.org, а имя контракта является производным от поддерживающего COM\-интерфейса.  Однако можно указать альтернативы, используя раздел `comContracts` в файле конфигурации.  
  
 Например, для указания пространства имен, имени контракта службы и параметра для принудительного использования сеансовых привязок можно использовать следующую конфигурацию.  
  
```  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.  
  
 Если раздел пуст, при инициализации службы применяется пространство имен по умолчанию и имя контракта, взятое из идентификатора поддерживающего COM\-интерфейса.  
  
 Кроме того, можно использовать элемент [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) для задания методов COM\+, предоставляемых, если интерфейс в компоненте COM\+ предоставляется как веб\-служба.  Элемент [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) можно использовать для задания неизменных типов, используемых в интеграции.  Наконец, можно использовать элемент [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) для включения пользовательских типов \(UDT\), которые должны включаться в контракт службы.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>   
 <xref:System.ServiceModel.Configuration.ComContractElement>   
 [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)   
 [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)   
 [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)   
 [\<comContract\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)   
 [Интеграция с приложениями COM\+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Практическое руководство. Настройка параметров службы COM\+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)