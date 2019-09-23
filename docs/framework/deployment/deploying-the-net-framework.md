---
title: Развертывание .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6906ccf5b639d6b90b921b5d471aa723aeb4da78
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052170"
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="64598-102">Развертывание .NET Framework</span><span class="sxs-lookup"><span data-stu-id="64598-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="64598-103">В этом разделе документации по платформе .NET Framework предоставлены сведения для разработчиков, которые хотят установить платформу .NET Framework для своих приложений, и для разработчиков, которые хотят развернуть платформу .NET Framework по сети.</span><span class="sxs-lookup"><span data-stu-id="64598-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="64598-104">В ней также рассмотрены вопросы активации и перезапуска, связанные с развертыванием, и описано, как отслеживать ход установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64598-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64598-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="64598-105">In This Section</span></span>  
 [<span data-ttu-id="64598-106">Руководство по развертыванию для разработчиков</span><span class="sxs-lookup"><span data-stu-id="64598-106">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)  
 <span data-ttu-id="64598-107">Описываются способы установки .NET Framework на компьютеры пользователей вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="64598-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="64598-108">Руководство по развертыванию для администраторов</span><span class="sxs-lookup"><span data-stu-id="64598-108">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)  
 <span data-ttu-id="64598-109">Описывается развертывание платформы .NET Framework и ее системных зависимостей в сети с помощью System Center Configuration Manager (SCCM).</span><span class="sxs-lookup"><span data-stu-id="64598-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>  
  
 [<span data-ttu-id="64598-110">Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="64598-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)  
 <span data-ttu-id="64598-111">Описывается диспетчер перезапуска, который по возможности предотвращает перезагрузки, и его преимущества для приложений, устанавливающих платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64598-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="64598-112">Практическое руководство. Получение хода выполнения установщика .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="64598-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="64598-113">Описывается автоматический запуск и отслеживание процесса установки .NET Framework с выводом собственного представления хода выполнения установки.</span><span class="sxs-lookup"><span data-stu-id="64598-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="64598-114">Ошибки инициализации платформы .NET Framework. Управление пользовательской средой</span><span class="sxs-lookup"><span data-stu-id="64598-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="64598-115">В этой статье объясняется, что происходит, когда приложению .NET Framework требуется версия среды CLR, которая является недопустимой или не установлена на компьютере пользователя. Также описано, как устранить эти ошибки и как управлять сообщением об ошибке, которое отображается для пользователя.</span><span class="sxs-lookup"><span data-stu-id="64598-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="64598-116">Практическое руководство. Отладка проблем при активации среды CLR</span><span class="sxs-lookup"><span data-stu-id="64598-116">How to: Debug CLR Activation Issues</span></span>](how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="64598-117">В этой статье объясняется, как просматривать и отлаживать журналы активации среды CLR, чтобы решить проблемы, с которыми вы можете столкнуться при настройке запуска приложения с необходимой версией CLR.</span><span class="sxs-lookup"><span data-stu-id="64598-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64598-118">См. также</span><span class="sxs-lookup"><span data-stu-id="64598-118">See also</span></span>

- [<span data-ttu-id="64598-119">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="64598-119">Development Guide</span></span>](../development-guide.md)
