---
title: "Схема разделов конфигурации"
ms.date: 05/02/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c668cf3d2f2c0bcffda185cea01edfb9e55c6d6c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="55e33-102">Схема разделов конфигурации</span><span class="sxs-lookup"><span data-stu-id="55e33-102">Configuration sections schema</span></span>

<span data-ttu-id="55e33-103">Схема разделов конфигурации содержит элементы, определяющие пользовательские параметры в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="55e33-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="55e33-104">Общие сведения о файлах конфигурации и схемы см. в разделе [схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="55e33-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="55e33-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="55e33-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="55e33-106">[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="55e33-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="55e33-107">[**\<Очистить >**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="55e33-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="55e33-108">[**\<Удалите >**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="55e33-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="55e33-109">[**\<раздел >**](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="55e33-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="55e33-110">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="55e33-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="55e33-111">Описание</span><span class="sxs-lookup"><span data-stu-id="55e33-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="55e33-112">**\<Очистить >** для  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="55e33-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="55e33-113">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="55e33-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="55e33-114">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="55e33-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="55e33-115">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="55e33-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="55e33-116">**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="55e33-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="55e33-117">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="55e33-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="55e33-118">**\<Удалите >** для  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="55e33-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="55e33-119">Удаляет предварительно определенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="55e33-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="55e33-120">**\<раздел >** для  **\<configSections >** и  **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="55e33-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="55e33-121">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="55e33-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="55e33-122">**\<sectionGroup >** для  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="55e33-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="55e33-123">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="55e33-123">Defines a namespace for configuration sections.</span></span> |
