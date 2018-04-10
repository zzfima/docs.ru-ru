---
title: Разработка служебных приложений Windows
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: 18
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 325e43f4b1734bc6ab8753285e5069f36b0fda51
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="05654-102">Разработка служебных приложений Windows</span><span class="sxs-lookup"><span data-stu-id="05654-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="05654-103">С помощью Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, можно легко создавать службы путем создания приложения, которое устанавливается как служба.</span><span class="sxs-lookup"><span data-stu-id="05654-103">Using Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="05654-104">Такие приложения называются службы Windows.</span><span class="sxs-lookup"><span data-stu-id="05654-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="05654-105">Используя компоненты платформы можно создавать службы, их установки и запустить, остановить и также управлять ими.</span><span class="sxs-lookup"><span data-stu-id="05654-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="05654-106">Шаблон службы Windows для C++ не было включено в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="05654-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="05654-107">Чтобы создать службу Windows, можно создать службы в управляемом коде на Visual C# или Visual Basic, который может взаимодействовать с существующим кодом C++, если это необходимо, или можно создать службу Windows на C++ с помощью [мастер проектов ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="05654-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05654-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="05654-108">In This Section</span></span>  
 [<span data-ttu-id="05654-109">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="05654-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="05654-110">Обзор приложений служб Windows, время существования службы и отличий служебного приложения от других типов проектов.</span><span class="sxs-lookup"><span data-stu-id="05654-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="05654-111">Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов</span><span class="sxs-lookup"><span data-stu-id="05654-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="05654-112">Пример создания службы в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] и Visual C#.</span><span class="sxs-lookup"><span data-stu-id="05654-112">Provides an example of creating a service in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and Visual C#.</span></span>  
  
 [<span data-ttu-id="05654-113">Программная архитектура приложений служб</span><span class="sxs-lookup"><span data-stu-id="05654-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="05654-114">Описание элементов языка, используемых при создании служб.</span><span class="sxs-lookup"><span data-stu-id="05654-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="05654-115">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="05654-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="05654-116">Описывается процесс создания и настройки служб Windows с помощью шаблона проекта службы Windows.</span><span class="sxs-lookup"><span data-stu-id="05654-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05654-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="05654-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="05654-118">Описывает основные характеристики <xref:System.ServiceProcess.ServiceBase> класс, который используется для создания служб.</span><span class="sxs-lookup"><span data-stu-id="05654-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="05654-119">Описание возможностей <xref:System.ServiceProcess.ServiceProcessInstaller> класс, который используется вместе с <xref:System.ServiceProcess.ServiceInstaller> класса для установки и удаления служб.</span><span class="sxs-lookup"><span data-stu-id="05654-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="05654-120">Описание возможностей <xref:System.ServiceProcess.ServiceInstaller> класс, который используется вместе с <xref:System.ServiceProcess.ServiceProcessInstaller> класса для установки и удаления службы.</span><span class="sxs-lookup"><span data-stu-id="05654-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="05654-121">NIB Создание проектов из шаблонов</span><span class="sxs-lookup"><span data-stu-id="05654-121">NIB Creating Projects from Templates</span></span>](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="05654-122">Описывает проекты, типы, используемые в этой главе и способ их выбора.</span><span class="sxs-lookup"><span data-stu-id="05654-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
