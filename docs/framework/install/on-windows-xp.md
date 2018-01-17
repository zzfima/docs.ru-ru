---
title: "Установка платформы .NET Framework в Windows XP"
description: "Сведения об установке платформы .NET Framework в Windows XP."
author: rlander
ms.author: mairaw
keywords: ".NET Framework, установка"
ms.date: 08/03/2017
ms.topic: article
ms.prod: .net-framework
ms.devlang: dotnet
ms.workload: dotnet
ms.openlocfilehash: 83def2091cf1fdc7d3d359c98aa3116a009d465d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="install-the-net-framework-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="e3f5c-104">Установка .NET Framework в Windows XP и Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="e3f5c-104">Install the .NET Framework on Windows XP and Windows Server 2003</span></span>

> [!NOTE]
> <span data-ttu-id="e3f5c-105">Windows XP больше не поддерживается корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-105">Windows XP is no longer supported by Microsoft.</span></span> <span data-ttu-id="e3f5c-106">Мы рекомендуем обновить операционную систему до Windows 10, которая поддерживается производителем и содержит последнюю версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-106">We recommend you upgrade to Windows 10, which is supported and includes the latest version of the .NET Framework.</span></span> <span data-ttu-id="e3f5c-107">Данный документ предоставляется исключительно как руководство по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-107">This document is provided solely as a helpful troubleshooting guide.</span></span>

<span data-ttu-id="e3f5c-108">Для многих приложений, работающих в ОС Windows, требуется платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-108">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="e3f5c-109">Приведенные ниже инструкции помогут вам установить ее.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-109">You can use the following instructions to install it.</span></span> <span data-ttu-id="e3f5c-110">Вы могли попасть на эту страницу после попытки запуска приложения и отображения следующего диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-110">You may have arrived on this page after trying to run an application and seeing the following dialog on your machine.</span></span>

![Не удалось запустить это приложение.](./media/this-application-could-not-be-started.png)

<span data-ttu-id="e3f5c-112">Эти инструкции помогут вам установить необходимые версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-112">These instructions will help you install the .NET Framework versions you need.</span></span> <span data-ttu-id="e3f5c-113">[.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) является самой новой версией.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-113">The [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) is the latest version.</span></span> <span data-ttu-id="e3f5c-114">Она не поддерживается в Windows XP и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-114">It is not supported on Windows XP and Windows Server 2003.</span></span> <span data-ttu-id="e3f5c-115">Она входит в состав [Windows 10 Fall Creators Update](https://www.microsoft.com/software-download/windows10) и [Windows Server 2016 версии 1709](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709).</span><span class="sxs-lookup"><span data-stu-id="e3f5c-115">It is included with the [Windows 10 Fall Creators Update](https://www.microsoft.com/software-download/windows10) and [Windows Server 2016 Version 1709](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709).</span></span>

## <a name="net-framework-403"></a><span data-ttu-id="e3f5c-116">.NET Framework 4.0.3</span><span class="sxs-lookup"><span data-stu-id="e3f5c-116">.NET Framework 4.0.3</span></span>

<span data-ttu-id="e3f5c-117">[.NET Framework 4.0.3](http://go.microsoft.com/fwlink/?LinkID=213834) является последней поддерживаемой версией платформы .NET Framework в Windows XP и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-117">The [.NET Framework 4.0.3](http://go.microsoft.com/fwlink/?LinkID=213834) is the latest supported .NET Framework version on Windows XP and Windows Server 2003.</span></span> <span data-ttu-id="e3f5c-118">Чтобы установить .NET Framework 4.0.3, сначала должна быть установлена [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834).</span><span class="sxs-lookup"><span data-stu-id="e3f5c-118">The .NET Framework 4.0.3 requires that the [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834) is installed first.</span></span> <span data-ttu-id="e3f5c-119">Обе эти версии .NET Framework уже не поддерживаются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-119">Both of these .NET Framework versions are no longer supported by Microsoft.</span></span>

## <a name="net-framework-4"></a><span data-ttu-id="e3f5c-120">.NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="e3f5c-120">.NET Framework 4</span></span>

<span data-ttu-id="e3f5c-121">На Windows XP можно установить [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs).</span><span class="sxs-lookup"><span data-stu-id="e3f5c-121">You can install the [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs) on Windows XP.</span></span> <span data-ttu-id="e3f5c-122">Эта версия уже не поддерживается корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-122">It's no longer supported by Microsoft.</span></span>

## <a name="net-framework-35"></a><span data-ttu-id="e3f5c-123">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="e3f5c-123">.NET Framework 3.5</span></span>

<span data-ttu-id="e3f5c-124">На Windows XP можно установить [.NET Framework 3.5](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs).</span><span class="sxs-lookup"><span data-stu-id="e3f5c-124">You can install the [.NET Framework 3.5](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs) on Windows XP.</span></span>

<span data-ttu-id="e3f5c-125">.NET Framework 3.5 можно использовать для запуска приложений, созданных для .NET Framework версии от 1.0 до 3.5.</span><span class="sxs-lookup"><span data-stu-id="e3f5c-125">The .NET Framework 3.5 can be used to run applications built for .NET Framework 1.0 through 3.5.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3f5c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e3f5c-126">See also</span></span>

<span data-ttu-id="e3f5c-127">[Скачивание .NET Framework](https://www.microsoft.com/net/download/framework?utm_source=ms-docs&utm_medium=referral) </span><span class="sxs-lookup"><span data-stu-id="e3f5c-127">[Download the .NET Framework](https://www.microsoft.com/net/download/framework?utm_source=ms-docs&utm_medium=referral) </span></span>  
<span data-ttu-id="e3f5c-128">[Устранение неполадок заблокированных установок и удалений .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md) </span><span class="sxs-lookup"><span data-stu-id="e3f5c-128">[Troubleshoot blocked .NET Framework installations and uninstallations](troubleshoot-blocked-installations-and-uninstallations.md) </span></span>  
[<span data-ttu-id="e3f5c-129">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="e3f5c-129">Install the .NET Framework for developers</span></span>](guide-for-developers.md)
