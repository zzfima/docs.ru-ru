---
title: Использование WS-AtomicTransaction
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d437b0bf3b14b60899028e293feecf5b1e36f766
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="f83bf-102">Использование WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="f83bf-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="f83bf-103">WS-AtomicTransaction (WS-AT) - это протокол передачи транзакций с возможностью взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f83bf-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="f83bf-104">Он позволяет передавать распределенные транзакции, используя сообщения веб-служб, и обеспечивать взаимодействие между разнородными инфраструктурами транзакций.</span><span class="sxs-lookup"><span data-stu-id="f83bf-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="f83bf-105">WS-AT использует протокол двухфазной фиксации для передачи атомарного результата между распределенными приложениями, диспетчерами транзакций и диспетчерами ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f83bf-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="f83bf-106">Реализация WS-AT, которую обеспечивает [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], включает службу протокола, встроенную в диспетчер транзакций координатора распределенных транзакций Майкрософт (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="f83bf-106">The WS-AT implementation [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="f83bf-107">С помощью WS-AT приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут передавать транзакции другим приложениям, включая веб-службы с возможностью взаимодействия, созданные с использованием сторонней технологии.</span><span class="sxs-lookup"><span data-stu-id="f83bf-107">Using WS-AT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="f83bf-108">При передаче транзакции между клиентским и серверным приложениями используемый протокол передачи транзакций определяется привязкой, которую сервер представляет на конечной точке, выбранной клиентом.</span><span class="sxs-lookup"><span data-stu-id="f83bf-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="f83bf-109">Некоторые привязки, предоставляемые системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в качестве формата распространения транзакций по умолчанию задают протокол `OleTransactions`, тогда как другие привязки по умолчанию определяют протокол WS-AT.</span><span class="sxs-lookup"><span data-stu-id="f83bf-109">Some [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="f83bf-110">Можно также программно изменить выбор протокола передачи транзакций внутри заданной привязки.</span><span class="sxs-lookup"><span data-stu-id="f83bf-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="f83bf-111">Выбор протокола оказывает влияние на:</span><span class="sxs-lookup"><span data-stu-id="f83bf-111">The choice of protocol influences:</span></span>  
  
-   <span data-ttu-id="f83bf-112">формат заголовков сообщений, используемых для передачи транзакции от клиента к серверу;</span><span class="sxs-lookup"><span data-stu-id="f83bf-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
-   <span data-ttu-id="f83bf-113">сетевой протокол, используемый для выполнения протокола двухфазной фиксации между диспетчером транзакций клиента и транзакцией сервера с целью распознавания результата транзакции.</span><span class="sxs-lookup"><span data-stu-id="f83bf-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="f83bf-114">Если сервер и клиент написаны с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], использовать WS-AT не требуется.</span><span class="sxs-lookup"><span data-stu-id="f83bf-114">If the server and client are written using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you do not need to use WS-AT.</span></span> <span data-ttu-id="f83bf-115">Вместо этого воспользуйтесь параметрами по умолчанию привязки `NetTcpBinding` с включенным атрибутом `TransactionFlow`. При этом будет применяться протокол `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="f83bf-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> <span data-ttu-id="f83bf-116">Дополнительные сведения см. в разделе [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f83bf-116">For more information, see [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="f83bf-117">В противном случае, если транзакции передаются в веб-службы, созданные на основе сторонних технологий, необходимо использовать протокол WS-AT.</span><span class="sxs-lookup"><span data-stu-id="f83bf-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83bf-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f83bf-118">See Also</span></span>  
 [<span data-ttu-id="f83bf-119">Настройка поддержки транзакций WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="f83bf-119">Configuring WS-Atomic Transaction Support</span></span>](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
