---
title: Базовый жизненный цикл программирования
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: fe578ba3c655c9c9ea8398b9b2e4d4f974153c8e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320818"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="c5590-102">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="c5590-102">Basic Programming Lifecycle</span></span>
<span data-ttu-id="c5590-103">Windows Communication Foundation (WCF) позволяет приложениям взаимодействовать независимо от того, находятся ли они на одном компьютере, через Интернет или на разных платформах приложений.</span><span class="sxs-lookup"><span data-stu-id="c5590-103">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="c5590-104">В этом разделе описаны задачи, необходимые для создания приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="c5590-104">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="c5590-105">Рабочий пример приложения см. в [руководстве по начало работы](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-105">For a working sample application, see [Getting Started Tutorial](getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="c5590-106">Основные задачи</span><span class="sxs-lookup"><span data-stu-id="c5590-106">The Basic Tasks</span></span>  
 <span data-ttu-id="c5590-107">Необходимо выполнить следующие основные задачи в указанном порядке:</span><span class="sxs-lookup"><span data-stu-id="c5590-107">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="c5590-108">Определите контракт службы.</span><span class="sxs-lookup"><span data-stu-id="c5590-108">Define the service contract.</span></span> <span data-ttu-id="c5590-109">В контракте службы указывается ее сигнатура, отправляемые и получаемые ей данные и прочие данные, требуемые контрактом.</span><span class="sxs-lookup"><span data-stu-id="c5590-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="c5590-110">Дополнительные сведения см. в разделе [проектирование контрактов служб](designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-110">For more information, see [Designing Service Contracts](designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="c5590-111">Реализуйте контракт.</span><span class="sxs-lookup"><span data-stu-id="c5590-111">Implement the contract.</span></span> <span data-ttu-id="c5590-112">Для реализации контракта службы создайте класс, который реализует этот контракт, и укажите пользовательские режимы работы, которые должна иметь среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="c5590-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="c5590-113">Дополнительные сведения см. в разделе [реализация контрактов служб](implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-113">For more information, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="c5590-114">Настройте службу, указав конечные точки и определив прочие сведения о режимах работы.</span><span class="sxs-lookup"><span data-stu-id="c5590-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="c5590-115">Дополнительные сведения см. в разделе [Настройка служб](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-115">For more information, see [Configuring Services](configuring-services.md).</span></span>  
  
4. <span data-ttu-id="c5590-116">Разместите службу.</span><span class="sxs-lookup"><span data-stu-id="c5590-116">Host the service.</span></span> <span data-ttu-id="c5590-117">Дополнительные сведения см. в разделе [службы хостинга](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-117">For more information, see [Hosting Services](hosting-services.md).</span></span>  
  
5. <span data-ttu-id="c5590-118">Создайте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="c5590-118">Build a client application.</span></span> <span data-ttu-id="c5590-119">Дополнительные сведения см. в разделе [Создание клиентов](building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-119">For more information, see [Building Clients](building-clients.md).</span></span>  
  
 <span data-ttu-id="c5590-120">Несмотря на то что подразделы этого раздела приведены именно в таком порядке, некоторые сценарии не начинаются с самого начала.</span><span class="sxs-lookup"><span data-stu-id="c5590-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="c5590-121">Например, если требуется создать клиент для существующей службы, следует начать с шага 5.</span><span class="sxs-lookup"><span data-stu-id="c5590-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="c5590-122">При создании службы, которая будет использоваться другими службами, можно пропустить шаг 5.</span><span class="sxs-lookup"><span data-stu-id="c5590-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="c5590-123">После ознакомления с разработкой контрактов служб вы также можете ознакомиться с [введением в расширяемость](introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="c5590-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](introduction-to-extensibility.md).</span></span> <span data-ttu-id="c5590-124">Если у вас возникли проблемы со службой, ознакомьтесь с [кратким руководством по устранению неполадок WCF](wcf-troubleshooting-quickstart.md) , чтобы узнать, не возникли ли другие проблемы.</span><span class="sxs-lookup"><span data-stu-id="c5590-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5590-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c5590-125">See also</span></span>

- [<span data-ttu-id="c5590-126">Реализация контрактов служб</span><span class="sxs-lookup"><span data-stu-id="c5590-126">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
