---
title: Разработка современных веб-приложений с помощью ASP.NET Core и Azure
description: Этот документ является полным руководством по созданию монолитных веб-приложений с помощью ASP.NET Core и Azure.
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 0d59a07e01897400a53f48799383d1670a468d73
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148110"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="3f200-103">Разработка современных веб-приложений с помощью ASP.NET Core и Azure</span><span class="sxs-lookup"><span data-stu-id="3f200-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![изображение обложки](./media/cover.png)

<span data-ttu-id="3f200-105">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="3f200-105">PUBLISHED BY</span></span>

<span data-ttu-id="3f200-106">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3f200-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="3f200-107">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3f200-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="3f200-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3f200-108">One Microsoft Way</span></span>

<span data-ttu-id="3f200-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="3f200-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="3f200-110">© Корпорация Майкрософт (Microsoft Corporation), 2018.</span><span class="sxs-lookup"><span data-stu-id="3f200-110">Copyright © 2018 by Microsoft Corporation</span></span>

<span data-ttu-id="3f200-111">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="3f200-111">All rights reserved.</span></span> <span data-ttu-id="3f200-112">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="3f200-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="3f200-113">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="3f200-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="3f200-114">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="3f200-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="3f200-115">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="3f200-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="3f200-116">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="3f200-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="3f200-117">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте https://www.microsoft.com, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f200-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="3f200-118">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="3f200-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="3f200-119">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="3f200-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="3f200-120">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="3f200-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="3f200-121">Автор:</span><span class="sxs-lookup"><span data-stu-id="3f200-121">Author:</span></span>

> <span data-ttu-id="3f200-122">**Стив Смит (Steve Smith) (@ardalis)**, советник по архитектуре программного обеспечения, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="3f200-122">**Steve Smith (@ardalis)**, Software Architecture Advisor, [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="3f200-123">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="3f200-123">Editors:</span></span>

> <span data-ttu-id="3f200-124">**Майра Вензел (Maira Wenzel)**</span><span class="sxs-lookup"><span data-stu-id="3f200-124">**Maira Wenzel**</span></span>

## <a name="introduction"></a><span data-ttu-id="3f200-125">Вступление</span><span class="sxs-lookup"><span data-stu-id="3f200-125">Introduction</span></span>

<span data-ttu-id="3f200-126">.NET Core и ASP.NET Core имеют ряд преимуществ по сравнению с традиционной разработкой .NET.</span><span class="sxs-lookup"><span data-stu-id="3f200-126">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="3f200-127">Используйте .NET Core для серверных приложений, если для их успешной работы вам важны некоторые или все приведенные далее аспекты:</span><span class="sxs-lookup"><span data-stu-id="3f200-127">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="3f200-128">Поддержка разных платформ.</span><span class="sxs-lookup"><span data-stu-id="3f200-128">Cross-platform support.</span></span>

- <span data-ttu-id="3f200-129">Использование микрослужб.</span><span class="sxs-lookup"><span data-stu-id="3f200-129">Use of microservices.</span></span>

- <span data-ttu-id="3f200-130">Использование контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="3f200-130">Use of Docker containers.</span></span>

- <span data-ttu-id="3f200-131">Требования к обеспечению высокой производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="3f200-131">High performance and scalability requirements.</span></span>

- <span data-ttu-id="3f200-132">Параллельное управление версиями приложения .NET на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="3f200-132">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="3f200-133">Эти требования поддерживаются традиционными приложениями .NET, однако оптимизированные платформы ASP.NET Core и .NET Core обеспечивают улучшенную поддержку указанных выше сценариев.</span><span class="sxs-lookup"><span data-stu-id="3f200-133">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="3f200-134">Все больше организаций предпочитают размещать свои веб-приложения в облаке с помощью таких служб, как Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="3f200-134">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="3f200-135">Рекомендуется рассмотреть возможность размещения приложения в облаке, если для приложения или организации важны следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="3f200-135">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="3f200-136">Сокращение инвестиций в центр обработки данных (оборудование, программное обеспечение, помещения, коммунальные услуги и т. д.)</span><span class="sxs-lookup"><span data-stu-id="3f200-136">Reduced investment in data center costs (hardware, software, space, utilities, etc.)</span></span>

- <span data-ttu-id="3f200-137">Гибкие цены (оплата за фактически используемые, а не простаивающие ресурсы).</span><span class="sxs-lookup"><span data-stu-id="3f200-137">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="3f200-138">Исключительная надежность.</span><span class="sxs-lookup"><span data-stu-id="3f200-138">Extreme reliability.</span></span>

- <span data-ttu-id="3f200-139">Улучшенная мобильность приложений, простота изменения места и способа их развертывания.</span><span class="sxs-lookup"><span data-stu-id="3f200-139">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="3f200-140">Гибкая емкость, масштабирование в соответствии с фактическими потребностями.</span><span class="sxs-lookup"><span data-stu-id="3f200-140">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="3f200-141">Создание веб-приложений с помощью ASP.NET Core, размещенных в Azure, имеет множество конкурентных преимуществ по сравнению с традиционными альтернативами.</span><span class="sxs-lookup"><span data-stu-id="3f200-141">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="3f200-142">Платформа ASP.NET Core оптимизирована для современных методик разработки веб-приложений и сценариев размещения в облаке.</span><span class="sxs-lookup"><span data-stu-id="3f200-142">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="3f200-143">В этом руководстве вы узнаете, как спроектировать приложения ASP.NET Core, чтобы максимально эффективно воспользоваться этими возможностями.</span><span class="sxs-lookup"><span data-stu-id="3f200-143">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="3f200-144">Цель</span><span class="sxs-lookup"><span data-stu-id="3f200-144">Purpose</span></span>

<span data-ttu-id="3f200-145">Этот документ является полным руководством по созданию монолитных веб-приложений с помощью ASP.NET Core и Azure.</span><span class="sxs-lookup"><span data-stu-id="3f200-145">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="3f200-146">Это руководство представляет собой дополнение к микрослужбам ["_.NET. Архитектура для упакованных в контейнеры приложений .NET_"](../microservices-architecture/index.md) с акцентом на Docker, микрослужбах и развертывании контейнеров для размещения корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="3f200-146">This guide is complementary to the ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices-architecture/index.md) which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="3f200-147">Микрослужбы .NET.</span><span class="sxs-lookup"><span data-stu-id="3f200-147">.NET Microservices.</span></span> <span data-ttu-id="3f200-148">Архитектура контейнерных приложений .NET</span><span class="sxs-lookup"><span data-stu-id="3f200-148">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="3f200-149">**электронная книга**</span><span class="sxs-lookup"><span data-stu-id="3f200-149">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="3f200-150">**Пример приложения**</span><span class="sxs-lookup"><span data-stu-id="3f200-150">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="3f200-151">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="3f200-151">Who should use this guide</span></span>

<span data-ttu-id="3f200-152">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, заинтересованных в создании современных веб-приложений с помощью технологий и служб Майкрософт в облаке.</span><span class="sxs-lookup"><span data-stu-id="3f200-152">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="3f200-153">Вторичной аудиторией являются лица, ответственные за принятие технических решений, которые уже знакомы с ASP.NET или Azure и которым требуются сведения о целесообразности обновления до ASP.NET Core для разработки новых и поддержки существующих проектов.</span><span class="sxs-lookup"><span data-stu-id="3f200-153">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="3f200-154">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="3f200-154">How you can use this guide</span></span>

<span data-ttu-id="3f200-155">Это руководство было сведено в относительно небольшой документ, в котором основное внимание уделяется созданию веб-приложений с помощью современных технологий .NET и Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="3f200-155">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="3f200-156">Поэтому, чтобы получить базовое представление о таких приложениях и разобраться в соответствующих технических рекомендациях, изучите документ полностью.</span><span class="sxs-lookup"><span data-stu-id="3f200-156">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="3f200-157">Это руководство вместе с примером приложения может быть хорошей отправной точкой или полезным справочным документом.</span><span class="sxs-lookup"><span data-stu-id="3f200-157">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="3f200-158">Используйте приведенный пример приложения в качестве шаблона для собственных приложений, или чтобы увидеть, каким образом можно организовать составные части приложения.</span><span class="sxs-lookup"><span data-stu-id="3f200-158">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="3f200-159">Принимая решение о применении этих вариантов к своему приложению, вы всегда можете обратиться к описанным в руководстве принципам и направлениям архитектуры и технологическим возможностям.</span><span class="sxs-lookup"><span data-stu-id="3f200-159">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="3f200-160">При необходимости вы можете порекомендовать это руководство членам своей команды, чтобы и они были в курсе всех важных аспектов.</span><span class="sxs-lookup"><span data-stu-id="3f200-160">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="3f200-161">Если все заинтересованные лица будут использовать общий набор терминологии и придерживаться основополагающих принципов, архитектурные модели и практики будут применяться более последовательно.</span><span class="sxs-lookup"><span data-stu-id="3f200-161">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="3f200-162">Ссылки</span><span class="sxs-lookup"><span data-stu-id="3f200-162">References</span></span>

- <span data-ttu-id="3f200-163">**Выбор между .NET Core и .NET Framework для серверных приложений**</span><span class="sxs-lookup"><span data-stu-id="3f200-163">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="3f200-164">Вперед</span><span class="sxs-lookup"><span data-stu-id="3f200-164">Next</span></span>](modern-web-applications-characteristics.md)