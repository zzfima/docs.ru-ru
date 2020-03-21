---
title: 'Учебник: Начало работы с приложениями Windows Communication Foundation'
description: Эти учебники дают представление о создании приложений WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184114"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="409dd-103">Учебник: Начало работы с приложениями Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="409dd-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="409dd-104">Следующие учебники познакомят вас с опытом программирования Фонда коммуникаций Windows (WCF).</span><span class="sxs-lookup"><span data-stu-id="409dd-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="409dd-105">Работа явивая эти учебники для того, чтобы дать вам вводное понимание шагов, необходимых для создания приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="409dd-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="409dd-106">После завершения работы у вас будет запущенная служба WCF и клиент WCF, который звонит в службу.</span><span class="sxs-lookup"><span data-stu-id="409dd-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span>

<span data-ttu-id="409dd-107">Учебник предполагает, что вы используете Visual Studio в качестве среды разработки.</span><span class="sxs-lookup"><span data-stu-id="409dd-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="409dd-108">Если вы используете другую среду разработки, игнорируйте инструкции Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="409dd-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="409dd-109">Для примера приложений WCF, которые можно загрузить и запустить, [см.](samples/index.md)</span><span class="sxs-lookup"><span data-stu-id="409dd-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="409dd-110">Для введения в образцы, [см. Начало образца](samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="409dd-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="409dd-111">Для получения более подробной информации о создании сервисов и клиентов, [см.](basic-wcf-programming.md)</span><span class="sxs-lookup"><span data-stu-id="409dd-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="409dd-112">Учебники WCF</span><span class="sxs-lookup"><span data-stu-id="409dd-112">WCF tutorials</span></span>

<span data-ttu-id="409dd-113">В первых трех учебниках описывается, как определить контракт на обслуживание WCF, как его реализовать и как его разместить.</span><span class="sxs-lookup"><span data-stu-id="409dd-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="409dd-114">Создаваемый сервис является самоуправляемым в приложении консоли.</span><span class="sxs-lookup"><span data-stu-id="409dd-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="409dd-115">Вы также можете размещать услуги в рамках служб ы информации о Интернете (IIS).</span><span class="sxs-lookup"><span data-stu-id="409dd-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="409dd-116">Для получения дополнительной информации [см.](feature-details/how-to-host-a-wcf-service-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="409dd-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="409dd-117">Хотя вы используете код для настройки службы в учебнике, вы также можете [настроить службы в файле конфигурации.](configuring-services-using-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="409dd-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span>

- [<span data-ttu-id="409dd-118">Учебник: Определить контракт на обслуживание</span><span class="sxs-lookup"><span data-stu-id="409dd-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="409dd-119">Вы создаете контракт WCF с пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="409dd-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="409dd-120">Этот контракт определяет функциональность, которую предоставляет служба.</span><span class="sxs-lookup"><span data-stu-id="409dd-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="409dd-121">Учебник: Реализация сервисного контракта</span><span class="sxs-lookup"><span data-stu-id="409dd-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="409dd-122">После определения контракта необходимо реализовать его с помощью класса обслуживания.</span><span class="sxs-lookup"><span data-stu-id="409dd-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="409dd-123">Учебник: Хост и запустить базовую услугу</span><span class="sxs-lookup"><span data-stu-id="409dd-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="409dd-124">Настройте конечную точку для службы и разместите службу в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="409dd-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="409dd-125">Чтобы служба стала активной, необходимо настроить ее и разместить в среде выполнения времени.</span><span class="sxs-lookup"><span data-stu-id="409dd-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="409dd-126">Эта среда времени выполнения создает службу и контролирует ее контекст и срок службы.</span><span class="sxs-lookup"><span data-stu-id="409dd-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="409dd-127">Следующие два учебника описывают, как создавать, настраивать и использовать клиентское приложение для вызова операций, которые предоставляет служба.</span><span class="sxs-lookup"><span data-stu-id="409dd-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="409dd-128">Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="409dd-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="409dd-129">Visual Studio автоматизирует процесс доступа к этим метаданным и использует их для построения клиентского приложения для службы.</span><span class="sxs-lookup"><span data-stu-id="409dd-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="409dd-130">Если вы решите не использовать Visual Studio, вы можете использовать [инструмент ServiceModel Metadata Utility (*Svcutil.exe)*](servicemodel-metadata-utility-tool-svcutil-exe.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="409dd-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="409dd-131">Учебник: Создание клиента</span><span class="sxs-lookup"><span data-stu-id="409dd-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="409dd-132">Извлекать метаданные для создания прокси-сервера клиента WCF из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="409dd-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="409dd-133">Вы получаете метаданные с помощью Visual Studio для добавления ссылки на услуги или можете использовать инструмент ServiceModel Metadata Utility.</span><span class="sxs-lookup"><span data-stu-id="409dd-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="409dd-134">Вы указываете конечную точку, которую клиент использует для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="409dd-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="409dd-135">Учебник: Используйте клиента</span><span class="sxs-lookup"><span data-stu-id="409dd-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="409dd-136">Используйте прокси-сервер клиента WCF для вызова службы операций.</span><span class="sxs-lookup"><span data-stu-id="409dd-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="409dd-137">Справочник</span><span class="sxs-lookup"><span data-stu-id="409dd-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="409dd-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="409dd-138">See also</span></span>

- [<span data-ttu-id="409dd-139">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="409dd-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="409dd-140">Руководство по документации</span><span class="sxs-lookup"><span data-stu-id="409dd-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="409dd-141">Что такое Фонд коммуникации Windows</span><span class="sxs-lookup"><span data-stu-id="409dd-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="409dd-142">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="409dd-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="409dd-143">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="409dd-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="409dd-144">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="409dd-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="409dd-145">Базовое программирование WCF</span><span class="sxs-lookup"><span data-stu-id="409dd-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="409dd-146">Как: Создать дуплексный контракт</span><span class="sxs-lookup"><span data-stu-id="409dd-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="409dd-147">Как: Услуги доступа с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="409dd-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="409dd-148">СервисМодель Метадата Утилита инструмент (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="409dd-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="409dd-149">Как: Используйте Svcutil.exe для загрузки метаданных документов</span><span class="sxs-lookup"><span data-stu-id="409dd-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="409dd-150">Как: Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="409dd-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="409dd-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="409dd-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="409dd-152">Начало образца</span><span class="sxs-lookup"><span data-stu-id="409dd-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="409dd-153">Образцы Фонда связи Windows</span><span class="sxs-lookup"><span data-stu-id="409dd-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="409dd-154">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="409dd-154">Self-Host</span></span>](samples/self-host.md)
