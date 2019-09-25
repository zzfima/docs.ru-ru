---
title: ASP.NET Core gRPC для разработчиков WCF — gRPC для разработчиков WCF
description: Подлежит написанию
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 7d02d7914aed39613b4a41da55515df80abddfe8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182751"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="30ea9-103">ASP.NET Core gRPC для разработчиков WCF</span><span class="sxs-lookup"><span data-stu-id="30ea9-103">ASP.NET Core gRPC for WCF Developers</span></span>

![изображение обложки](./media/cover.png)

<span data-ttu-id="30ea9-105">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="30ea9-105">PUBLISHED BY</span></span>

<span data-ttu-id="30ea9-106">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30ea9-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="30ea9-107">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="30ea9-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="30ea9-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="30ea9-108">One Microsoft Way</span></span>

<span data-ttu-id="30ea9-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="30ea9-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="30ea9-110">© Корпорация Майкрософт (Microsoft Corporation), 2019.</span><span class="sxs-lookup"><span data-stu-id="30ea9-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="30ea9-111">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="30ea9-111">All rights reserved.</span></span> <span data-ttu-id="30ea9-112">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="30ea9-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="30ea9-113">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="30ea9-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="30ea9-114">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="30ea9-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="30ea9-115">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="30ea9-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="30ea9-116">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="30ea9-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="30ea9-117">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте https://www.microsoft.com, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="30ea9-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="30ea9-118">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="30ea9-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="30ea9-119">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="30ea9-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="30ea9-120">Автор:</span><span class="sxs-lookup"><span data-stu-id="30ea9-120">Author:</span></span>

> <span data-ttu-id="30ea9-121">**Марк Рендл (Mark Rendle)**  — главный технический директор — [Visual Recode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="30ea9-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="30ea9-122">**Миранда Стайнер (Miranda Steiner)**  — технический писатель</span><span class="sxs-lookup"><span data-stu-id="30ea9-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="30ea9-123">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="30ea9-123">Editors:</span></span>

> <span data-ttu-id="30ea9-124">**Майра Вензел (Maira Wenzel)**  — старший разработчик содержимого — корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="30ea9-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="30ea9-125">Вступление</span><span class="sxs-lookup"><span data-stu-id="30ea9-125">Introduction</span></span>

<span data-ttu-id="30ea9-126">TODO</span><span class="sxs-lookup"><span data-stu-id="30ea9-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="30ea9-127">Цель</span><span class="sxs-lookup"><span data-stu-id="30ea9-127">Purpose</span></span>

<span data-ttu-id="30ea9-128">TODO</span><span class="sxs-lookup"><span data-stu-id="30ea9-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="30ea9-129">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="30ea9-129">Who should use this guide</span></span>

<span data-ttu-id="30ea9-130">**ОБНОВИТЕ ЭТО**</span><span class="sxs-lookup"><span data-stu-id="30ea9-130">**UPDATE THIS**</span></span>

<span data-ttu-id="30ea9-131">Это руководство предназначено для разработчиков WCF, руководителей отделов разработки и архитекторов, заинтересованных в переносе решений WCF на базе .NET 4 и более ранних версий в ASP.NET Core 3.0 с использованием служб gRPC.</span><span class="sxs-lookup"><span data-stu-id="30ea9-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="30ea9-132">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="30ea9-132">How you can use this guide</span></span>

<span data-ttu-id="30ea9-133">**ОБНОВИТЕ ЭТО**</span><span class="sxs-lookup"><span data-stu-id="30ea9-133">**UPDATE THIS**</span></span>

<span data-ttu-id="30ea9-134">Это краткое введение в создание служб gRPC в ASP.NET Core 3.0 с определенной ссылкой на WCF как на аналогичную платформу.</span><span class="sxs-lookup"><span data-stu-id="30ea9-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="30ea9-135">В нем объясняются принципы gRPC, связывающие каждую из представленных концепций с эквивалентными функциями в WCF, и даются рекомендации по переносу существующего приложения WCF в gRPC.</span><span class="sxs-lookup"><span data-stu-id="30ea9-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="30ea9-136">Оно также полезно для разработчиков, имеющих опыт работы с WCF и желающих изучать gRPC для создания новых служб.</span><span class="sxs-lookup"><span data-stu-id="30ea9-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="30ea9-137">Этот пример приложения можно использовать в качестве шаблона для собственных проектов, и вы можете свободно копировать и повторно использовать код из книги или ее примеров.</span><span class="sxs-lookup"><span data-stu-id="30ea9-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="30ea9-138">При необходимости вы можете порекомендовать это руководство членам своей команды, чтобы и они были в курсе всех важных аспектов.</span><span class="sxs-lookup"><span data-stu-id="30ea9-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="30ea9-139">Если все заинтересованные лица будут использовать общий набор терминологии и придерживаться основополагающих принципов, архитектурные модели и практики будут применяться более последовательно.</span><span class="sxs-lookup"><span data-stu-id="30ea9-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="30ea9-140">Ссылки</span><span class="sxs-lookup"><span data-stu-id="30ea9-140">References</span></span>

- <span data-ttu-id="30ea9-141">**Веб-сайт gRPC**</span><span class="sxs-lookup"><span data-stu-id="30ea9-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="30ea9-142">**Выбор между .NET Core и .NET Framework для серверных приложений**</span><span class="sxs-lookup"><span data-stu-id="30ea9-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="30ea9-143">Вперед</span><span class="sxs-lookup"><span data-stu-id="30ea9-143">Next</span></span>](introduction.md)
