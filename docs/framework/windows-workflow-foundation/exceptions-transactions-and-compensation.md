---
title: Исключения, транзакции и компенсация
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: c4d66e252561ad7b896ff8092e80013c51bd463c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709475"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="6292d-102">Исключения, транзакции и компенсация</span><span class="sxs-lookup"><span data-stu-id="6292d-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="6292d-103">предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="6292d-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="6292d-104">Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.</span><span class="sxs-lookup"><span data-stu-id="6292d-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6292d-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6292d-105">In This Section</span></span>  
 [<span data-ttu-id="6292d-106">Исключения</span><span class="sxs-lookup"><span data-stu-id="6292d-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="6292d-107">Показывается использование действия <xref:System.Activities.Statements.TryCatch> для обработки исключений в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="6292d-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="6292d-108">Транзакции</span><span class="sxs-lookup"><span data-stu-id="6292d-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="6292d-109">Показывается использование действия <xref:System.Activities.Statements.TransactionScope> для использования транзакций в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="6292d-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="6292d-110">Компенсация</span><span class="sxs-lookup"><span data-stu-id="6292d-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="6292d-111">Описывается компенсация в рабочих процессах и показывается использование действий компенсации, например <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> и <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="6292d-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="6292d-112">Отмена</span><span class="sxs-lookup"><span data-stu-id="6292d-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="6292d-113">Описывает, как производить выполнение отмены в рабочих процессах с помощью встроенных и настраиваемых действий.</span><span class="sxs-lookup"><span data-stu-id="6292d-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="6292d-114">Отладка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6292d-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="6292d-115">Содержит описание способов отладки рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6292d-115">Describes how to debug workflows.</span></span>
