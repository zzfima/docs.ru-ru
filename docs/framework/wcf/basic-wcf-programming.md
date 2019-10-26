---
title: Базовое программирование WCF
ms.date: 03/30/2017
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
ms.openlocfilehash: eff565fa18e3360170584395adcf2a3e7029ac07
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960933"
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="37013-102">Базовое программирование WCF</span><span class="sxs-lookup"><span data-stu-id="37013-102">Basic WCF programming</span></span>

<span data-ttu-id="37013-103">В этом разделе представлены основные принципы создания приложений Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="37013-103">This section presents the fundamentals for creating Windows Communication Foundation (WCF) applications.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="37013-104">В данном разделе</span><span class="sxs-lookup"><span data-stu-id="37013-104">In this section</span></span>

 <span data-ttu-id="37013-105">[Базовый жизненный цикл программирования](basic-programming-lifecycle.md)</span><span class="sxs-lookup"><span data-stu-id="37013-105">[Basic Programming Lifecycle](basic-programming-lifecycle.md)</span></span>\
 <span data-ttu-id="37013-106">Описание жизненного цикла разработки, сборки и развертывания служб и клиентских приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="37013-106">Describes the lifecycle of designing, building, and deploying WCF service and client applications.</span></span>

 <span data-ttu-id="37013-107">[Проектирование и реализация служб](designing-and-implementing-services.md)</span><span class="sxs-lookup"><span data-stu-id="37013-107">[Designing and Implementing Services](designing-and-implementing-services.md)</span></span>\
 <span data-ttu-id="37013-108">Описание разработки и реализации контракта службы, выбора шаблона обмена сообщениями, задания контракта сбоя и других основных аспектов служб.</span><span class="sxs-lookup"><span data-stu-id="37013-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>

 <span data-ttu-id="37013-109">[Configuring Services](configuring-services.md)</span><span class="sxs-lookup"><span data-stu-id="37013-109">[Configuring Services](configuring-services.md)</span></span>\
 <span data-ttu-id="37013-110">Описывает настройку службы WCF для поддержки требований контракта, настройку поведения локальной среды выполнения и указание адреса для публикации службы.</span><span class="sxs-lookup"><span data-stu-id="37013-110">Describes how to configure a WCF service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>

 <span data-ttu-id="37013-111">\ [служб размещения](hosting-services.md)</span><span class="sxs-lookup"><span data-stu-id="37013-111">[Hosting Services](hosting-services.md)\</span></span>
 <span data-ttu-id="37013-112">Описание основных принципов размещения служб в приложении.</span><span class="sxs-lookup"><span data-stu-id="37013-112">Describes the basics of hosting services in an application.</span></span>

 <span data-ttu-id="37013-113">[Создание клиентов](building-clients.md)</span><span class="sxs-lookup"><span data-stu-id="37013-113">[Building Clients](building-clients.md)</span></span>\
 <span data-ttu-id="37013-114">Описывает получение метаданных из служб, преобразование их в клиентский код WCF, обработку проблем безопасности, а затем сборку, настройку и размещение клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="37013-114">Describes how to obtain metadata from services, convert that into WCF client code, handle security issues, and build, configure, and host a WCF client.</span></span>

 <span data-ttu-id="37013-115">[Введение в расширяемость](introduction-to-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="37013-115">[Introduction to Extensibility](introduction-to-extensibility.md)</span></span>\
 <span data-ttu-id="37013-116">Описывает, как расширить WCF для создания пользовательских решений.</span><span class="sxs-lookup"><span data-stu-id="37013-116">Describes how to extend WCF to create custom solutions.</span></span>

 <span data-ttu-id="37013-117">[Краткое руководство по устранению неполадок WCF](wcf-troubleshooting-quickstart.md)</span><span class="sxs-lookup"><span data-stu-id="37013-117">[WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md)</span></span>\
 <span data-ttu-id="37013-118">Описание наиболее распространенных проблем, способов их решения и источников дополнительной информации о них.</span><span class="sxs-lookup"><span data-stu-id="37013-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>

 <span data-ttu-id="37013-119">[WCF и веб-API ASP.NET](wcf-and-aspnet-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="37013-119">[WCF and ASP.NET Web API](wcf-and-aspnet-web-api.md)</span></span>\
 <span data-ttu-id="37013-120">Описывает две технологии, их взаимосвязь друг с другом и способы их использования.</span><span class="sxs-lookup"><span data-stu-id="37013-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>

## <a name="reference"></a><span data-ttu-id="37013-121">Справочники</span><span class="sxs-lookup"><span data-stu-id="37013-121">Reference</span></span>

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Description>

## <a name="related-sections"></a><span data-ttu-id="37013-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="37013-122">Related sections</span></span>

- [<span data-ttu-id="37013-123">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="37013-123">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="37013-124">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="37013-124">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="37013-125">Правила и рекомендации</span><span class="sxs-lookup"><span data-stu-id="37013-125">Guidelines and Best Practices</span></span>](guidelines-and-best-practices.md)
- [<span data-ttu-id="37013-126">Средства Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="37013-126">Windows Communication Foundation Tools</span></span>](tools.md)
- [<span data-ttu-id="37013-127">Примеры Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="37013-127">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="37013-128">Начало работы</span><span class="sxs-lookup"><span data-stu-id="37013-128">Getting Started</span></span>](./samples/getting-started-sample.md)
- [<span data-ttu-id="37013-129">Размещение в службах IIS с использованием встроенного кода</span><span class="sxs-lookup"><span data-stu-id="37013-129">IIS Hosting Using Inline Code</span></span>](./samples/iis-hosting-using-inline-code.md)
- [<span data-ttu-id="37013-130">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="37013-130">Self-Host</span></span>](./samples/self-host.md)
