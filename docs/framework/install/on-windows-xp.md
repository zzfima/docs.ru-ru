---
title: Установка платформы .NET Framework в Windows XP
description: Сведения об установке платформы .NET Framework в Windows XP.
ms.custom: updateeachrelease
author: rlander
ms.author: mairaw
ms.date: 04/10/2018
ms.openlocfilehash: eb62bfe992e5b3774c4a8123eb9ca3f790eaf0b9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50192880"
---
# <a name="install-the-net-framework-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="062c3-103">Установка .NET Framework в Windows XP и Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="062c3-103">Install the .NET Framework on Windows XP and Windows Server 2003</span></span>

> [!NOTE]
> <span data-ttu-id="062c3-104">Windows XP больше не поддерживается корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="062c3-104">Windows XP is no longer supported by Microsoft.</span></span> <span data-ttu-id="062c3-105">Мы рекомендуем обновить операционную систему до Windows 10, которая поддерживается производителем и содержит последнюю версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="062c3-105">We recommend you upgrade to Windows 10, which is supported and includes the latest version of the .NET Framework.</span></span> <span data-ttu-id="062c3-106">Данный документ предоставляется исключительно как руководство по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="062c3-106">This document is provided solely as a helpful troubleshooting guide.</span></span>

<span data-ttu-id="062c3-107">Для многих приложений, работающих в ОС Windows, требуется платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="062c3-107">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="062c3-108">Приведенные ниже инструкции помогут вам установить ее.</span><span class="sxs-lookup"><span data-stu-id="062c3-108">You can use the following instructions to install it.</span></span> <span data-ttu-id="062c3-109">Вы могли попасть на эту страницу после попытки запуска приложения и отображения следующего диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="062c3-109">You may have arrived on this page after trying to run an application and seeing the following dialog on your machine.</span></span>

![Не удалось запустить это приложение.](./media/this-application-could-not-be-started.png)

<span data-ttu-id="062c3-111">Эти инструкции помогут вам установить необходимые версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="062c3-111">These instructions will help you install the .NET Framework versions you need.</span></span> <span data-ttu-id="062c3-112">[.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) является самой новой версией.</span><span class="sxs-lookup"><span data-stu-id="062c3-112">The [.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) is the latest version.</span></span> <span data-ttu-id="062c3-113">Она не поддерживается в Windows XP и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="062c3-113">It is not supported on Windows XP and Windows Server 2003.</span></span> <span data-ttu-id="062c3-114">Эта платформа включена в [обновление Windows 10 за октябрь 2018 г.](https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update) и [обновление Windows 10 за апрель 2018 г.](https://www.microsoft.com/software-download/windows10)</span><span class="sxs-lookup"><span data-stu-id="062c3-114">It is included with [Windows 10 October 2018 Update](https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update) and [Windows 10 April 2018 Update](https://www.microsoft.com/software-download/windows10).</span></span>

## <a name="net-framework-403"></a><span data-ttu-id="062c3-115">.NET Framework 4.0.3</span><span class="sxs-lookup"><span data-stu-id="062c3-115">.NET Framework 4.0.3</span></span>

<span data-ttu-id="062c3-116">[.NET Framework 4.0.3](https://go.microsoft.com/fwlink/?LinkID=213834) является последней поддерживаемой версией платформы .NET Framework в Windows XP и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="062c3-116">The [.NET Framework 4.0.3](https://go.microsoft.com/fwlink/?LinkID=213834) is the latest supported .NET Framework version on Windows XP and Windows Server 2003.</span></span> <span data-ttu-id="062c3-117">Чтобы установить .NET Framework 4.0.3, сначала должна быть установлена [.NET Framework 4](https://go.microsoft.com/fwlink/?LinkID=213834).</span><span class="sxs-lookup"><span data-stu-id="062c3-117">The .NET Framework 4.0.3 requires that the [.NET Framework 4](https://go.microsoft.com/fwlink/?LinkID=213834) is installed first.</span></span> <span data-ttu-id="062c3-118">Обе эти версии .NET Framework уже не поддерживаются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="062c3-118">Both of these .NET Framework versions are no longer supported by Microsoft.</span></span>

## <a name="net-framework-4"></a><span data-ttu-id="062c3-119">.NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="062c3-119">.NET Framework 4</span></span>

<span data-ttu-id="062c3-120">На Windows XP можно установить [.NET Framework 4](https://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs).</span><span class="sxs-lookup"><span data-stu-id="062c3-120">You can install the [.NET Framework 4](https://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs) on Windows XP.</span></span> <span data-ttu-id="062c3-121">Эта версия уже не поддерживается корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="062c3-121">It's no longer supported by Microsoft.</span></span>

## <a name="net-framework-35"></a><span data-ttu-id="062c3-122">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="062c3-122">.NET Framework 3.5</span></span>

<span data-ttu-id="062c3-123">На Windows XP можно установить [.NET Framework 3.5](https://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs).</span><span class="sxs-lookup"><span data-stu-id="062c3-123">You can install the [.NET Framework 3.5](https://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs) on Windows XP.</span></span>

<span data-ttu-id="062c3-124">.NET Framework 3.5 можно использовать для запуска приложений, созданных для .NET Framework версии от 1.0 до 3.5.</span><span class="sxs-lookup"><span data-stu-id="062c3-124">The .NET Framework 3.5 can be used to run applications built for .NET Framework 1.0 through 3.5.</span></span>

## <a name="see-also"></a><span data-ttu-id="062c3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="062c3-125">See also</span></span>

<span data-ttu-id="062c3-126">[Скачивание .NET Framework](https://www.microsoft.com/net/download/framework?utm_source=ms-docs&utm_medium=referral) </span><span class="sxs-lookup"><span data-stu-id="062c3-126">[Download the .NET Framework](https://www.microsoft.com/net/download/framework?utm_source=ms-docs&utm_medium=referral) </span></span>  
<span data-ttu-id="062c3-127">[Устранение неполадок заблокированных установок и удалений .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md) </span><span class="sxs-lookup"><span data-stu-id="062c3-127">[Troubleshoot blocked .NET Framework installations and uninstallations](troubleshoot-blocked-installations-and-uninstallations.md) </span></span>  
[<span data-ttu-id="062c3-128">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="062c3-128">Install the .NET Framework for developers</span></span>](guide-for-developers.md)
