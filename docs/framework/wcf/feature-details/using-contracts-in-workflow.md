---
title: "Использование контрактов в рабочих процессах"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c13da32e304e54d1826c6dd4ad83d5fbb17702a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-contracts-in-workflow"></a>Использование контрактов в рабочих процессах
При реализации службы выполняется определение числа контрактов, описывающих службу и данные, которые она отправляет и получает. Данные представлены в виде контрактов данных и сообщений; службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службы рабочих процессов используют контракты данных и определения контрактов сообщений как часть описаний служб. Служба сама предоставляет метаданные (в форме WSDL) для описания операций службы. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] контракты службы и операций определяют службу и операции, которые они поддерживают. Однако в службе Workflow Service эти контракты являются частью самого бизнес-процесса, они представляются в метаданных процессом, называемым выводом контракта.  
  
## <a name="contract-inference"></a>Вывод контракта  
 При размещении службы рабочего процесса с использованием <xref:System.ServiceModel.Activities.WorkflowServiceHost> просматривается определение рабочего процесса и формируется контракт на основе набора действий по отправке и получению сообщений, обнаруженных в рабочем процессе. В частности, для создания контракта используются следующие действия и свойства:  
  
 Действие <xref:System.ServiceModel.Activities.Receive>  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 Действие <xref:System.ServiceModel.Activities.SendReply>  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
 Конечным результатом вывода контракта является описание службы, использующее структуры данных, аналогичные структурам данных служб WCF и контрактов операций. Затем эти сведения используются для предоставления WSDL для службы рабочего процесса.  
  
## <a name="see-also"></a>См. также  
 [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Действия обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [Как: создание службы рабочего процесса с действиями обмена сообщениями](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
