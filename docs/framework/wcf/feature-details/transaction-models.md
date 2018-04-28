---
title: Модели транзакций
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab3baf8cc0bb6af951f6f3e6396b7545d0c6b301
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="transaction-models"></a><span data-ttu-id="6fd83-102">Модели транзакций</span><span class="sxs-lookup"><span data-stu-id="6fd83-102">Transaction Models</span></span>
<span data-ttu-id="6fd83-103">В этом разделе описывается связь между моделями программирования транзакций и компонентами инфраструктуры, предоставляемыми корпорацией Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fd83-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="6fd83-104">При использовании транзакций в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] важно понимать, что выбор производится не между различными транзакционными моделями, а между различными уровнями интегрированной и согласованной модели.</span><span class="sxs-lookup"><span data-stu-id="6fd83-104">When using transactions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="6fd83-105">В следующих подразделах рассматриваются три основных компонента транзакции.</span><span class="sxs-lookup"><span data-stu-id="6fd83-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="6fd83-106">Транзакции Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="6fd83-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="6fd83-107">Поддержка транзакций в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет создавать транзакционные службы.</span><span class="sxs-lookup"><span data-stu-id="6fd83-107">The transaction support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you write transactional services.</span></span> <span data-ttu-id="6fd83-108">Кроме того, благодаря поддержке протокола WS-AtomicTransaction (WS-AT) приложения могут направлять транзакции веб-службам, созданным как с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], так и с помощью технологий независимых разработчиков.</span><span class="sxs-lookup"><span data-stu-id="6fd83-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or third-party technology.</span></span>  
  
 <span data-ttu-id="6fd83-109">В службе или приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] функции транзакций [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляют атрибуты и конфигурацию для декларативного задания способа и момента создания, передачи и синхронизации транзакций на уровне инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="6fd83-109">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="6fd83-110">Транзакции System.Transactions</span><span class="sxs-lookup"><span data-stu-id="6fd83-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="6fd83-111">Пространство имен <xref:System.Transactions> предоставляет как модель явного программирования, основанную на классе <xref:System.Transactions.Transaction>, так и модель неявного программирования, использующая класс <xref:System.Transactions.TransactionScope>, в котором транзакции автоматически управляются инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="6fd83-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="6fd83-112"> как создавать приложения с поддержкой транзакций с помощью этих двух моделях см. в разделе [Создание транзакционного приложения](http://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="6fd83-112"> how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="6fd83-113">В службе или приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] пространство имен <xref:System.Transactions> предоставляет модель программирования для создания транзакций в клиентском приложении и для явного взаимодействия с транзакциями, когда это необходимо, в пределах службы.</span><span class="sxs-lookup"><span data-stu-id="6fd83-113">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="6fd83-114">Транзакции MSDTC</span><span class="sxs-lookup"><span data-stu-id="6fd83-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="6fd83-115">Координатор распределенных транзакций (Майкрософт) (MSDTC) представляет собой диспетчер транзакций, обеспечивающий поддержку распределенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="6fd83-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="6fd83-116">Дополнительные сведения см. в разделе [Справочник по программированию DTC](http://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="6fd83-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="6fd83-117">В службе или приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSDTC обеспечивает инфраструктуру для координации транзакций, созданных в клиенте или службе.</span><span class="sxs-lookup"><span data-stu-id="6fd83-117">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
