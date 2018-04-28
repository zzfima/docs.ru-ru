---
title: Базовый жизненный цикл программирования
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
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff735a8caf1fbaff636f94eee366b20c33d8f331
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="b2b0f-102">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="b2b0f-102">Basic Programming Lifecycle</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="b2b0f-103"> позволяет приложениям обмениваться информацией не только в пределах одного компьютера, но и через Интернет, даже если они выполняются на различных платформах.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-103"> enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="b2b0f-104">В этом разделе приводятся задачи, которые необходимо выполнить при создании приложения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b0f-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="b2b0f-105">Рабочий пример приложения см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="b2b0f-106">Основные задачи</span><span class="sxs-lookup"><span data-stu-id="b2b0f-106">The Basic Tasks</span></span>  
 <span data-ttu-id="b2b0f-107">Необходимо выполнить следующие основные задачи в указанном порядке:</span><span class="sxs-lookup"><span data-stu-id="b2b0f-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="b2b0f-108">Определите контракт службы.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-108">Define the service contract.</span></span> <span data-ttu-id="b2b0f-109">В контракте службы указывается ее сигнатура, отправляемые и получаемые ей данные и прочие данные, требуемые контрактом.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="b2b0f-110">Дополнительные сведения см. в разделе [проектирование контрактов службы](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-110">For more information, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="b2b0f-111">Реализуйте контракт.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-111">Implement the contract.</span></span> <span data-ttu-id="b2b0f-112">Для реализации контракта службы создайте класс, который реализует этот контракт, и укажите пользовательские режимы работы, которые должна иметь среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="b2b0f-113">Дополнительные сведения см. в разделе [реализация контрактов службы](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-113">For more information, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="b2b0f-114">Настройте службу, указав конечные точки и определив прочие сведения о режимах работы.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="b2b0f-115">Дополнительные сведения см. в разделе [Настройка службы](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-115">For more information, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="b2b0f-116">Разместите службу.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-116">Host the service.</span></span> <span data-ttu-id="b2b0f-117">Дополнительные сведения см. в разделе [размещение служб](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-117">For more information, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="b2b0f-118">Создайте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-118">Build a client application.</span></span> <span data-ttu-id="b2b0f-119">Дополнительные сведения см. в разделе [Создание клиентов](../../../docs/framework/wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-119">For more information, see [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="b2b0f-120">Несмотря на то что подразделы этого раздела приведены именно в таком порядке, некоторые сценарии не начинаются с самого начала.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="b2b0f-121">Например, если требуется создать клиент для существующей службы, следует начать с шага 5.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="b2b0f-122">При создании службы, которая будет использоваться другими службами, можно пропустить шаг 5.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="b2b0f-123">После ознакомления с Разработка контрактов службы, также может считывать [введение в расширяемость](../../../docs/framework/wcf/introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="b2b0f-124">Если возникают проблемы со службой, проверьте [примеры устранения неполадок WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) для просмотра, имеют ли другие такие же или аналогичные проблемы.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b0f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b2b0f-125">See Also</span></span>  
 [<span data-ttu-id="b2b0f-126">Реализация контрактов служб</span><span class="sxs-lookup"><span data-stu-id="b2b0f-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
