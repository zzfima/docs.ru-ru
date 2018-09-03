---
title: Модели транзакций
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474230"
---
# <a name="transaction-models"></a><span data-ttu-id="bb522-102">Модели транзакций</span><span class="sxs-lookup"><span data-stu-id="bb522-102">Transaction Models</span></span>
<span data-ttu-id="bb522-103">В этом разделе описывается связь между моделями программирования транзакций и компонентами инфраструктуры, предоставляемыми корпорацией Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb522-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="bb522-104">При использовании транзакций в Windows Communication Foundation (WCF), важно понять, что вы Если не выбрать между различными транзакционными моделями, а между различными уровнями интегрированной и согласованной модели.</span><span class="sxs-lookup"><span data-stu-id="bb522-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="bb522-105">В следующих подразделах рассматриваются три основных компонента транзакции.</span><span class="sxs-lookup"><span data-stu-id="bb522-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="bb522-106">Транзакции Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="bb522-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="bb522-107">Поддержка транзакций в WCF позволяет создавать транзакционные службы.</span><span class="sxs-lookup"><span data-stu-id="bb522-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="bb522-108">Кроме того благодаря поддержке протокола WS-AtomicTransaction (WS-AT), приложения могут направлять транзакции веб-служб, построенных с помощью WCF или сторонней технологии.</span><span class="sxs-lookup"><span data-stu-id="bb522-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="bb522-109">В WCF-службы или приложения возможности транзакций WCF предоставляют атрибуты и конфигурацию для декларативного задания, как и когда следует создать инфраструктуры, поток и синхронизации транзакций.</span><span class="sxs-lookup"><span data-stu-id="bb522-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="bb522-110">Транзакции System.Transactions</span><span class="sxs-lookup"><span data-stu-id="bb522-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="bb522-111">Пространство имен <xref:System.Transactions> предоставляет как модель явного программирования, основанную на классе <xref:System.Transactions.Transaction>, так и модель неявного программирования, использующая класс <xref:System.Transactions.TransactionScope>, в котором транзакции автоматически управляются инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="bb522-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="bb522-112">Дополнительные сведения о создании транзакционного приложения с помощью этих двух моделей см. в разделе [Создание транзакционного приложения](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="bb522-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="bb522-113">В WCF-службы или приложения <xref:System.Transactions> предоставляет модель программирования для создания транзакций в клиентском приложении, а также для явного взаимодействия с транзакциями, при необходимости, в службе.</span><span class="sxs-lookup"><span data-stu-id="bb522-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="bb522-114">Транзакции MSDTC</span><span class="sxs-lookup"><span data-stu-id="bb522-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="bb522-115">Координатор распределенных транзакций (Майкрософт) (MSDTC) представляет собой диспетчер транзакций, обеспечивающий поддержку распределенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="bb522-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="bb522-116">Дополнительные сведения см. в разделе [Справочник программиста DTC](https://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="bb522-116">For more information, see the [DTC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="bb522-117">В WCF-службы или приложения MSDTC обеспечивает инфраструктуру для координации транзакций, созданных в рамках клиента или службы.</span><span class="sxs-lookup"><span data-stu-id="bb522-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
