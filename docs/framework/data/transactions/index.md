---
title: "Обработка транзакций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a6dcd11d34f0b81d6d3982ef1c6ab211d94818b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-processing"></a><span data-ttu-id="f0530-102">Обработка транзакций</span><span class="sxs-lookup"><span data-stu-id="f0530-102">Transaction Processing</span></span>
<span data-ttu-id="f0530-103">При покупке книги в книжном интернет-магазине вы обмениваете деньги (находящиеся на вашей кредитной карте) на книгу.</span><span class="sxs-lookup"><span data-stu-id="f0530-103">When you purchase a book from an online bookstore, you exchange money (in the form of credit) for a book.</span></span> <span data-ttu-id="f0530-104">Если на вашей кредитной карте достаточно средств, выполняется последовательность операций, гарантирующая, что вы получите книгу, а книжный магазин - ваши деньги.</span><span class="sxs-lookup"><span data-stu-id="f0530-104">If your credit is good, a series of related operations ensures that you get the book and the bookstore gets your money.</span></span> <span data-ttu-id="f0530-105">Однако если не удается выполнить хотя бы одну операцию в этой последовательности, вся процедура обмена заканчивается неудачей.</span><span class="sxs-lookup"><span data-stu-id="f0530-105">However, if a single operation in the series fails during the exchange, the entire exchange fails.</span></span> <span data-ttu-id="f0530-106">Вы не получаете книгу, а книжный магазин не получает ваши деньги.</span><span class="sxs-lookup"><span data-stu-id="f0530-106">You do not get the book and the bookstore does not get your money.</span></span>  
  
 <span data-ttu-id="f0530-107">Технология, отвечающая за обеспечение сбалансированного и предсказуемого обмена, называется обработкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="f0530-107">The technology responsible for making the exchange balanced and predictable is called transaction processing.</span></span> <span data-ttu-id="f0530-108">Транзакции гарантируют, что изменения информационно-ориентированных ресурсов фиксируются только после успешного выполнения всех операций в блоке транзакции.</span><span class="sxs-lookup"><span data-stu-id="f0530-108">Transactions ensure that data-oriented resources are not permanently updated unless all operations within the transactional unit complete successfully.</span></span> <span data-ttu-id="f0530-109">Объединение нескольких связанных операций в один блок, который либо полностью выполняется, либо полностью не выполняется, позволяет упростить процесс восстановления после ошибок и повысить надежность вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="f0530-109">By combining a set of related operations into a unit that either completely succeeds or completely fails, you can simplify error recovery and make your application more reliable.</span></span>  
  
 <span data-ttu-id="f0530-110">Системы обработки транзакций состоят из компьютерного оборудования и программного обеспечения, в котором работает транзакционное приложение, выполняющее повседневные транзакции, необходимые для ведения бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f0530-110">Transaction processing systems consist of computer hardware and software hosting a transaction-oriented application that performs the routine transactions necessary to conduct business.</span></span> <span data-ttu-id="f0530-111">Примерами таких систем являются системы обработки заказов на закупку, бронирования авиабилетов, обработки платежных ведомостей, обработки записей сотрудников, управления производством и доставки.</span><span class="sxs-lookup"><span data-stu-id="f0530-111">Examples include systems that manage sales order entry, airline reservations, payroll, employee records, manufacturing, and shipping.</span></span>  
  
 <span data-ttu-id="f0530-112">В данном разделе представлены как общие сведения об обработке транзакций, так и конкретная информация о создании транзакционных приложений и диспетчеров ресурсов с помощью платформы Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0530-112">This section provides both general information on transaction processing, and specific information on how to write transactional applications and resource managers using the Microsoft .NET Framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0530-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="f0530-113">In This Section</span></span>  
 [<span data-ttu-id="f0530-114">Основные сведения о транзакциях</span><span class="sxs-lookup"><span data-stu-id="f0530-114">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 <span data-ttu-id="f0530-115">Описывает базовые термины и понятия технологии обработки транзакций.</span><span class="sxs-lookup"><span data-stu-id="f0530-115">Introduces basic transaction processing terms and concepts.</span></span>  
  
 [<span data-ttu-id="f0530-116">Функциональные возможности, предоставляемые пространством имен System.Transactions</span><span class="sxs-lookup"><span data-stu-id="f0530-116">Features Provided by System.Transactions</span></span>](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)  
 <span data-ttu-id="f0530-117">Описывает, как можно использовать функциональные возможности пространства имен System.Transactions для создания собственного транзакционного приложения.</span><span class="sxs-lookup"><span data-stu-id="f0530-117">Discusses how you can use features in System.Transactions to write your own transactional application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f0530-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f0530-118">Reference</span></span>  
 <xref:System.Transactions>  
 <span data-ttu-id="f0530-119">Предоставляет классы, позволяющие коду участвовать в транзакциях.</span><span class="sxs-lookup"><span data-stu-id="f0530-119">Provides classes that allow your code to participate in transactions.</span></span> <span data-ttu-id="f0530-120">Эти классы поддерживают транзакции с несколькими распределенными участниками, многофазные уведомления и зачисление устойчивых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f0530-120">The classes support transactions with multiple distributed participants, multiple phase notifications, and durable enlistments.</span></span>
