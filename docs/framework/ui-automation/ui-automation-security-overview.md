---
title: "Общие сведения о безопасности модели автоматизации пользовательского интерфейса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
caps.latest.revision: "23"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: c9cec20d2ab011f2ec6d44dc5d899e3d83c4dba5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="e33aa-102">Общие сведения о безопасности модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e33aa-102">UI Automation Security Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="e33aa-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="e33aa-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e33aa-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="e33aa-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e33aa-105">В этом обзоре описывается модель безопасности для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] в [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e33aa-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a><span data-ttu-id="e33aa-106">контроль учетных записей</span><span class="sxs-lookup"><span data-stu-id="e33aa-106">User Account Control</span></span>  
 <span data-ttu-id="e33aa-107">Безопасность является основным направлением [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] , и среди нововведений можно отметить, что пользователи имеют возможность выполнять запуск от имени обычных пользователей (не администраторов) без обязательной блокировки запуска приложений и служб, которым требуются более высокие привилегии.</span><span class="sxs-lookup"><span data-stu-id="e33aa-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>  
  
 <span data-ttu-id="e33aa-108">В [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]большинство приложений предоставляется с помощью стандартного или административного токена.</span><span class="sxs-lookup"><span data-stu-id="e33aa-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="e33aa-109">Если приложение не идентифицировано как административное приложение, оно запускается в качестве стандартного приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e33aa-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="e33aa-110">Прежде чем приложение, идентифицированное как административное, может быть запущено, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] запрашивает у пользователя разрешение на запуск приложения с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="e33aa-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="e33aa-111">Запрос на продолжение отображается по умолчанию, даже если пользователь является членом локальной группы администраторов, так как администраторы выполняют запуск как обычные пользователи, пока приложение или системный компонент, которому требуются административные учетные данные, не запросит разрешение на запуск.</span><span class="sxs-lookup"><span data-stu-id="e33aa-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="e33aa-112">Задачи, требующие повышенных привилегий</span><span class="sxs-lookup"><span data-stu-id="e33aa-112">Tasks Requiring Higher Privileges</span></span>  
 <span data-ttu-id="e33aa-113">Когда пользователь пытается выполнить задачу, для которой требуются административные привилегии, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] выводит диалоговое окно с запросом на продолжение.</span><span class="sxs-lookup"><span data-stu-id="e33aa-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="e33aa-114">Это диалоговое окно защищено от межпроцессного взаимодействия, чтобы вредоносные программы не могли имитировать ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="e33aa-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="e33aa-115">Аналогичным образом экран входа в систему обычно недоступен для других процессов.</span><span class="sxs-lookup"><span data-stu-id="e33aa-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>  
  
 <span data-ttu-id="e33aa-116">Клиенты автоматизации пользовательского интерфейса должны взаимодействовать с другими процессами, а некоторые из них могут запускаться с повышенным уровнем привилегий.</span><span class="sxs-lookup"><span data-stu-id="e33aa-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="e33aa-117">Клиентам также может требоваться доступ к диалоговым окнам системы, которые обычно невидимы для других процессов.</span><span class="sxs-lookup"><span data-stu-id="e33aa-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="e33aa-118">Таким образом, клиенты [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны быть доверенными для системы и должны запускаться со специальными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="e33aa-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>  
  
 <span data-ttu-id="e33aa-119">Чтобы быть доверенными для взаимодействия с приложениями, работающими на более высоком уровне привилегий, приложения должны быть подписаны.</span><span class="sxs-lookup"><span data-stu-id="e33aa-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a><span data-ttu-id="e33aa-120">Файлы манифеста</span><span class="sxs-lookup"><span data-stu-id="e33aa-120">Manifest Files</span></span>  
 <span data-ttu-id="e33aa-121">Для получения доступа к защищенному системой [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]приложения должны быть построены с файлом манифеста, включающим специальный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e33aa-121">To gain access to the protected system [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], applications must be built with a manifest file that includes a special attribute in the manifest file.</span></span> <span data-ttu-id="e33aa-122">Этот атрибут `uiAccess` включен в тег `requestedExecutionLevel` , как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e33aa-122">This `uiAccess` attribute is included in the `requestedExecutionLevel` tag, as follows:</span></span>  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 <span data-ttu-id="e33aa-123">Значение атрибута `level` в этом коде приводится только для примера.</span><span class="sxs-lookup"><span data-stu-id="e33aa-123">The value of the `level` attribute in this code is an example only.</span></span>  
  
 <span data-ttu-id="e33aa-124">`UIAccess` имеет значение false по умолчанию; это означает, что если этот атрибут не указан или если отсутствует манифест сборки, приложение не сможет получить доступ к защищенному [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e33aa-124">`UIAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="e33aa-125">Дополнительные сведения о безопасности [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] при подписи приложений и при создании манифестов сборки см. в статье "Рекомендации и инструкции разработчику для приложений в среде с минимальными привилегиями" на веб-сайте  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span><span class="sxs-lookup"><span data-stu-id="e33aa-125">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see "Developer Best Practices and Guidelines for Applications in a Least Privileged Environment" on  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span></span>
