---
title: Настройка сериализации в службе рабочего процесса
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 0e0f03a30aa8e8679cf849aa75948e0bc2314fe5
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57843940"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="8f1a2-102">Настройка сериализации в службе рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8f1a2-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="8f1a2-103">Службы рабочего процесса — это службы Windows Communication Foundation (WCF), поэтому возможность использовать либо <xref:System.Runtime.Serialization.DataContractSerializer> (по умолчанию) или <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="8f1a2-104">При написании кода служб, отличных от служб рабочих процессов, тип используемого сериализатора задается применительно к контракту службы или операции.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="8f1a2-105">При создании служб рабочих процессов WCF не указать эти контракты в коде, но вместо этого они формируются во время выполнения выводом контракта.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="8f1a2-106">Дополнительные сведения об определении контракта см. в разделе [использование контрактов в рабочем процессе](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8f1a2-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="8f1a2-107">Сериализатор определяется с помощью свойства <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="8f1a2-108">Оно задается в конструкторе, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Задание свойства SerializerOption в окне «Свойства».](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="8f1a2-110">Сериализатор можно также задать в коде, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="8f1a2-111">Для служб рабочего процесса можно также указать известные типы.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="8f1a2-112">Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="8f1a2-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="8f1a2-113">Известные типы можно указать в конструкторе или в коде.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="8f1a2-114">Для указания известных типов в конструкторе, нажмите кнопку с многоточием рядом со свойством KnownTypes в **окно "Свойства"** для <xref:System.ServiceModel.Activities.Receive> действия, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>   
  
 ![Снимок экрана: диалоговое окно свойств KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="8f1a2-116">Откроется редактор коллекции типов, которая позволяет искать и указывать известные типы.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Снимок экрана редактора коллекций типов.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="8f1a2-118">Нажмите кнопку **добавить новый тип** ссылку и воспользуйтесь раскрывающимся списком для выбора или поиска типа, добавляемый в коллекцию известных типов.</span><span class="sxs-lookup"><span data-stu-id="8f1a2-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="8f1a2-119">Для указания известных типов в коде используется свойство <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8f1a2-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
