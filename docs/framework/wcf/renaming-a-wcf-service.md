---
title: Переименование службы WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8cb86621972423f55bfa18c60c1d4eb60cacb205
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651049"
---
# <a name="renaming-a-wcf-service"></a>Переименование службы WCF
В этом разделе описывается, как переименовать службу Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Переименование службы WCF  
 Выполните следующие действия для переименования службы в шаблоне службы Windows Communication Foundation (WCF)  
  
- Измените имя класса, реализующего службу.  
  
- В файле конфигурации службы измените имя службы на новое выбранное имя, как показано в следующем примере. В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Если служба размещена на веб-сайте, то она использует файл *.svc. Откройте SVC-файл и измените имя службы, как показано в следующем примере. Этот шаг необязателен для резидентных приложений, так как у них нет SVC-файла.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Переименование контракта службы WCF  
  
- Выполните следующие действия для переименования контракта службы.  
  
- Измените имя контракта службы.  
  
- В файле конфигурации службы измените имя контракта службы на новое выбранное имя, как показано в следующем примере. В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
