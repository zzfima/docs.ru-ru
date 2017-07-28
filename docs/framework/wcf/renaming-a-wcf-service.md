---
title: "Переименование службы WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Переименование службы WCF
В данном разделе описывается, как переименовать службу [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Переименование службы WCF  
 Выполните следующие действия для переименования службы в шаблоне [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
-   Измените имя класса, реализующего службу.  
  
-   В файле конфигурации службы измените имя службы на новое выбранное имя, как показано в следующем примере.В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```  
<system.servicemodel>  
   <services>  
      <service name=”WcfService.NewName”>  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   Если служба размещена на веб\-сайте, то она использует файл \*.svc.Откройте SVC\-файл и измените имя службы, как показано в следующем примере.Этот шаг необязателен для резидентных приложений, так как у них нет SVC\-файла.  
  
```  
<%@ ServiceHost Service=”WcfService.NewName”>  
```  
  
## Переименование контракта службы WCF  
  
-   Выполните следующие действия для переименования контракта службы.  
  
-   Измените имя контракта службы.  
  
-   В файле конфигурации службы измените имя контракта службы на новое выбранное имя, как показано в следующем примере.В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract=”WcfService.NewContractName” />  
      </service>  
   </services>  
</system.servicemodel>  
```