---
title: Переименование службы WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: a215523b92757e3bde1dae2e50de22169020e870
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="renaming-a-wcf-service"></a>Переименование службы WCF
Описывается, как переименовать службы Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Переименование службы WCF  
 Выполните следующие действия для переименования службы в шаблоне службы Windows Communication Foundation (WCF)  
  
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
