---
title: "Использование доменов приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b2dac2238ae9117d3678335748c680d594a8b5c6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-application-domains"></a><span data-ttu-id="546c1-102">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="546c1-102">Using Application Domains</span></span>
<span data-ttu-id="546c1-103">Домены приложений предоставляют изолированный модуль для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="546c1-103">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="546c1-104">Они создаются и выполняются внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="546c1-104">They are created and run inside a process.</span></span> <span data-ttu-id="546c1-105">Домены приложений обычно создаются хост-приложением среды выполнения — приложением, ответственным за загрузку среды выполнения в процесс и выполнение пользовательского кода внутри домена приложения.</span><span class="sxs-lookup"><span data-stu-id="546c1-105">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="546c1-106">Хост-приложение среды выполнения создает процесс и домен приложения по умолчанию, а также выполняет внутри него управляемый код.</span><span class="sxs-lookup"><span data-stu-id="546c1-106">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="546c1-107">Хост-приложения среды выполнения включают в себя ASP.NET, Microsoft Internet Explorer и оболочку Windows.</span><span class="sxs-lookup"><span data-stu-id="546c1-107">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
 <span data-ttu-id="546c1-108">Для большинства приложений нет необходимости создавать собственный домен приложения: хост-приложение среды выполнения создает все требуемые домены автоматически.</span><span class="sxs-lookup"><span data-stu-id="546c1-108">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="546c1-109">Но вы можете создать и настроить дополнительные домены приложений, если приложению необходимо изолировать код или использовать и выгружать библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="546c1-109">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="546c1-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="546c1-110">In This Section</span></span>  
 [<span data-ttu-id="546c1-111">Практическое руководство. Создание домена приложения</span><span class="sxs-lookup"><span data-stu-id="546c1-111">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 <span data-ttu-id="546c1-112">Описание того, как создать домен приложения программным способом.</span><span class="sxs-lookup"><span data-stu-id="546c1-112">Describes how to programmatically create an application domain.</span></span>  
  
 [<span data-ttu-id="546c1-113">Практическое руководство. Выгрузка домена приложения</span><span class="sxs-lookup"><span data-stu-id="546c1-113">How to: Unload an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 <span data-ttu-id="546c1-114">Описание того, как выгрузить домен приложения программным способом.</span><span class="sxs-lookup"><span data-stu-id="546c1-114">Describes how to programmatically unload an application domain.</span></span>  
  
 [<span data-ttu-id="546c1-115">Практическое руководство. Настройка домена приложения</span><span class="sxs-lookup"><span data-stu-id="546c1-115">How to: Configure an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 <span data-ttu-id="546c1-116">Содержит общие сведения о настройке домена приложения.</span><span class="sxs-lookup"><span data-stu-id="546c1-116">Provides an introduction to configuring an application domain.</span></span>  
  
 [<span data-ttu-id="546c1-117">Извлечение сведений о настройке из домена приложения</span><span class="sxs-lookup"><span data-stu-id="546c1-117">Retrieving Setup Information from an Application Domain</span></span>](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 <span data-ttu-id="546c1-118">Описание того, как извлечь сведения о настройке из домена приложения.</span><span class="sxs-lookup"><span data-stu-id="546c1-118">Describes how to retrieve setup information from an application domain.</span></span>  
  
 [<span data-ttu-id="546c1-119">Практическое руководство. Загрузка сборок в домен приложения</span><span class="sxs-lookup"><span data-stu-id="546c1-119">How to: Load Assemblies into an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 <span data-ttu-id="546c1-120">Описание того, как загрузить сборку в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="546c1-120">Describes how to load an assembly into an application domain.</span></span>  
  
 [<span data-ttu-id="546c1-121">Практическое руководство. Получение сведений о типах и членах из сборки</span><span class="sxs-lookup"><span data-stu-id="546c1-121">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="546c1-122">Описание того, как получить сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="546c1-122">Describes how to retrieve information about an assembly.</span></span>  
  
 [<span data-ttu-id="546c1-123">Теневое копирование сборок</span><span class="sxs-lookup"><span data-stu-id="546c1-123">Shadow Copying Assemblies</span></span>](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 <span data-ttu-id="546c1-124">Описание того, как теневое копирование позволяет обновлять сборки во время их использования и как настроить теневое копирование.</span><span class="sxs-lookup"><span data-stu-id="546c1-124">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
 [<span data-ttu-id="546c1-125">Практическое руководство. Получение уведомлений о первом этапе обработки исключений</span><span class="sxs-lookup"><span data-stu-id="546c1-125">How to: Receive First-Chance Exception Notifications</span></span>](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 <span data-ttu-id="546c1-126">Описывается, как можно получать уведомления о создании исключений до того, как среда CLR начнет искать обработчики исключений.</span><span class="sxs-lookup"><span data-stu-id="546c1-126">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 [<span data-ttu-id="546c1-127">Разрешение загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="546c1-127">Resolving Assembly Loads</span></span>](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 <span data-ttu-id="546c1-128">Содержит инструкции по использованию события <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> для разрешения сбоев загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="546c1-128">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="546c1-129">Ссылка</span><span class="sxs-lookup"><span data-stu-id="546c1-129">Reference</span></span>  
 <xref:System.AppDomain>  
 <span data-ttu-id="546c1-130">Представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="546c1-130">Represents an application domain.</span></span> <span data-ttu-id="546c1-131">Предоставляет методы для создания доменов приложений и управления ими.</span><span class="sxs-lookup"><span data-stu-id="546c1-131">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="546c1-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="546c1-132">Related Sections</span></span>  
 [<span data-ttu-id="546c1-133">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="546c1-133">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="546c1-134">Предоставляет обзор функций, которые выполняются сборками.</span><span class="sxs-lookup"><span data-stu-id="546c1-134">Provides an overview of the functions performed by assemblies.</span></span>  
  
 [<span data-ttu-id="546c1-135">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="546c1-135">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="546c1-136">Описание способов создания, подписи и установки атрибутов сборок.</span><span class="sxs-lookup"><span data-stu-id="546c1-136">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
 [<span data-ttu-id="546c1-137">Предоставление динамических методов и сборок</span><span class="sxs-lookup"><span data-stu-id="546c1-137">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="546c1-138">Описание способов создания динамических сборок.</span><span class="sxs-lookup"><span data-stu-id="546c1-138">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="546c1-139">Домены приложений</span><span class="sxs-lookup"><span data-stu-id="546c1-139">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="546c1-140">Общие сведения о доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="546c1-140">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="546c1-141">Общие сведения о классе Reflection</span><span class="sxs-lookup"><span data-stu-id="546c1-141">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="546c1-142">Использование класса **Reflection** для получения сведений о сборке.</span><span class="sxs-lookup"><span data-stu-id="546c1-142">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>

