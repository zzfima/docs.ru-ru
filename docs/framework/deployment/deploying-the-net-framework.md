---
title: Развертывание .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2eb1898f03a52306a8a2763059cf198208b7b88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551843"
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="125b9-102">Развертывание .NET Framework</span><span class="sxs-lookup"><span data-stu-id="125b9-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="125b9-103">В этом разделе документации по платформе .NET Framework предоставлены сведения для разработчиков, которые хотят установить платформу .NET Framework для своих приложений, и для разработчиков, которые хотят развернуть платформу .NET Framework по сети.</span><span class="sxs-lookup"><span data-stu-id="125b9-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="125b9-104">В ней также рассмотрены вопросы активации и перезапуска, связанные с развертыванием, и описано, как отслеживать ход установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="125b9-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="125b9-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="125b9-105">In This Section</span></span>  
 [<span data-ttu-id="125b9-106">Руководство по развертыванию для разработчиков</span><span class="sxs-lookup"><span data-stu-id="125b9-106">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 <span data-ttu-id="125b9-107">Описываются способы установки .NET Framework на компьютеры пользователей вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="125b9-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="125b9-108">Руководство по развертыванию для администраторов</span><span class="sxs-lookup"><span data-stu-id="125b9-108">Deployment Guide for Administrators</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)  
 <span data-ttu-id="125b9-109">Описывается развертывание платформы .NET Framework и ее системных зависимостей в сети с помощью System Center Configuration Manager (SCCM).</span><span class="sxs-lookup"><span data-stu-id="125b9-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>  
  
 [<span data-ttu-id="125b9-110">Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="125b9-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)  
 <span data-ttu-id="125b9-111">Описывается диспетчер перезапуска, который по возможности предотвращает перезагрузки, и его преимущества для приложений, устанавливающих платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="125b9-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="125b9-112">Практическое руководство. Получение хода выполнения установщика .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="125b9-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="125b9-113">Описывается автоматический запуск и отслеживание процесса установки .NET Framework с выводом собственного представления хода выполнения установки.</span><span class="sxs-lookup"><span data-stu-id="125b9-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="125b9-114">Ошибки инициализации платформы .NET Framework. Управление пользовательской средой</span><span class="sxs-lookup"><span data-stu-id="125b9-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="125b9-115">В этой статье объясняется, что происходит, когда приложению .NET Framework требуется версия среды CLR, которая является недопустимой или не установлена на компьютере пользователя. Также описано, как устранить эти ошибки и как управлять сообщением об ошибке, которое отображается для пользователя.</span><span class="sxs-lookup"><span data-stu-id="125b9-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="125b9-116">Практическое руководство. Отладка проблем при активации среды CLR</span><span class="sxs-lookup"><span data-stu-id="125b9-116">How to: Debug CLR Activation Issues</span></span>](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="125b9-117">В этой статье объясняется, как просматривать и отлаживать журналы активации среды CLR, чтобы решить проблемы, с которыми вы можете столкнуться при настройке запуска приложения с необходимой версией CLR.</span><span class="sxs-lookup"><span data-stu-id="125b9-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125b9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="125b9-118">See also</span></span>
- [<span data-ttu-id="125b9-119">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="125b9-119">Development Guide</span></span>](../../../docs/framework/development-guide.md)
