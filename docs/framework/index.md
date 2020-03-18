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
ms.openlocfilehash: d94d97cd1b519025ff360dc903558ea3656818d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181536"
---
# <a name="net-framework-guide"></a><span data-ttu-id="d8852-102">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d8852-102">.NET Framework guide</span></span>

> [!NOTE]
> <span data-ttu-id="d8852-103">Этот набор содержимого .NET Framework включает сведения для версий .NET Framework с 4.5 по 4.8.</span><span class="sxs-lookup"><span data-stu-id="d8852-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="d8852-104">Сведения о скачивании .NET Framework см. в статье [Установка .NET Framework](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-104">To download .NET Framework, see [Install .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="d8852-105">Список новых функций и изменений в .NET Framework см. в статье [Новые возможности .NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-105">For a list of new features and changes in .NET Framework, see [What's New in .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="d8852-106">Список поддерживаемых платформ см. в описании [системных требований .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="d8852-107">Сведения о более старых версиях .NET Framework см. в статье [Документации по предыдущим версиям .NET](https://docs.microsoft.com/previous-versions/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="d8852-107">For documentation about older versions of .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="d8852-108">.NET Framework — это платформа разработки для создания веб-приложений, приложений для Windows, Windows Server и Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="d8852-108">.NET Framework is a development platform for building apps for web, Windows, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="d8852-109">Она состоит из среды CLR и библиотеки классов .NET Framework, которая содержит обширный набор функциональных возможностей, а также обеспечивает поддержку многих отраслевых стандартов.</span><span class="sxs-lookup"><span data-stu-id="d8852-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="d8852-110">Платформа .NET Framework предоставляет множество служб, включая управление памятью, безопасность типов и памяти, функции безопасности, сетевые функции и развертывание приложений.</span><span class="sxs-lookup"><span data-stu-id="d8852-110">.NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="d8852-111">Она предоставляет удобные структуры данных и интерфейсы API, которые абстрагируют операционную систему Windows более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="d8852-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="d8852-112">В .NET Framework вы можете использовать различные языки программирования, включая C#, F# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d8852-112">You can use different programming languages with .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="d8852-113">Общие сведения о платформе .NET Framework для пользователей и разработчиков см. в статье [Начало работы](./get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-113">For a general introduction to .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="d8852-114">Общие сведения об архитектуре и основных возможностях платформы .NET Framework см. в статье [Обзор](./get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-114">For an introduction to the architecture and key features of .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="d8852-115">Платформу .NET Framework можно использовать с Docker и [контейнерами Windows](/virtualization/windowscontainers/about/).</span><span class="sxs-lookup"><span data-stu-id="d8852-115">.NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="d8852-116">Установка</span><span class="sxs-lookup"><span data-stu-id="d8852-116">Installation</span></span>

<span data-ttu-id="d8852-117">Платформа .NET Framework поставляется вместе с Windows, что позволяет запускать приложения .NET Framework в Windows.</span><span class="sxs-lookup"><span data-stu-id="d8852-117">.NET Framework comes with Windows, which enables you to run .NET Framework applications.</span></span> <span data-ttu-id="d8852-118">Вам может потребоваться более поздняя версия .NET Framework, чем та, которая входит в состав Windows.</span><span class="sxs-lookup"><span data-stu-id="d8852-118">You may need a later version of .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="d8852-119">Дополнительные сведения см. в статье [Установка .NET Framework в Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-119">For more information, see [Install .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="d8852-120">Сведения о том, как восстановить платформу .NET Framework, если при ее установке возникают ошибки, см. в статье [Восстановление .NET Framework](./install/repair.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-120">To learn how to repair your .NET Framework installation if you're experiencing errors during installation, see [Repair .NET Framework](./install/repair.md).</span></span>

<span data-ttu-id="d8852-121">Подробные сведения о скачивании .NET Framework см. в статье [Установка .NET Framework для разработчиков](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-121">For more detailed information on downloading .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d8852-122">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="d8852-122">In this section</span></span>

* [<span data-ttu-id="d8852-123">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="d8852-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="d8852-124">Здесь приводится описание ключевых новых возможностей и изменений в последних версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8852-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="d8852-125">Сюда включены списки устаревших типов и членов, а также руководство по переносу приложений с предыдущей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8852-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="d8852-126">Начало работы</span><span class="sxs-lookup"><span data-stu-id="d8852-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="d8852-127">Здесь содержится комплексный обзор платформы .NET Framework и ссылки на дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="d8852-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="d8852-128">Руководство по установке</span><span class="sxs-lookup"><span data-stu-id="d8852-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="d8852-129">Здесь содержатся ресурсы и рекомендации по установке и устранению неполадок .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8852-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="d8852-130">Руководство по миграции</span><span class="sxs-lookup"><span data-stu-id="d8852-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="d8852-131">Здесь содержатся ресурсы и список изменений, которые нужно учитывать при миграции приложения на новую версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8852-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="d8852-132">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="d8852-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="d8852-133">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="d8852-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="d8852-134">Инструменты</span><span class="sxs-lookup"><span data-stu-id="d8852-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="d8852-135">Инструменты, описанные в этом разделе, помогут в разработке, настройке и развертывании приложений с помощью технологий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8852-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="d8852-136">Дополнительные библиотеки классов и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="d8852-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="d8852-137">Здесь содержится документация для частных API-интерфейсов .NET Framework, используемых средствами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d8852-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8852-138">См. также</span><span class="sxs-lookup"><span data-stu-id="d8852-138">See also</span></span>

* [<span data-ttu-id="d8852-139">Библиотека классов .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d8852-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
