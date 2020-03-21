---
title: Схема конфигурации секций
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: 28f936e6fd7c9e7f6f895396df8e8b8d36ab9139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155327"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="bf959-102">Схема конфигурации секций</span><span class="sxs-lookup"><span data-stu-id="bf959-102">Configuration sections schema</span></span>

<span data-ttu-id="bf959-103">Схема секций конфигурации содержит элементы, определяющие пользовательские настройки в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf959-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="bf959-104">Для получения общей информации о файлах конфигурации и схемах [см.](index.md)</span><span class="sxs-lookup"><span data-stu-id="bf959-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="bf959-105">[**\<конфигурация>** ](configuration-element.md) 
 [\*\* \<конфигурации \*\*](configsections-element-for-configuration.md) 
>[\*\* \<четкой>\*\*](clear-element-for-configsections.md) 
 [\*\* \<удалить раздел>\*\*](remove-element-for-configsections.md) 
 [\*\* \<>\*\*](section-element.md) 
 [\*\* \<разделаГруппа>\*\*](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="bf959-105">[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<clear>**](clear-element-for-configsections.md)
[**\<remove>**](remove-element-for-configsections.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>

|     | <span data-ttu-id="bf959-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bf959-106">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bf959-107">четкая>для \*\* \<\*\* \*\* \<>configSections\*\*</span><span class="sxs-lookup"><span data-stu-id="bf959-107">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="bf959-108">Очищает все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="bf959-108">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="bf959-109">**\<ясно>**</span><span class="sxs-lookup"><span data-stu-id="bf959-109">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="bf959-110">Очищает все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="bf959-110">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="bf959-111">**\<конфигурации>**</span><span class="sxs-lookup"><span data-stu-id="bf959-111">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="bf959-112">Содержит раздел конфигурации и декларации пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bf959-112">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="bf959-113">удалить>для \*\* \<\*\* \*\* \<>конфигураций\*\*</span><span class="sxs-lookup"><span data-stu-id="bf959-113">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="bf959-114">Удаляет заранее определенный раздел или группу раздела.</span><span class="sxs-lookup"><span data-stu-id="bf959-114">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="bf959-115">раздел>для \*\* \<configSections>\*\* и \*\* \<разделгруппы>\*\* \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="bf959-115">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="bf959-116">Содержит декларацию раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf959-116">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="bf959-117">разделГруппа>для \*\* \<\*\* \*\* \<configSections>\*\*</span><span class="sxs-lookup"><span data-stu-id="bf959-117">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="bf959-118">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf959-118">Defines a namespace for configuration sections.</span></span> |
