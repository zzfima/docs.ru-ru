---
title: Разработка служебных приложений Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: 2c7fb148b96d5ff9804bcb0bb7c842c475c0f117
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385985"
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="d2091-102">Разработка служебных приложений Windows</span><span class="sxs-lookup"><span data-stu-id="d2091-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="d2091-103">С помощью Microsoft Visual Studio или пакета SDK Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] можно легко создавать службы. Просто создайте приложение, которое устанавливается как служба.</span><span class="sxs-lookup"><span data-stu-id="d2091-103">Using Microsoft Visual Studio or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="d2091-104">Такие приложения называются службами Windows.</span><span class="sxs-lookup"><span data-stu-id="d2091-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="d2091-105">Используя компоненты платформы, можно создавать, устанавливать, запускать, останавливать и администрировать службы.</span><span class="sxs-lookup"><span data-stu-id="d2091-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d2091-106">Шаблон службы Windows для C++ не включен в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="d2091-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="d2091-107">Службу Windows можно создать с помощью управляемого кода на Visual C# или Visual Basic, который при необходимости может взаимодействовать с существующим кодом C++, или можно создать службу Windows на машинном языке C++ с помощью [мастера проектов ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="d2091-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d2091-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d2091-108">In This Section</span></span>  
 [<span data-ttu-id="d2091-109">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="d2091-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="d2091-110">Сведения о приложениях служб Windows, времени существования служб и отличиях приложений служб от распространенных типов проектов.</span><span class="sxs-lookup"><span data-stu-id="d2091-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="d2091-111">Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов</span><span class="sxs-lookup"><span data-stu-id="d2091-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="d2091-112">Пример создания службы на Visual Basic и Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d2091-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>  
  
 [<span data-ttu-id="d2091-113">Программная архитектура приложений служб</span><span class="sxs-lookup"><span data-stu-id="d2091-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="d2091-114">Описание элементов языка, используемых при создании служб.</span><span class="sxs-lookup"><span data-stu-id="d2091-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="d2091-115">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="d2091-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="d2091-116">Создание и настройка служб Windows с помощью шаблона проекта службы Windows.</span><span class="sxs-lookup"><span data-stu-id="d2091-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d2091-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d2091-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="d2091-118">Описываются основные характеристики класса <xref:System.ServiceProcess.ServiceBase>, который используется для создания служб.</span><span class="sxs-lookup"><span data-stu-id="d2091-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="d2091-119">Описываются возможности класса <xref:System.ServiceProcess.ServiceProcessInstaller>, который используется вместе с классом <xref:System.ServiceProcess.ServiceInstaller> для установки и удаления служб.</span><span class="sxs-lookup"><span data-stu-id="d2091-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="d2091-120">Описываются возможности класса <xref:System.ServiceProcess.ServiceInstaller>, который используется вместе с классом <xref:System.ServiceProcess.ServiceProcessInstaller> для установки и удаления службы.</span><span class="sxs-lookup"><span data-stu-id="d2091-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="d2091-121">Создание проектов с помощью шаблонов (NIB)</span><span class="sxs-lookup"><span data-stu-id="d2091-121">NIB Creating Projects from Templates</span></span>](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="d2091-122">Описываются типы проектов, которые используются в этом разделе, и способ их выбора.</span><span class="sxs-lookup"><span data-stu-id="d2091-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
