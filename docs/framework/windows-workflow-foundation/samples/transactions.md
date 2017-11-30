---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c7611ce26c1a3b9150a60ced7b4931cc1282eecd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="transactions"></a><span data-ttu-id="59707-102">Транзакции</span><span class="sxs-lookup"><span data-stu-id="59707-102">Transactions</span></span>
<span data-ttu-id="59707-103">Образцы в этом разделе демонстрируют транзакции рабочих процессов в [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59707-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59707-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="59707-104">In This Section</span></span>  
 [<span data-ttu-id="59707-105">Простой класс TransactionScope</span><span class="sxs-lookup"><span data-stu-id="59707-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="59707-106">Этот раздел состоит из четырех сценариев, показывающих, как вкладывать экземпляры <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="59707-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="59707-107">Использование TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="59707-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="59707-108">Показывается передача транзакции от клиента к серверу с использованием <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции у клиента и <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения сообщения с передаваемой транзакцией и определения времени ее существования на сервере.</span><span class="sxs-lookup"><span data-stu-id="59707-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="59707-109">Вложенные объекты TransactionScope в службе</span><span class="sxs-lookup"><span data-stu-id="59707-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="59707-110">Представлено два сценария, показывающих, как обрабатывать экземпляры действий <xref:System.Activities.Statements.TransactionScope> в службе.</span><span class="sxs-lookup"><span data-stu-id="59707-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
