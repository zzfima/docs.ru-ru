---
title: Схема параметров приложения
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b931b76aa09b3f62fbd799990975268af4f7293
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119219"
---
# <a name="app-settings-schema"></a><span data-ttu-id="70da9-102">Схема параметров приложения</span><span class="sxs-lookup"><span data-stu-id="70da9-102">App Settings schema</span></span>

<span data-ttu-id="70da9-103">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="70da9-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="70da9-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="70da9-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="70da9-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="70da9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="70da9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="70da9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="70da9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="70da9-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="70da9-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="70da9-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="70da9-109">Element</span></span> | <span data-ttu-id="70da9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="70da9-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="70da9-111"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="70da9-111">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="70da9-112">Содержит теги **\<add>** , **\<clear>** и **\<remove>** , управляющие параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="70da9-113">Имеет необязательный атрибут **file**.</span><span class="sxs-lookup"><span data-stu-id="70da9-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="70da9-114"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="70da9-114">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="70da9-115">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="70da9-115">Defines a setting.</span></span> <span data-ttu-id="70da9-116">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="70da9-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="70da9-117">Обязательные атрибуты — **key** и **value**.</span><span class="sxs-lookup"><span data-stu-id="70da9-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="70da9-118"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="70da9-118">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="70da9-119">Удаляет все параметры.</span><span class="sxs-lookup"><span data-stu-id="70da9-119">Clears all settings.</span></span> <span data-ttu-id="70da9-120">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="70da9-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="70da9-121">Не имеет атрибутов.</span><span class="sxs-lookup"><span data-stu-id="70da9-121">Has no attributes.</span></span> |
| [<span data-ttu-id="70da9-122"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="70da9-122">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="70da9-123">Удаляет параметр.</span><span class="sxs-lookup"><span data-stu-id="70da9-123">Removes a setting.</span></span> <span data-ttu-id="70da9-124">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="70da9-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="70da9-125">Требуется атрибут **key**.</span><span class="sxs-lookup"><span data-stu-id="70da9-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="70da9-126">Элемент \<appSettings></span><span class="sxs-lookup"><span data-stu-id="70da9-126">\<appSettings> element</span></span>

<span data-ttu-id="70da9-127">Этот элемент содержит теги **\<add>** , **\<clear>** и **\<remove>** , управляющие параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="70da9-128">Определяет необязательный атрибут для **file**.</span><span class="sxs-lookup"><span data-stu-id="70da9-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="70da9-129">Элемент \<add></span><span class="sxs-lookup"><span data-stu-id="70da9-129">\<add> element</span></span>

<span data-ttu-id="70da9-130">Добавляет пользовательский параметр приложения в виде пары "имя-значение" в коллекцию параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="70da9-131">Определяет атрибуты для **key** и **value**.</span><span class="sxs-lookup"><span data-stu-id="70da9-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="70da9-132">Элемент \<clear></span><span class="sxs-lookup"><span data-stu-id="70da9-132">\<clear> element</span></span>

<span data-ttu-id="70da9-133">Удаляет все ссылки на унаследованные пользовательские параметры приложения, разрешая только ссылки, добавленные с помощью элементов **\<add>** после элемента **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="70da9-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="70da9-134">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="70da9-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="70da9-135">Элемент \<remove></span><span class="sxs-lookup"><span data-stu-id="70da9-135">\<remove> element</span></span>

<span data-ttu-id="70da9-136">Удаляет ссылку на унаследованный пользовательский параметр приложения из коллекции параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="70da9-137">Определяет атрибут для **key**.</span><span class="sxs-lookup"><span data-stu-id="70da9-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="70da9-138">Пример</span><span class="sxs-lookup"><span data-stu-id="70da9-138">Example</span></span>

<span data-ttu-id="70da9-139">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="70da9-140">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="70da9-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="70da9-141">См. также</span><span class="sxs-lookup"><span data-stu-id="70da9-141">See also</span></span>

- [<span data-ttu-id="70da9-142">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="70da9-142">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="70da9-143">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="70da9-143">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
