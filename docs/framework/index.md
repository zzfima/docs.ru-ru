---
title: .NET Framework 4.7, 4.6 и 4.5
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 34402e74bb0cb560d213760c38ce4b936d712eb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="net-framework-guide"></a><span data-ttu-id="9dcf3-102">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9dcf3-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="9dcf3-103">Этот набор содержимого .NET Framework включает сведения для версий .NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 и 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-103">This .NET Framework content set includes information for .NET Framework versions 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, and 4.7.1.</span></span> <span data-ttu-id="9dcf3-104">Сведения о скачивании .NET Framework см. в [руководстве по установке](../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-104">To download the .NET Framework, see [Installing the .NET Framework](../../docs/framework/install/guide-for-developers.md).</span></span> <span data-ttu-id="9dcf3-105">Список новых возможностей и изменений в .NET Framework 4.5, [!INCLUDE[net_v46](../../includes/net-v46-md.md)], вспомогательных выпусках, .NET Framework 4.7 и 4.7.1 см. в разделе [Новые возможности .NET Framework](../../docs/framework/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-105">For a list of new features and changes in the NET Framework 4.5, the [!INCLUDE[net_v46](../../includes/net-v46-md.md)], their point releases, and the .NET Framework 4.7 and 4.7.1, see [What's New in the .NET Framework](../../docs/framework/whats-new/index.md).</span></span> <span data-ttu-id="9dcf3-106">Список поддерживаемых платформ см. в описании [системных требований .NET Framework](../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-106">For a list of supported platforms, see [.NET Framework System Requirements](../../docs/framework/get-started/system-requirements.md).</span></span> 

<span data-ttu-id="9dcf3-107">.NET Framework — это платформа разработки для создания приложений для Интернета, Windows, Windows Phone, Windows Server и Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-107">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="9dcf3-108">Она состоит из среды CLR и библиотеки классов .NET Framework, которая содержит обширный набор функциональных возможностей, а также обеспечивает поддержку многих отраслевых стандартов.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-108">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="9dcf3-109">Платформа .NET Framework предоставляет множество служб, включая управление памятью, безопасность типа и памяти, функции безопасности, работу с сетями и развертывание приложений.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-109">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="9dcf3-110">Она предоставляет удобные структуры данных и интерфейсы API, которые абстрагируют операционную систему Windows более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-110">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="9dcf3-111">В .NET Framework вы можете использовать различные языки программирования, включая C#, F # и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-111">You can use a variety of programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>  

<span data-ttu-id="9dcf3-112">Общие сведения о платформе .NET Framework для пользователей и разработчиков см. в разделе [Начало работы](../../docs/framework/get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-112">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](../../docs/framework/get-started/index.md).</span></span> <span data-ttu-id="9dcf3-113">См. [обзорные сведения](../../docs/framework/get-started/overview.md) об архитектуре и основных возможностях платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-113">For an introduction to the architecture and key features of the .NET Framework, see the [overview](../../docs/framework/get-started/overview.md).</span></span>  

<span data-ttu-id="9dcf3-114">Платформу .NET Framework можно использовать с Docker и [контейнерами Windows](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-114">The .NET Framework can be used with Docker and with [Windows Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span></span> <span data-ttu-id="9dcf3-115">Сведения о том, как запускать приложения в контейнерах Docker, см. в статье [Развертывание приложений .NET Framework с помощью Docker](./docker/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-115">See [Deploying .NET Framework applications with Docker](./docker/index.md) to learn how to run your applications in Docker containers.</span></span>

## <a name="installation"></a><span data-ttu-id="9dcf3-116">Установка</span><span class="sxs-lookup"><span data-stu-id="9dcf3-116">Installation</span></span>

<span data-ttu-id="9dcf3-117">Платформа .NET Framework поставляется вместе с Windows, что позволяет выполнять приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="9dcf3-118">Вам может потребоваться более поздняя версия .NET Framework, чем та, которая входит в состав Windows.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-118">You may need a later version of the .NET Framework than comes with your Windows version.</span></span> <span data-ttu-id="9dcf3-119">См. дополнительные сведения об [установке .NET Framework в Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="9dcf3-120">Статья [Восстановление .NET Framework](./install/repair.md) содержит сведения о том, как восстановить платформу .NET Framework, если при ее установке возникают ошибки.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you are experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="9dcf3-121">Сведения о скачивании .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf3-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9dcf3-122">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9dcf3-122">In This Section</span></span>

[<span data-ttu-id="9dcf3-123">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="9dcf3-123">What's New</span></span>](../../docs/framework/whats-new/index.md)  
<span data-ttu-id="9dcf3-124">Здесь приводится описание ключевых новых возможностей и изменений в последних версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="9dcf3-125">Сюда включены списки устаревших типов и членов, а также руководство по переносу приложений с предыдущей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="9dcf3-126">Начало работы</span><span class="sxs-lookup"><span data-stu-id="9dcf3-126">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
<span data-ttu-id="9dcf3-127">Здесь содержится комплексный обзор платформы .NET Framework и ссылки на дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
<span data-ttu-id="9dcf3-128">[Руководство по миграции](../../docs/framework/migration-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9dcf3-128">[Migration Guide](../../docs/framework/migration-guide/index.md) </span></span>  
<span data-ttu-id="9dcf3-129">Здесь содержатся ресурсы и список изменений, которые нужно учитывать при миграции приложения на новую версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-129">Provides resources and a list of changes you need to consider  if you're migrating your application to a new version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="9dcf3-130">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="9dcf3-130">Development Guide</span></span>](../../docs/framework/development-guide.md)  
<span data-ttu-id="9dcf3-131">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-131">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
[<span data-ttu-id="9dcf3-132">Инструменты</span><span class="sxs-lookup"><span data-stu-id="9dcf3-132">Tools</span></span>](../../docs/framework/tools/index.md)  
<span data-ttu-id="9dcf3-133">Инструменты, описанные в этом разделе, помогут в разработке, настройке и развертывании приложений с помощью технологий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-133">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>  
  
<span data-ttu-id="9dcf3-134">[Библиотека классов .NET Framework](/dotnet/api/?view=netframework-4.7.1) </span><span class="sxs-lookup"><span data-stu-id="9dcf3-134">[.NET Framework Class Library](/dotnet/api/?view=netframework-4.7.1) </span></span>  
<span data-ttu-id="9dcf3-135">Синтаксис, примеры кода и другие сведения для каждого класса, содержащегося в пространствах имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-135">Supplies syntax, code examples, and related information for each class contained in the .NET Framework namespaces.</span></span>  
  
[<span data-ttu-id="9dcf3-136">Дополнительные библиотеки классов и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="9dcf3-136">Additional Class Libraries and APIs</span></span>](../../docs/framework/additional-apis/index.md)  
<span data-ttu-id="9dcf3-137">Документация для классов, содержащихся в виде внештатных выпусков, как и для классов, используемых с определенными платформами или реализациями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dcf3-137">Provides documentation for classes contained in out-of-band (OOB) releases, as well as for classes that target specific platforms or implementations of the .NET Framework.</span></span>
