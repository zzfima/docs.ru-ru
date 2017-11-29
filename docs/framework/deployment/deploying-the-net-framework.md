---
title: "Развертывание .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3a33b57ee7cf38e06195244023e8bb918dea02b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="2777d-102">Развертывание .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2777d-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="2777d-103">В этом разделе документации по платформе .NET Framework предоставлены сведения для разработчиков, которые хотят установить платформу .NET Framework для своих приложений, и для разработчиков, которые хотят развернуть платформу .NET Framework по сети.</span><span class="sxs-lookup"><span data-stu-id="2777d-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="2777d-104">В ней также рассмотрены вопросы активации и перезапуска, связанные с развертыванием, и описано, как отслеживать ход установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2777d-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2777d-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="2777d-105">In This Section</span></span>  
 [<span data-ttu-id="2777d-106">Руководство по развертыванию для разработчиков</span><span class="sxs-lookup"><span data-stu-id="2777d-106">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 <span data-ttu-id="2777d-107">Описываются способы установки .NET Framework на компьютеры пользователей вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="2777d-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="2777d-108">Руководство по развертыванию для администраторов</span><span class="sxs-lookup"><span data-stu-id="2777d-108">Deployment Guide for Administrators</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)  
 <span data-ttu-id="2777d-109">Описывается развертывание платформы .NET Framework и ее системных зависимостей в сети с помощью System Center Configuration Manager (SCCM).</span><span class="sxs-lookup"><span data-stu-id="2777d-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>  
  
 [<span data-ttu-id="2777d-110">Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="2777d-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)  
 <span data-ttu-id="2777d-111">Описывается диспетчер перезапуска, который по возможности предотвращает перезагрузки, и его преимущества для приложений, устанавливающих платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2777d-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="2777d-112">Практическое руководство. Получение хода выполнения установщика .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="2777d-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="2777d-113">Описывается автоматический запуск и отслеживание процесса установки .NET Framework с выводом собственного представления хода выполнения установки.</span><span class="sxs-lookup"><span data-stu-id="2777d-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="2777d-114">Ошибки инициализации платформы .NET Framework. Управление взаимодействием с пользователем</span><span class="sxs-lookup"><span data-stu-id="2777d-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="2777d-115">В этой статье объясняется, что происходит, когда приложению .NET Framework требуется версия среды CLR, которая является недопустимой или не установлена на компьютере пользователя. Также описано, как устранить эти ошибки и как управлять сообщением об ошибке, которое отображается для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2777d-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="2777d-116">Практическое руководство. Решение проблем при активации среды CLR</span><span class="sxs-lookup"><span data-stu-id="2777d-116">How to: Debug CLR Activation Issues</span></span>](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="2777d-117">В этой статье объясняется, как просматривать и отлаживать журналы активации среды CLR, чтобы решить проблемы, с которыми вы можете столкнуться при настройке запуска приложения с необходимой версией CLR.</span><span class="sxs-lookup"><span data-stu-id="2777d-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2777d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2777d-118">See Also</span></span>  
 [<span data-ttu-id="2777d-119">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="2777d-119">Development Guide</span></span>](../../../docs/framework/development-guide.md)
