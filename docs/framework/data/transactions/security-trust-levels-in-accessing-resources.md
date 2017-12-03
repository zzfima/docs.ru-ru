---
title: "Уровни доверия, используемые при доступе к ресурсам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d6fe8902021d6585434c2dcdfa42784d59818157
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="security-trust-levels-in-accessing-resources"></a><span data-ttu-id="6779a-102">Уровни доверия, используемые при доступе к ресурсам</span><span class="sxs-lookup"><span data-stu-id="6779a-102">Security Trust Levels in Accessing Resources</span></span>
<span data-ttu-id="6779a-103">В этом разделе описывается порядок ограничения доступа к ресурсам различных типов, используемым инфраструктурой <xref:System.Transactions>.</span><span class="sxs-lookup"><span data-stu-id="6779a-103">This topic discusses how access is restricted on the types of resources that <xref:System.Transactions> exposes.</span></span>  
  
 <span data-ttu-id="6779a-104">Предусмотрено три основных уровня доверия для инфраструктуры <xref:System.Transactions>.</span><span class="sxs-lookup"><span data-stu-id="6779a-104">There are three main levels of trust for <xref:System.Transactions>.</span></span> <span data-ttu-id="6779a-105">Уровни доверия определяются на основе типов ресурсов, используемых инфраструктурой <xref:System.Transactions>, и уровня доверия, который требуется для доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="6779a-105">The trust levels are defined based on the types of resources that <xref:System.Transactions> exposes, and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="6779a-106">Ресурсами, к которым инфраструктура <xref:System.Transactions> предоставляет доступ, являются системная память, ресурсы, общие для всего процесса, и ресурсы, общие для всей системы.</span><span class="sxs-lookup"><span data-stu-id="6779a-106">The resources that <xref:System.Transactions> provides access to are system memory, shared process wide resources, and system wide resources.</span></span> <span data-ttu-id="6779a-107">Ниже представлены предусмотренные уровни доверия.</span><span class="sxs-lookup"><span data-stu-id="6779a-107">The levels are:</span></span>  
  
-   <span data-ttu-id="6779a-108">**AllowPartiallyTrustedCallers** (APTCA) для приложений, использующих транзакции в одном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6779a-108">**AllowPartiallyTrustedCallers** (APTCA) for applications using transactions within a single application domain.</span></span>  
  
-   <span data-ttu-id="6779a-109">**Разрешения DistributedTransactionPermission** (DTP) для приложений, использующих распределенные транзакции.</span><span class="sxs-lookup"><span data-stu-id="6779a-109">**DistributedTransactionPermission** (DTP) for applications using distributed transactions.</span></span>  
  
-   <span data-ttu-id="6779a-110">FullTrust - для устойчивых ресурсов, приложений управления конфигурацией и приложений взаимодействия с традиционными системами.</span><span class="sxs-lookup"><span data-stu-id="6779a-110">Full trust for durable resources, configuration management applications, and legacy interop applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6779a-111">Не следует вызывать какие-либо интерфейсы зачисления с олицетворяемыми контекстами.</span><span class="sxs-lookup"><span data-stu-id="6779a-111">You should not call any of the enlistment interfaces with impersonated contexts.</span></span>  
  
## <a name="trust-levels"></a><span data-ttu-id="6779a-112">Уровни доверия</span><span class="sxs-lookup"><span data-stu-id="6779a-112">Trust Levels</span></span>  
  
### <a name="aptca-partial-trust"></a><span data-ttu-id="6779a-113">APTCA (частичное доверие)</span><span class="sxs-lookup"><span data-stu-id="6779a-113">APTCA (Partial Trust)</span></span>  
 <span data-ttu-id="6779a-114"><xref:System.Transactions> Сборки может вызываться частично доверенным кодом, так как он был помечен **AllowPartiallyTrustedCallers** атрибут (APTCA).</span><span class="sxs-lookup"><span data-stu-id="6779a-114">The <xref:System.Transactions> assembly can be called by partially trusted code because it has been marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="6779a-115">Этот атрибут по существу исключает неявный <xref:System.Security.Permissions.SecurityAction.LinkDemand> для **FullTrust** набор разрешений, в противном случае автоматически используется в каждом общедоступном методе каждого типа.</span><span class="sxs-lookup"><span data-stu-id="6779a-115">This attribute essentially removes the implicit <xref:System.Security.Permissions.SecurityAction.LinkDemand> for the **FullTrust** permission set that is otherwise automatically placed on each publicly accessible method in each type.</span></span> <span data-ttu-id="6779a-116">Однако для некоторых типов и элементов по-прежнему требуются разрешения более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="6779a-116">However, some types and members still require stronger permissions.</span></span>  
  
 <span data-ttu-id="6779a-117">Атрибут APTCA позволяет приложениям использовать транзакции с частичным доверием в одном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6779a-117">The APTCA attribute enables applications to use transactions in partial trust within a single application domain.</span></span> <span data-ttu-id="6779a-118">Это обеспечивает использование неповышаемых транзакций и зачислений неустойчивых ресурсов, которые можно применять для обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="6779a-118">This enables non-escalated transactions and volatile enlistments that can be used for error handling.</span></span> <span data-ttu-id="6779a-119">В качестве примера рассмотрим транзакционную хэш-таблицу и используемое ей приложение.</span><span class="sxs-lookup"><span data-stu-id="6779a-119">One example of this is a transacted hash table and an application that uses it.</span></span> <span data-ttu-id="6779a-120">Данные можно добавлять и удалять из хэш-таблицы в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="6779a-120">Data can be added to and removed from the hash table under a single transaction.</span></span> <span data-ttu-id="6779a-121">В случае последующего отката транзакции все произведенные в рамках транзакции изменения хэш-таблицы могут быть отменены.</span><span class="sxs-lookup"><span data-stu-id="6779a-121">If the transaction is later rolled back, all of the changes made to the hash table under that transaction can be undone.</span></span>  
  
### <a name="distributedtransactionpermission-dtp"></a><span data-ttu-id="6779a-122">Разрешение DistributedTransactionPermission (DTP)</span><span class="sxs-lookup"><span data-stu-id="6779a-122">DistributedTransactionPermission (DTP)</span></span>  
 <span data-ttu-id="6779a-123">При передаче управления транзакцией <xref:System.Transactions> координатору MSDTC инфраструктура <xref:System.Transactions> запрашивает разрешение <xref:System.Transactions.DistributedTransactionPermission> (DTP) для создания распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="6779a-123">When a <xref:System.Transactions> transaction is escalated to be managed by MSDTC, <xref:System.Transactions> demands the <xref:System.Transactions.DistributedTransactionPermission> (DTP) to create the distributed transaction.</span></span> <span data-ttu-id="6779a-124">Это означает, что коду, вызывающему передачу транзакции на следующий уровень иерархии (например, посредством сериализации или зачисления дополнительных устойчивых ресурсов), требуется предоставление разрешения DTP.</span><span class="sxs-lookup"><span data-stu-id="6779a-124">This means that the code that causes the transaction to be escalated (such as through serialization or additional durable enlistments) would need to be granted DTP.</span></span> <span data-ttu-id="6779a-125">Коду, который изначально создал транзакцию <xref:System.Transactions>, не обязательно располагать данным разрешением.</span><span class="sxs-lookup"><span data-stu-id="6779a-125">The code that originally created the <xref:System.Transactions> transaction does not necessarily need to possess this permission.</span></span>  
  
### <a name="fulltrust-link-demands"></a><span data-ttu-id="6779a-126">FullTrust (полное доверие)</span><span class="sxs-lookup"><span data-stu-id="6779a-126">FullTrust Link Demands</span></span>  
 <span data-ttu-id="6779a-127">Этот уровень разрешений предназначен для ограничения приложений, записывающих данные в устойчивые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6779a-127">This permission level is intended to restrict applications that are writing to durable resources.</span></span> <span data-ttu-id="6779a-128">В случае сбоя приложение должно быть способно восстановить связь с диспетчером транзакций для определения окончательного результата транзакции, чтобы обновить постоянные данные.</span><span class="sxs-lookup"><span data-stu-id="6779a-128">Upon failure, the application needs to be able to recover with the transaction manager to determine the final outcome of the transaction, so that it can update permanent data.</span></span> <span data-ttu-id="6779a-129">Приложение такого типа называется диспетчером устойчивых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6779a-129">This type of application is known as a durable source manager.</span></span> <span data-ttu-id="6779a-130">Классическим примером такого приложения является SQL.</span><span class="sxs-lookup"><span data-stu-id="6779a-130">A classic example of this type of application is SQL.</span></span>  
  
 <span data-ttu-id="6779a-131">Для выполнения восстановления у этого приложения имеется способность постоянно потреблять системные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6779a-131">To enable recovery, this type of application has the ability to permanently consume system resources.</span></span> <span data-ttu-id="6779a-132">Это необходимо, поскольку диспетчер ресурсов, выполняющий восстановление, должен вспомнить все зафиксированные транзакции, прежде чем он сможет подтвердить, что все участвующие в транзакции диспетчеры устойчивых ресурсов получили результат транзакции.</span><span class="sxs-lookup"><span data-stu-id="6779a-132">This is because the recoverable transaction manager must remember transactions that have committed until it can confirm that all durable resource managers that are participating in the transaction have received the outcome.</span></span> <span data-ttu-id="6779a-133">Поэтому приложению данного типа требуется разрешение FullTrust, и его не следует запускать, если такой уровень доверия не предоставлен.</span><span class="sxs-lookup"><span data-stu-id="6779a-133">Therefore, this type of application requires full trust and should not be run unless that level of trust has been granted.</span></span>  
  
 <span data-ttu-id="6779a-134">Дополнительные сведения о долговременным присоединением к транзакции и восстановления см. в разделе [прикрепление ресурсов в качестве участников в транзакции](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) и [выполнение восстановления](../../../../docs/framework/data/transactions/performing-recovery.md) разделы.</span><span class="sxs-lookup"><span data-stu-id="6779a-134">For more information on durable enlistments and recovery, see the [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) and [Performing Recovery](../../../../docs/framework/data/transactions/performing-recovery.md) topics.</span></span>  
  
 <span data-ttu-id="6779a-135">Приложениям, которые выполняют традиционные операции взаимодействия с COM+, также требуется разрешение FullTrust.</span><span class="sxs-lookup"><span data-stu-id="6779a-135">Applications that perform legacy interop work with COM+ are also required to have full trust.</span></span>  
  
 <span data-ttu-id="6779a-136">Ниже приведен список типов и членов, которые не могут вызываться частично доверенным кодом, поскольку маркируются с **FullTrust** атрибут декларативной безопасности:</span><span class="sxs-lookup"><span data-stu-id="6779a-136">The following is a list of types and members that are not callable by partially trusted code because they are decorated with the **FullTrust** declarative security attribute:</span></span>  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
-   <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
-   <xref:System.Transactions.TransactionInterop>  
  
-   <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
-   <xref:System.Transactions.HostCurrentTransactionCallback>  
  
-   <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
-   <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
-   <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 <span data-ttu-id="6779a-137">Только непосредственный вызывающий объект должен обладать **FullTrust** набор разрешений для использования выше типов или методов.</span><span class="sxs-lookup"><span data-stu-id="6779a-137">Only the immediate caller is required to possess the **FullTrust** permission set to use the above types or methods.</span></span>
