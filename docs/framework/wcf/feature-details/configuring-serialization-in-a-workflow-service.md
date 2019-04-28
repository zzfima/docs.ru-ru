---
title: Настройка сериализации в службе рабочего процесса
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 0e0f03a30aa8e8679cf849aa75948e0bc2314fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857509"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Настройка сериализации в службе рабочего процесса
Службы рабочего процесса — это службы Windows Communication Foundation (WCF), поэтому возможность использовать либо <xref:System.Runtime.Serialization.DataContractSerializer> (по умолчанию) или <xref:System.Xml.Serialization.XmlSerializer>. При написании кода служб, отличных от служб рабочих процессов, тип используемого сериализатора задается применительно к контракту службы или операции. При создании служб рабочих процессов WCF не указать эти контракты в коде, но вместо этого они формируются во время выполнения выводом контракта. Дополнительные сведения об определении контракта см. в разделе [использование контрактов в рабочем процессе](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  Сериализатор определяется с помощью свойства <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>. Оно задается в конструкторе, как показано на следующем рисунке.  
  
 ![Задание свойства SerializerOption в окне «Свойства».](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
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
  
  Для служб рабочего процесса можно также указать известные типы. Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](data-contract-known-types.md). Известные типы можно указать в конструкторе или в коде. Для указания известных типов в конструкторе, нажмите кнопку с многоточием рядом со свойством KnownTypes в **окно "Свойства"** для <xref:System.ServiceModel.Activities.Receive> действия, как показано на следующем рисунке.   
  
 ![Снимок экрана: диалоговое окно свойств KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Откроется редактор коллекции типов, которая позволяет искать и указывать известные типы.  
  
 ![Снимок экрана редактора коллекций типов.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Нажмите кнопку **добавить новый тип** ссылку и воспользуйтесь раскрывающимся списком для выбора или поиска типа, добавляемый в коллекцию известных типов. Для указания известных типов в коде используется свойство <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, как показано в следующем примере:  
  
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
