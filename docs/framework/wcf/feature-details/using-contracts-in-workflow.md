---
title: "Использование контрактов в рабочих процессах | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Использование контрактов в рабочих процессах
При реализации службы выполняется определение числа контрактов, описывающих службу и данные, которые она отправляет и получает.Данные представлены в виде контрактов данных и сообщений; службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службы рабочих процессов используют контракты данных и определения контрактов сообщений как часть описаний служб.Служба сама предоставляет метаданные \(в форме WSDL\) для описания операций службы.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] контракты службы и операций определяют службу и операции, которые они поддерживают.Однако в службе рабочего процесса данные контракты являются частью самого бизнес\-процесса, они представляются в метаданных процессом, называемым выводом контракта.  
  
## Вывод контракта  
 При размещении службы рабочего процесса с использованием <xref:System.ServiceModel.Activities.WorkflowServiceHost> просматривается определение рабочего процесса и формируется контракт на основе набора действий по отправке и получению сообщений, обнаруженных в рабочем процессе.В частности, для создания контракта используются следующие действия и свойства:  
  
 Действие <xref:System.ServiceModel.Activities.Receive>  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.ValueType%2A>  
  
 Действие <xref:System.ServiceModel.Activities.SendReply>  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
-   <xref:System.ServiceModel.Activities.SendReply.ValueType%2A>  
  
 Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
 Конечным результатом вывода контракта является описание службы, использующее структуры данных, аналогичные структурам данных служб WCF и контрактов операций.Затем эти сведения используются для предоставления WSDL для службы рабочего процесса.  
  
## См. также  
 [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Действия обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-activities.md)   
 [Как создать службу рабочего процесса с помощью действий обмена сообщениями](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)   
 [Как создать службу рабочего процесса, которая использует существующий контракт службы](../../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)