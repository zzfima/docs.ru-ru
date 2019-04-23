---
title: Учебник. Начало работы с приложениями Windows Communication Foundation
description: Эти учебники предоставляет вводные сведения по созданию приложений WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: d4613edefeb8db2c0d1e11e925f8ac41329efb0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137934"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="d592b-103">Учебник. Начало работы с приложениями Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d592b-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="d592b-104">Следующие учебники представлена в Windows Communication Foundation (WCF) опыт программирования.</span><span class="sxs-lookup"><span data-stu-id="d592b-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="d592b-105">Работе с этими руководствами, в порядке обеспечит начальное понимание шагов, необходимых для создания приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="d592b-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="d592b-106">После завершения, вы получите работающей службы WCF и клиент WCF, который вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="d592b-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span> 

<span data-ttu-id="d592b-107">В учебнике предполагается, что вы используете Visual Studio в качестве среды разработки.</span><span class="sxs-lookup"><span data-stu-id="d592b-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="d592b-108">Если используется другая среда разработки, игнорировать инструкции конкретных Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d592b-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span> 

<span data-ttu-id="d592b-109">Образцы приложений WCF, которые можно загрузить и запустить, см. в разделе [образцов Windows Communication Foundation](samples/index.md).</span><span class="sxs-lookup"><span data-stu-id="d592b-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="d592b-110">Общие сведения о примерах, см. в разделе [Приступая к работе образца](samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d592b-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="d592b-111">Дополнительные сведения о создании служб и клиентов см. в разделе [базовое Программирование WCF](basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="d592b-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="d592b-112">Учебники по WCF</span><span class="sxs-lookup"><span data-stu-id="d592b-112">WCF tutorials</span></span>

<span data-ttu-id="d592b-113">Первые три руководства описывают, как определить контракт службы WCF, как реализовать его и как разместить его.</span><span class="sxs-lookup"><span data-stu-id="d592b-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="d592b-114">Создаваемая служба является резидентной в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="d592b-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="d592b-115">Вы также можете разместить службы в группе Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d592b-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="d592b-116">Дополнительные сведения см. в разделе [Как Размещение службы WCF в IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="d592b-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="d592b-117">Несмотря на то, что для настройки службы в этом руководстве используется код, вы также можете [настраивать службы в файле конфигурации](configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="d592b-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span> 

- [<span data-ttu-id="d592b-118">Учебник. Определите контракт службы</span><span class="sxs-lookup"><span data-stu-id="d592b-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="d592b-119">Создание контракта WCF с интерфейсом, определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="d592b-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="d592b-120">Этот контракт определяет функциональность, предоставленную службой.</span><span class="sxs-lookup"><span data-stu-id="d592b-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="d592b-121">Учебник. Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="d592b-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="d592b-122">После определения контракта, должен быть реализован классом службы.</span><span class="sxs-lookup"><span data-stu-id="d592b-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="d592b-123">Учебник. Размещение и запуск базовой службы</span><span class="sxs-lookup"><span data-stu-id="d592b-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="d592b-124">Настройте конечную точку для службы и разместите службу в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="d592b-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="d592b-125">Для службы станет активным необходимо настроить его и разместить ее внутри среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d592b-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="d592b-126">Эта среда выполнения создает службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="d592b-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="d592b-127">Следующие два руководства описывается, как создавать, настраивать, а предоставляет используйте клиентское приложение для вызова операций службы.</span><span class="sxs-lookup"><span data-stu-id="d592b-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="d592b-128">Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="d592b-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="d592b-129">Visual Studio автоматизирует процесс доступа к этим метаданным и использует его для создания клиентского приложения для службы.</span><span class="sxs-lookup"><span data-stu-id="d592b-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="d592b-130">Если вы решили не использовать Visual Studio, можно использовать [средство ServiceModel Metadata Utility (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="d592b-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="d592b-131">Учебник. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="d592b-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="d592b-132">Получение метаданных для создания прокси клиента WCF из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d592b-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="d592b-133">Получить метаданные с помощью Visual Studio для добавления ссылки на службу, или можно использовать средство ServiceModel Metadata Utility.</span><span class="sxs-lookup"><span data-stu-id="d592b-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="d592b-134">Можно указать конечную точку, клиент использует для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="d592b-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="d592b-135">Учебник. Использование клиента</span><span class="sxs-lookup"><span data-stu-id="d592b-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="d592b-136">Используйте прокси клиента WCF для вызова операций службы.</span><span class="sxs-lookup"><span data-stu-id="d592b-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="d592b-137">Ссылка</span><span class="sxs-lookup"><span data-stu-id="d592b-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="d592b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="d592b-138">See also</span></span>

- [<span data-ttu-id="d592b-139">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="d592b-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="d592b-140">Руководство по документации</span><span class="sxs-lookup"><span data-stu-id="d592b-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="d592b-141">Что такое Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d592b-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="d592b-142">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="d592b-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="d592b-143">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="d592b-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="d592b-144">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="d592b-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="d592b-145">Базовое Программирование WCF</span><span class="sxs-lookup"><span data-stu-id="d592b-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="d592b-146">Практическое руководство. Создание дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="d592b-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="d592b-147">Практическое руководство. Службы доступа с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="d592b-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="d592b-148">Служебное средство ServiceModel Metadata Utility tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="d592b-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="d592b-149">Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных</span><span class="sxs-lookup"><span data-stu-id="d592b-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="d592b-150">Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d592b-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d592b-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d592b-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d592b-152">Пример для начала работы</span><span class="sxs-lookup"><span data-stu-id="d592b-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="d592b-153">Примеры Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d592b-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="d592b-154">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="d592b-154">Self-Host</span></span>](samples/self-host.md)
