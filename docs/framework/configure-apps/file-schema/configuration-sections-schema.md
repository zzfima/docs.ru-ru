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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a17d30af9d7abc3eea6b87d5e8768ac49a7c05ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118934"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="cfd43-102">Схема разделов конфигурации</span><span class="sxs-lookup"><span data-stu-id="cfd43-102">Configuration sections schema</span></span>

<span data-ttu-id="cfd43-103">Схема разделов конфигурации содержит элементы, определяющие пользовательские параметры в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfd43-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="cfd43-104">Общие сведения о файлах конфигурации и схемах см. [в разделе Схема файла конфигурации для .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="cfd43-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="cfd43-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="cfd43-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="cfd43-106">[ **>\<configSections**](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="cfd43-106">[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="cfd43-107">[ **\<очистить >** ](clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="cfd43-107">[**\<clear>**](clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="cfd43-108">[ **\<удалить >** ](remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="cfd43-108">[**\<remove>**](remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="cfd43-109">[ **> раздел\<** ](section-element.md) </span><span class="sxs-lookup"><span data-stu-id="cfd43-109">[**\<section>**](section-element.md) </span></span>  
[<span data-ttu-id="cfd43-110"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="cfd43-110">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="cfd43-111">Описание</span><span class="sxs-lookup"><span data-stu-id="cfd43-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cfd43-112"> **\<очистить >** для **\<configSections >** </span><span class="sxs-lookup"><span data-stu-id="cfd43-112">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="cfd43-113">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="cfd43-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="cfd43-114"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="cfd43-114">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="cfd43-115">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="cfd43-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="cfd43-116"> **\<configSections >** </span><span class="sxs-lookup"><span data-stu-id="cfd43-116">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="cfd43-117">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="cfd43-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="cfd43-118"> **\<удалить >** для **\<configSections >** </span><span class="sxs-lookup"><span data-stu-id="cfd43-118">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="cfd43-119">Удаляет предопределенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="cfd43-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="cfd43-120"> **\<разделе >** **\<configSections >** и **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="cfd43-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="cfd43-121">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfd43-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="cfd43-122"> **>\<sectionGroup** для **\<configSections >** </span><span class="sxs-lookup"><span data-stu-id="cfd43-122">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="cfd43-123">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfd43-123">Defines a namespace for configuration sections.</span></span> |
