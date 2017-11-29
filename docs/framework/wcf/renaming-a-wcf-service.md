---
title: "Переименование службы WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee707a898bf915491cc1ca44e0606c261dc87dc6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="renaming-a-wcf-service"></a>Переименование службы WCF
В данном разделе описывается, как переименовать службу [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="renaming-a-wcf-service"></a>Переименование службы WCF  
 Выполните следующие действия для переименования службы в шаблоне [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
-   Измените имя класса, реализующего службу.  
  
-   В файле конфигурации службы измените имя службы на новое выбранное имя, как показано в следующем примере. В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   Если служба размещена на веб-сайте, то она использует файл *.svc. Откройте SVC-файл и измените имя службы, как показано в следующем примере. Этот шаг необязателен для резидентных приложений, так как у них нет SVC-файла.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Переименование контракта службы WCF  
  
-   Выполните следующие действия для переименования контракта службы.  
  
-   Измените имя контракта службы.  
  
-   В файле конфигурации службы измените имя контракта службы на новое выбранное имя, как показано в следующем примере. В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
