---
title: "Базовый жизненный цикл программирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f5c45cad0b1e4ae1aa6b1963e9acdab47cd9203
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="2fc49-102">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="2fc49-102">Basic Programming Lifecycle</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="2fc49-103"> позволяет приложениям обмениваться информацией не только в пределах одного компьютера, но и через Интернет, даже если они выполняются на различных платформах.</span><span class="sxs-lookup"><span data-stu-id="2fc49-103"> enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="2fc49-104">В этом разделе приводятся задачи, которые необходимо выполнить при создании приложения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fc49-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="2fc49-105">Рабочий пример приложения см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="2fc49-106">Основные задачи</span><span class="sxs-lookup"><span data-stu-id="2fc49-106">The Basic Tasks</span></span>  
 <span data-ttu-id="2fc49-107">Необходимо выполнить следующие основные задачи в указанном порядке:</span><span class="sxs-lookup"><span data-stu-id="2fc49-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="2fc49-108">Определите контракт службы.</span><span class="sxs-lookup"><span data-stu-id="2fc49-108">Define the service contract.</span></span> <span data-ttu-id="2fc49-109">В контракте службы указывается ее сигнатура, отправляемые и получаемые ей данные и прочие данные, требуемые контрактом.</span><span class="sxs-lookup"><span data-stu-id="2fc49-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="2fc49-110">[Проектирование контрактов службы](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-110"> [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="2fc49-111">Реализуйте контракт.</span><span class="sxs-lookup"><span data-stu-id="2fc49-111">Implement the contract.</span></span> <span data-ttu-id="2fc49-112">Для реализации контракта службы создайте класс, который реализует этот контракт, и укажите пользовательские режимы работы, которые должна иметь среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="2fc49-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="2fc49-113">[Реализация контрактов службы](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-113"> [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="2fc49-114">Настройте службу, указав конечные точки и определив прочие сведения о режимах работы.</span><span class="sxs-lookup"><span data-stu-id="2fc49-114">Configure the service by specifying endpoints and other behavior information.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="2fc49-115">[Настройка служб](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-115"> [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="2fc49-116">Разместите службу.</span><span class="sxs-lookup"><span data-stu-id="2fc49-116">Host the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="2fc49-117">[Услуг](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-117"> [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="2fc49-118">Создайте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="2fc49-118">Build a client application.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="2fc49-119">[Создание клиентов](../../../docs/framework/wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-119"> [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="2fc49-120">Несмотря на то что подразделы этого раздела приведены именно в таком порядке, некоторые сценарии не начинаются с самого начала.</span><span class="sxs-lookup"><span data-stu-id="2fc49-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="2fc49-121">Например, если требуется создать клиент для существующей службы, следует начать с шага 5.</span><span class="sxs-lookup"><span data-stu-id="2fc49-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="2fc49-122">При создании службы, которая будет использоваться другими службами, можно пропустить шаг 5.</span><span class="sxs-lookup"><span data-stu-id="2fc49-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="2fc49-123">После ознакомления с Разработка контрактов службы, также может считывать [введение в расширяемость](../../../docs/framework/wcf/introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="2fc49-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="2fc49-124">Если возникают проблемы со службой, проверьте [примеры устранения неполадок WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) для просмотра, имеют ли другие такие же или аналогичные проблемы.</span><span class="sxs-lookup"><span data-stu-id="2fc49-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc49-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2fc49-125">See Also</span></span>  
 [<span data-ttu-id="2fc49-126">Реализация контрактов служб</span><span class="sxs-lookup"><span data-stu-id="2fc49-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
