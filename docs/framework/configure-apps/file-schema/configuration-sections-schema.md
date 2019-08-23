---
title: Схема разделов конфигурации
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 120733873a7ea29303fe7f82c4c324d411532897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921209"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="17165-102">Схема разделов конфигурации</span><span class="sxs-lookup"><span data-stu-id="17165-102">Configuration sections schema</span></span>

<span data-ttu-id="17165-103">Схема разделов конфигурации содержит элементы, определяющие пользовательские параметры в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17165-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="17165-104">Общие сведения о файлах конфигурации и схемах см. [в разделе Схема файла конфигурации для .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="17165-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="17165-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="17165-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="17165-106">[ **\<> configSections**](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="17165-106">[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="17165-107">[ **\<очистить >** ](clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="17165-107">[**\<clear>**](clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="17165-108">[ **\<Удалить >** ](remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="17165-108">[**\<remove>**](remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="17165-109">[ **\<раздел >** ](section-element.md) </span><span class="sxs-lookup"><span data-stu-id="17165-109">[**\<section>**](section-element.md) </span></span>  
[<span data-ttu-id="17165-110"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="17165-110">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="17165-111">Описание</span><span class="sxs-lookup"><span data-stu-id="17165-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="17165-112">Очистка > для  **\<**  **configSections>\<** </span><span class="sxs-lookup"><span data-stu-id="17165-112">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="17165-113">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="17165-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="17165-114"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="17165-114">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="17165-115">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="17165-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="17165-116"> **\<> configSections**</span><span class="sxs-lookup"><span data-stu-id="17165-116">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="17165-117">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="17165-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="17165-118">Удаление > для  **\<**  **>configSections\<** </span><span class="sxs-lookup"><span data-stu-id="17165-118">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="17165-119">Удаляет предопределенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="17165-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="17165-120">раздел > **для >configSections\<** и  **sectionGroup\<>**  **\<** </span><span class="sxs-lookup"><span data-stu-id="17165-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="17165-121">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17165-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="17165-122">> sectionGroup для  **\<**  **configSections>\<** </span><span class="sxs-lookup"><span data-stu-id="17165-122">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="17165-123">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17165-123">Defines a namespace for configuration sections.</span></span> |
