---
title: Настройка сериализации в службе рабочего процесса
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: f894f2e044e35bb278f975ef2385a6b22a8bea49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185334"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Настройка сериализации в службе рабочего процесса
Службы рабочего процесса — это службы Windows Communication Foundation <xref:System.Runtime.Serialization.DataContractSerializer> (WCF), и <xref:System.Xml.Serialization.XmlSerializer>поэтому они имеют возможность использовать либо (по умолчанию) или . При написании кода служб, отличных от служб рабочих процессов, тип используемого сериализатора задается применительно к контракту службы или операции. При создании служб рабочего процесса WCF эти контракты не указываются в коде, а генерируются во время выполнения по выводу контракта. Для получения дополнительной информации о выводе контракта [см.](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  Сериализатор определяется с помощью свойства <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>. Оно задается в конструкторе, как показано на следующем рисунке.  
  
 ![Настройка свойства SerializerOption в окне свойств.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 Сериализатор можно также задать в коде, как показано в следующем примере.  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  Для служб рабочего процесса можно также указать известные типы. Для получения дополнительной информации [Data Contract Known Types](data-contract-known-types.md)об известных типах см. Известные типы можно указать в конструкторе или в коде. Чтобы указать известные типы в проекте, нажмите кнопку ellipsis <xref:System.ServiceModel.Activities.Receive> рядом с свойством KnownTypes в **окне свойств** для действия, указанного на следующей иллюстрации.
  
 ![Скриншот диалогового окна свойств KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 При этом отображается редактор коллекций типов, который позволяет искать и указывать известные типы.  
  
 ![Скриншот редактора коллекций типа.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Нажмите на ссылку **Добавления нового типа** и используйте падение вниз, чтобы выбрать или найти тип для добавления в коллекцию известных типов. Для указания известных типов в коде используется свойство <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, как показано в следующем примере:  
  
```csharp
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
