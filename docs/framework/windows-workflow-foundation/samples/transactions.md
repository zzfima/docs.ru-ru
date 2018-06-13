---
title: Transactions2
ms.date: 03/30/2017
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
ms.openlocfilehash: 361022851d971c0b9350899e1fee6a27c557d666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514599"
---
# <a name="transactions"></a><span data-ttu-id="84387-102">Транзакции</span><span class="sxs-lookup"><span data-stu-id="84387-102">Transactions</span></span>
<span data-ttu-id="84387-103">Этот раздел содержит образцы, демонстрирующие транзакции рабочих процессов в Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="84387-103">This section contains samples that demonstrate workflow transactions in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84387-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="84387-104">In This Section</span></span>  
 [<span data-ttu-id="84387-105">Простой класс TransactionScope</span><span class="sxs-lookup"><span data-stu-id="84387-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="84387-106">Этот раздел состоит из четырех сценариев, показывающих, как вкладывать экземпляры <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="84387-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="84387-107">Использование TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="84387-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="84387-108">Показывается передача транзакции от клиента к серверу с использованием <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции у клиента и <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения сообщения с передаваемой транзакцией и определения времени ее существования на сервере.</span><span class="sxs-lookup"><span data-stu-id="84387-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="84387-109">Вложенные объекты TransactionScope в службе</span><span class="sxs-lookup"><span data-stu-id="84387-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="84387-110">Представлено два сценария, показывающих, как обрабатывать экземпляры действий <xref:System.Activities.Statements.TransactionScope> в службе.</span><span class="sxs-lookup"><span data-stu-id="84387-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
