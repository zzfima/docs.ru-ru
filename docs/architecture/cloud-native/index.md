---
title: Разработка ориентированных на облако приложений .NET для Azure
description: Руководство по созданию ориентированных на облако приложений, использующих контейнеры, микрослужбы и бессерверные функции Azure.
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: 7f14a690d0153edc43f0ce7f4e91c9e9cd2c6858
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71696777"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="43f60-103">Разработка ориентированных на облако приложений .NET для Azure</span><span class="sxs-lookup"><span data-stu-id="43f60-103">Architecting Cloud Native .NET Applications for Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![изображение обложки](./media/cover.png)

<span data-ttu-id="43f60-105">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="43f60-105">PUBLISHED BY</span></span>

<span data-ttu-id="43f60-106">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="43f60-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="43f60-107">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="43f60-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="43f60-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="43f60-108">One Microsoft Way</span></span>

<span data-ttu-id="43f60-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="43f60-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="43f60-110">© Корпорация Майкрософт (Microsoft Corporation), 2019.</span><span class="sxs-lookup"><span data-stu-id="43f60-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="43f60-111">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="43f60-111">All rights reserved.</span></span> <span data-ttu-id="43f60-112">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="43f60-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="43f60-113">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="43f60-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="43f60-114">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="43f60-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="43f60-115">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="43f60-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="43f60-116">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="43f60-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="43f60-117">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте https://www.microsoft.com, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="43f60-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="43f60-118">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="43f60-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="43f60-119">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="43f60-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="43f60-120">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="43f60-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="43f60-121">Авторы:</span><span class="sxs-lookup"><span data-stu-id="43f60-121">Authors:</span></span>

> <span data-ttu-id="43f60-122">**Стив Смит (Steve Smith)** , преподаватель и разработчик программного обеспечения, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="43f60-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="43f60-123">**Роб Веттор (Rob Vettor)**  — Майкрософт — главный архитектор облачных систем/IP-архитектор — [RobVettor.com](https://robvettor.com)</span><span class="sxs-lookup"><span data-stu-id="43f60-123">**Rob Vettor** - Microsoft - Principal Cloud System Architect/IP Architect - [RobVettor.com](https://robvettor.com)</span></span>

<span data-ttu-id="43f60-124">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="43f60-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="43f60-125">**Цезарь де ла Торре (Cesar De la Torre)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="43f60-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="43f60-126">**Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="43f60-126">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>

<span data-ttu-id="43f60-127">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="43f60-127">Editors:</span></span>

> <span data-ttu-id="43f60-128">**Майра Вензел (Maira Wenzel)** , старший разработчик содержимого, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="43f60-128">**Maira Wenzel**, Sr. Content Developer, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="43f60-129">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="43f60-129">Who should use this guide</span></span>

<span data-ttu-id="43f60-130">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, желающих научиться создавать приложения, ориентированные на облако.</span><span class="sxs-lookup"><span data-stu-id="43f60-130">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="43f60-131">Побочной аудиторией являются лица, принимающие решения технического характера, которым нужно определить, использовать ли ориентацию на облако при создании своих приложений.</span><span class="sxs-lookup"><span data-stu-id="43f60-131">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="43f60-132">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="43f60-132">How you can use this guide</span></span>

<span data-ttu-id="43f60-133">Это руководство начинается с определения ориентации на облако и представляет эталонное приложение, созданное с применением принципов и технологий ориентации на облако.</span><span class="sxs-lookup"><span data-stu-id="43f60-133">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="43f60-134">Помимо этих первых двух глав, оставшаяся часть книги поделена на главы, касающиеся большинства ориентированных на облако приложений.</span><span class="sxs-lookup"><span data-stu-id="43f60-134">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="43f60-135">Вы можете перейти к любой из этих глав, чтобы узнать о подходах ориентации на облако.</span><span class="sxs-lookup"><span data-stu-id="43f60-135">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="43f60-136">Данные и доступ к ним</span><span class="sxs-lookup"><span data-stu-id="43f60-136">Data and data access</span></span>
- <span data-ttu-id="43f60-137">Модели связи</span><span class="sxs-lookup"><span data-stu-id="43f60-137">Communication patterns</span></span>
- <span data-ttu-id="43f60-138">Масштабирование и масштабируемость</span><span class="sxs-lookup"><span data-stu-id="43f60-138">Scaling and scalability</span></span>
- <span data-ttu-id="43f60-139">Устойчивость приложения</span><span class="sxs-lookup"><span data-stu-id="43f60-139">Application resiliency</span></span>
- <span data-ttu-id="43f60-140">Мониторинг и работоспособность</span><span class="sxs-lookup"><span data-stu-id="43f60-140">Monitoring and health</span></span>
- <span data-ttu-id="43f60-141">Идентификация и безопасность</span><span class="sxs-lookup"><span data-stu-id="43f60-141">Identity and security</span></span>
- <span data-ttu-id="43f60-142">DevOps</span><span class="sxs-lookup"><span data-stu-id="43f60-142">DevOps</span></span>

<span data-ttu-id="43f60-143">Руководство доступно как в формате PDF, так и в интерактивном формате.</span><span class="sxs-lookup"><span data-stu-id="43f60-143">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="43f60-144">При необходимости вы можете порекомендовать этот документ членам своей команды или отправить им ссылку на его интернет-версию, чтобы они были в курсе этих аспектов.</span><span class="sxs-lookup"><span data-stu-id="43f60-144">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="43f60-145">В большинстве этих вопросов важную роль играет понимание базовых принципов и шаблонов, а также компромиссов, связанных с соответствующими решениями.</span><span class="sxs-lookup"><span data-stu-id="43f60-145">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="43f60-146">Цель этого документа заключается в том, чтобы предоставить командам и их руководителям сведения, необходимые для принятия взвешенных решений по архитектуре, разработке и размещению приложений.</span><span class="sxs-lookup"><span data-stu-id="43f60-146">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="43f60-147">Вперед</span><span class="sxs-lookup"><span data-stu-id="43f60-147">Next</span></span>](introduction.md)
