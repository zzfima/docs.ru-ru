---
title: Использование контрактов в рабочих процессах
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: 9f967d75a8e9d24fcfac8b7376a3d4840fba52f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184276"
---
# <a name="using-contracts-in-workflow"></a>Использование контрактов в рабочих процессах
При реализации службы выполняется определение числа контрактов, описывающих службу и данные, которые она отправляет и получает. Данные представлены как контракты данных и контракты на сообщения; как WCF, так и службы рабочего процесса используют определения контрактов данных и контрактов сообщений как часть описаний службы. Служба сама предоставляет метаданные (в форме WSDL) для описания операций службы. В WCF контракты службы и операций определяют службу и операции, которые она поддерживает. Однако в службе Workflow Service эти контракты являются частью самого бизнес-процесса, они представляются в метаданных процессом, называемым выводом контракта.  
  
## <a name="contract-inference"></a>Вывод контракта  
 При размещении службы рабочего процесса с использованием <xref:System.ServiceModel.Activities.WorkflowServiceHost> просматривается определение рабочего процесса и формируется контракт на основе набора действий по отправке и получению сообщений, обнаруженных в рабочем процессе. В частности, для создания контракта используются следующие действия и свойства:  
  
 <xref:System.ServiceModel.Activities.Receive> Действие  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>

 <xref:System.ServiceModel.Activities.SendReply> Действие  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> Действие  
  
 Конечным результатом вывода контракта является описание службы, использующее структуры данных, аналогичные структурам данных служб WCF и контрактов операций. Затем эти сведения используются для предоставления WSDL для службы рабочего процесса.  
  
## <a name="see-also"></a>См. также раздел

- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Действия обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
- [Как создать службу рабочего процесса с помощью действий обмена сообщениями](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [Как создать службу рабочего процесса, которая использует существующий контракт службы](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
