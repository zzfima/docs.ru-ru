---
title: Общие сведения о контейнерах и Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 8d1062aaea85cf810fa07b36252974eceb227c43
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="72d97-103">Общие сведения о контейнерах и Docker</span><span class="sxs-lookup"><span data-stu-id="72d97-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="72d97-104">Контейнеризация — это подход к разработке программного обеспечения, при котором приложение или служба, их зависимости и конфигурация (абстрактные файлы манифеста развертывания) упаковываются вместе в образ контейнера.</span><span class="sxs-lookup"><span data-stu-id="72d97-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="72d97-105">Контейнерное приложение можно тестировать как единое целое и развертывать как экземпляр образа контейнера в операционной системе (ОС) узла.</span><span class="sxs-lookup"><span data-stu-id="72d97-105">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="72d97-106">Так же как обычные контейнеры позволяют перевозить любые грузы на корабле, поезде или грузовике, программные контейнеры выступают в качестве стандартных модулей программного обеспечения, которые могут содержать различный код и зависимости.</span><span class="sxs-lookup"><span data-stu-id="72d97-106">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="72d97-107">Размещение программного обеспечения в контейнерах позволяет разработчикам и ИТ-специалистам развертывать эти контейнеры в разных средах без каких-либо изменений или с минимальными изменениями.</span><span class="sxs-lookup"><span data-stu-id="72d97-107">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="72d97-108">Контейнеры также изолируют приложения друг от друга в общей операционной системе.</span><span class="sxs-lookup"><span data-stu-id="72d97-108">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="72d97-109">Контейнерные приложения выполняются на основе узла контейнеров, который в свою очередь работает в операционной системе (Linux или Windows).</span><span class="sxs-lookup"><span data-stu-id="72d97-109">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="72d97-110">Поэтому контейнеры требуют гораздо меньше ресурсов, чем образы виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="72d97-110">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="72d97-111">Каждый контейнер может вмещать целое веб-приложение или службу, как показано на рис. 1-1.</span><span class="sxs-lookup"><span data-stu-id="72d97-111">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="72d97-112">Рис. 1-1.Несколько контейнеров на одном узле</span><span class="sxs-lookup"><span data-stu-id="72d97-112">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="72d97-113">В этом примере узел Docker — это узел контейнеров, а App1, App2, Svc 1 и Svc 2 — контейнерные приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="72d97-113">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="72d97-114">Еще одним преимуществом контейнеризации является масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="72d97-114">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="72d97-115">Вы можете быстро осуществлять горизонтальное масштабирование, создавая контейнеры для краткосрочных задач.</span><span class="sxs-lookup"><span data-stu-id="72d97-115">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="72d97-116">С точки зрения приложения, *создание экземпляра образа* (контейнера) аналогично созданию экземпляра процесса, например для службы или веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="72d97-116">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="72d97-117">Но для обеспечения надежности при запуске нескольких экземпляров одного образа на нескольких серверах обычно желательно, чтобы контейнеры (экземпляры образа) выполнялись на разных серверах или виртуальных машинах в разных доменах сбоя.</span><span class="sxs-lookup"><span data-stu-id="72d97-117">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="72d97-118">Иными словами, контейнеры предоставляют такие преимущества, как изоляция, переносимость, гибкость, масштабируемость и контроль, на протяжении всего жизненного цикла приложения.</span><span class="sxs-lookup"><span data-stu-id="72d97-118">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="72d97-119">Самым важным преимуществом является изоляция среды разработки от рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="72d97-119">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="72d97-120">[Далее] (what-is-docker.md)</span><span class="sxs-lookup"><span data-stu-id="72d97-120">[Next] (what-is-docker.md)</span></span>
