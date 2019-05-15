---
title: Документация по .NET Framework
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d93dea42dbb854d8d52bd5cf3e54d1ce0d892d6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635529"
---
# <a name="net-framework-guide"></a><span data-ttu-id="6af89-102">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6af89-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="6af89-103">Этот набор содержимого .NET Framework включает сведения для версий .NET Framework с 4.5 по 4.8.</span><span class="sxs-lookup"><span data-stu-id="6af89-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="6af89-104">Сведения о скачивании .NET Framework см. в [руководстве по установке](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="6af89-104">To download the .NET Framework, see [Installing the .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="6af89-105">Список новых функций и изменений в .NET Framework см. в статье [Новые возможности .NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="6af89-105">For a list of new features and changes in the NET Framework, see [What's New in the .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="6af89-106">Список поддерживаемых платформ см. в описании [системных требований .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6af89-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="6af89-107">Сведения о более старых версиях .NET Framework см. в [документации по предыдущим версиям .NET](https://docs.microsoft.com/previous-versions/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="6af89-107">For documentation about older versions of the .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="6af89-108">.NET Framework — это платформа разработки для создания приложений для Интернета, Windows, Windows Phone, Windows Server и Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="6af89-108">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="6af89-109">Она состоит из среды CLR и библиотеки классов .NET Framework, которая содержит обширный набор функциональных возможностей, а также обеспечивает поддержку многих отраслевых стандартов.</span><span class="sxs-lookup"><span data-stu-id="6af89-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="6af89-110">Платформа .NET Framework предоставляет множество служб, включая управление памятью, безопасность типа и памяти, функции безопасности, работу с сетями и развертывание приложений.</span><span class="sxs-lookup"><span data-stu-id="6af89-110">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="6af89-111">Она предоставляет удобные структуры данных и интерфейсы API, которые абстрагируют операционную систему Windows более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="6af89-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="6af89-112">В .NET Framework вы можете использовать различные языки программирования, включая C#, F# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6af89-112">You can use different programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="6af89-113">Общие сведения о платформе .NET Framework для пользователей и разработчиков см. в разделе [Начало работы](./get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="6af89-113">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="6af89-114">См. [обзорные сведения](./get-started/overview.md) об архитектуре и основных возможностях платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-114">For an introduction to the architecture and key features of the .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="6af89-115">Платформу .NET Framework можно использовать с Docker и [контейнерами Windows](/virtualization/windowscontainers/about/).</span><span class="sxs-lookup"><span data-stu-id="6af89-115">The .NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="6af89-116">Установка</span><span class="sxs-lookup"><span data-stu-id="6af89-116">Installation</span></span>

<span data-ttu-id="6af89-117">Платформа .NET Framework поставляется вместе с Windows, что позволяет выполнять приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="6af89-118">Вам может потребоваться более поздняя версия .NET Framework, чем та, которая входит в состав Windows.</span><span class="sxs-lookup"><span data-stu-id="6af89-118">You may need a later version of the .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="6af89-119">См. дополнительные сведения об [установке .NET Framework в Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="6af89-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="6af89-120">Статья [Восстановление .NET Framework](./install/repair.md) содержит сведения о том, как восстановить платформу .NET Framework, если при ее установке возникают ошибки.</span><span class="sxs-lookup"><span data-stu-id="6af89-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you're experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="6af89-121">Сведения о скачивании .NET Framework см. в разделе [Установка .NET Framework для разработчиков](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="6af89-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6af89-122">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="6af89-122">In this section</span></span>

* [<span data-ttu-id="6af89-123">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="6af89-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="6af89-124">Здесь приводится описание ключевых новых возможностей и изменений в последних версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="6af89-125">Сюда включены списки устаревших типов и членов, а также руководство по переносу приложений с предыдущей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="6af89-126">Начало работы</span><span class="sxs-lookup"><span data-stu-id="6af89-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="6af89-127">Здесь содержится комплексный обзор платформы .NET Framework и ссылки на дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6af89-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="6af89-128">Руководство по установке</span><span class="sxs-lookup"><span data-stu-id="6af89-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="6af89-129">Здесь содержатся ресурсы и рекомендации по установке и устранению неполадок .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="6af89-130">Руководство по миграции</span><span class="sxs-lookup"><span data-stu-id="6af89-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="6af89-131">Здесь содержатся ресурсы и список изменений, которые нужно учитывать при миграции приложения на новую версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="6af89-132">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="6af89-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="6af89-133">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="6af89-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="6af89-134">Инструменты</span><span class="sxs-lookup"><span data-stu-id="6af89-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="6af89-135">Инструменты, описанные в этом разделе, помогут в разработке, настройке и развертывании приложений с помощью технологий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6af89-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="6af89-136">Дополнительные библиотеки классов и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6af89-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="6af89-137">Здесь содержится документация для частных API-интерфейсов .NET Framework, используемых средствами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6af89-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="6af89-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6af89-138">See also</span></span>

* [<span data-ttu-id="6af89-139">Библиотека классов .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6af89-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
