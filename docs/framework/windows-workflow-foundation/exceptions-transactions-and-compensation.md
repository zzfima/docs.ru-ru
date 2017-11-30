---
title: "Исключения, транзакции и компенсация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be803580a4d8ed195222e5960cfa6e26804d91c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="a4869-102">Исключения, транзакции и компенсация</span><span class="sxs-lookup"><span data-stu-id="a4869-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="a4869-103"> предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="a4869-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="a4869-104">Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.</span><span class="sxs-lookup"><span data-stu-id="a4869-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4869-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="a4869-105">In This Section</span></span>  
 [<span data-ttu-id="a4869-106">Исключения</span><span class="sxs-lookup"><span data-stu-id="a4869-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="a4869-107">Показывается использование действия <xref:System.Activities.Statements.TryCatch> для обработки исключений в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="a4869-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="a4869-108">Транзакции</span><span class="sxs-lookup"><span data-stu-id="a4869-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="a4869-109">Показывается использование действия <xref:System.Activities.Statements.TransactionScope> для использования транзакций в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="a4869-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="a4869-110">Компенсация</span><span class="sxs-lookup"><span data-stu-id="a4869-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="a4869-111">Описывается компенсация в рабочих процессах и показывается использование действий компенсации, например <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> и <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="a4869-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="a4869-112">Отмена</span><span class="sxs-lookup"><span data-stu-id="a4869-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="a4869-113">Описывает, как производить выполнение отмены в рабочих процессах с помощью встроенных и настраиваемых действий.</span><span class="sxs-lookup"><span data-stu-id="a4869-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="a4869-114">Отладка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a4869-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="a4869-115">Содержит описание способов отладки рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="a4869-115">Describes how to debug workflows.</span></span>
