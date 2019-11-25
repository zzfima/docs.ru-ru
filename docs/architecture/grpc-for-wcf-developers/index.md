---
title: ASP.NET Core gRPC для разработчиков WCF — gRPC для разработчиков WCF
description: Введение в создание служб gRPC в ASP.NET Core 3.0 для разработчиков WCF
ms.date: 09/02/2019
ms.openlocfilehash: 3ef513d2397b6f282591dfe6c9b25cd178372a28
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967746"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="cc691-103">ASP.NET Core gRPC для разработчиков WCF</span><span class="sxs-lookup"><span data-stu-id="cc691-103">ASP.NET Core gRPC for WCF Developers</span></span>

![изображение обложки](./media/cover.png)

<span data-ttu-id="cc691-105">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="cc691-105">PUBLISHED BY</span></span>

<span data-ttu-id="cc691-106">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc691-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="cc691-107">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cc691-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="cc691-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cc691-108">One Microsoft Way</span></span>

<span data-ttu-id="cc691-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="cc691-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="cc691-110">© Корпорация Майкрософт (Microsoft Corporation), 2019.</span><span class="sxs-lookup"><span data-stu-id="cc691-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="cc691-111">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="cc691-111">All rights reserved.</span></span> <span data-ttu-id="cc691-112">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="cc691-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="cc691-113">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="cc691-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="cc691-114">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="cc691-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="cc691-115">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="cc691-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="cc691-116">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="cc691-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="cc691-117">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте https://www.microsoft.com, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc691-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="cc691-118">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="cc691-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="cc691-119">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="cc691-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="cc691-120">Автор:</span><span class="sxs-lookup"><span data-stu-id="cc691-120">Author:</span></span>

> <span data-ttu-id="cc691-121">**Марк Рендл (Mark Rendle)**  — главный технический директор — [Visual Recode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="cc691-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="cc691-122">**Миранда Стайнер (Miranda Steiner)**  — технический писатель</span><span class="sxs-lookup"><span data-stu-id="cc691-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="cc691-123">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="cc691-123">Editors:</span></span>

> <span data-ttu-id="cc691-124">**Майра Вензел (Maira Wenzel)**  — старший разработчик содержимого — корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cc691-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="cc691-125">Вступление</span><span class="sxs-lookup"><span data-stu-id="cc691-125">Introduction</span></span>

<span data-ttu-id="cc691-126">gRPC — это современная платформа для создания сетевых служб и распределенных приложений.</span><span class="sxs-lookup"><span data-stu-id="cc691-126">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="cc691-127">Представьте себе производительность привязок NetTCP WCF с кроссплатформенным взаимодействием SOAP.</span><span class="sxs-lookup"><span data-stu-id="cc691-127">Imagine the performance of WCF's NetTCP bindings with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="cc691-128">gRPC основывается на HTTP/2 и протоколе кодирования сообщений Protobuf для обеспечения высокой производительности и низкого потребления пропускной способности при взаимодействии приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="cc691-128">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="cc691-129">Она поддерживает создание серверного и клиентского кода в большинстве популярных языков программирования и платформ, включая .NET, Java, Python, Node.js, Go, C++ и многие другие.</span><span class="sxs-lookup"><span data-stu-id="cc691-129">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, C++ and more.</span></span> <span data-ttu-id="cc691-130">Учитывая первоклассную поддержку gRPC в ASP.NET Core 3.0 и имеющиеся средства и библиотеки gRPC для .NET 4.x, мы считаем ее отличной альтернативой WCF для команд разработчиков, стремящихся внедрить .NET Core в своих организациях.</span><span class="sxs-lookup"><span data-stu-id="cc691-130">With the first-class support for gRPC in ASP.NET Core 3.0, alongside the existing gRPC tools and libraries for .NET 4.x, we think it is an excellent alternative to WCF for development teams looking to adopt .NET Core in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="cc691-131">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="cc691-131">Who should use this guide</span></span>

<span data-ttu-id="cc691-132">Это руководство было написано для разработчиков, работающих в .NET Framework или .NET Core, которые ранее пользовались WCF и хотят перенести свои приложения в современную среду RPC для .NET Core 3.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cc691-132">This guide was written for developers working in .NET Framework or .NET Core who have previously used WCF and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="cc691-133">Кроме того, это руководство может пригодиться разработчикам, которые производят обновление до .NET Core 3.0 либо рассматривают такую возможность и при этом хотят использовать встроенные средства gRPC.</span><span class="sxs-lookup"><span data-stu-id="cc691-133">The guide may also be of use more generally for developers upgrading or considering upgrading to .NET Core 3.0 who want to use the built-in gRPC tools.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="cc691-134">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="cc691-134">How you can use this guide</span></span>

<span data-ttu-id="cc691-135">Это краткое введение в создание служб gRPC в ASP.NET Core 3.0 с определенной ссылкой на WCF как на аналогичную платформу.</span><span class="sxs-lookup"><span data-stu-id="cc691-135">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="cc691-136">В нем объясняются принципы gRPC, связывающие каждую из представленных концепций с эквивалентными функциями в WCF, и даются рекомендации по переносу существующего приложения WCF в gRPC.</span><span class="sxs-lookup"><span data-stu-id="cc691-136">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="cc691-137">Оно также полезно для разработчиков, имеющих опыт работы с WCF и желающих изучать gRPC для создания новых служб.</span><span class="sxs-lookup"><span data-stu-id="cc691-137">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="cc691-138">Эти примеры приложений можно использовать в качестве шаблона для собственных проектов, и вы можете свободно копировать и повторно использовать код из книги или ее примеров.</span><span class="sxs-lookup"><span data-stu-id="cc691-138">The sample applications can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="cc691-139">При необходимости вы можете порекомендовать это руководство членам своей команды, чтобы и они были в курсе всех важных аспектов.</span><span class="sxs-lookup"><span data-stu-id="cc691-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="cc691-140">Если все заинтересованные лица будут использовать общий набор терминологии и придерживаться основополагающих принципов, архитектурные модели и практики будут применяться более последовательно.</span><span class="sxs-lookup"><span data-stu-id="cc691-140">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="cc691-141">Ссылки</span><span class="sxs-lookup"><span data-stu-id="cc691-141">References</span></span>

- <span data-ttu-id="cc691-142">**Веб-сайт gRPC**</span><span class="sxs-lookup"><span data-stu-id="cc691-142">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="cc691-143">**Выбор между .NET Core и .NET Framework для серверных приложений**</span><span class="sxs-lookup"><span data-stu-id="cc691-143">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="cc691-144">Вперед</span><span class="sxs-lookup"><span data-stu-id="cc691-144">Next</span></span>](introduction.md)
