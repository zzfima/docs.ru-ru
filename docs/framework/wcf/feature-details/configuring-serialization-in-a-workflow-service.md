---
title: Настройка сериализации в службе рабочего процесса
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47c66077da051fd70300e1961593e906fe8e77aa
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Настройка сериализации в службе рабочего процесса
Службы рабочих процессов являются службами [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и поэтому обладают возможностью использовать <xref:System.Runtime.Serialization.DataContractSerializer> (по умолчанию) или <xref:System.Xml.Serialization.XmlSerializer>. При написании кода служб, отличных от служб рабочих процессов, тип используемого сериализатора задается применительно к контракту службы или операции. При создании служб Workflow Services [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не надо указывать эти контракты в коде, вместо этого они формируются во время выполнения выводом контракта. Дополнительные сведения о вывод контракта см. в разделе [использование контрактов в рабочем процессе](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  Сериализатор определяется с помощью свойства <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>. Оно задается в конструкторе, как показано на следующем рисунке.  
  
 ![Настройка сериализатора](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")  
  
 Сериализатор можно также задать в коде, как показано в следующем примере.  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
 Для служб рабочего процесса можно также указать известные типы. Дополнительные сведения об известных типах см. [известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md). Известные типы можно указать в конструкторе или в коде. Для указания известных типов в конструкторе нажмите кнопку с многоточием рядом со свойством KnownTypes в окне свойств для действия <xref:System.ServiceModel.Activities.Receive>, как показано на следующем рисунке.  
  
 ![Свойство KnownTypes](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")  
  
 При этом отобразится редактор коллекции типов, который позволяет искать и указывать известные типы.  
  
 ![Добавление известных типов](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")  
  
 Нажмите кнопку **добавить новый тип** ссылку и воспользуйтесь раскрывающимся списком для выбора или поиска типа, добавляемый в коллекцию известных типов. Для указания известных типов в коде используется свойство <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, как показано в следующем примере:  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```  
  
 В полном примере кода показан способ настройки сериализации для службы рабочего процесса см. в разделе [форматирование сообщений в службах рабочих процессов](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).
