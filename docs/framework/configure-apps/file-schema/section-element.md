---
title: '&lt;раздел&gt; элемент'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 17b44ca93efc26f4732f5fe2926f894257d8f984
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="section-element"></a><span data-ttu-id="ad027-102">\<раздел > элемент</span><span class="sxs-lookup"><span data-stu-id="ad027-102">\<section> element</span></span>

<span data-ttu-id="ad027-103">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad027-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="ad027-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ad027-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ad027-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ad027-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="ad027-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел >**</span><span class="sxs-lookup"><span data-stu-id="ad027-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="ad027-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ad027-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ad027-108">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ad027-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="ad027-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="ad027-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="ad027-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел >**</span><span class="sxs-lookup"><span data-stu-id="ad027-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ad027-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad027-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="ad027-112">Обязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad027-112">Required attributes</span></span>

|           | <span data-ttu-id="ad027-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ad027-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ad027-114">**name**</span><span class="sxs-lookup"><span data-stu-id="ad027-114">**name**</span></span>  | <span data-ttu-id="ad027-115">Задает имя раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad027-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="ad027-116">**type**</span><span class="sxs-lookup"><span data-stu-id="ad027-116">**type**</span></span>  | <span data-ttu-id="ad027-117">Задает имя класса обработчика раздела конфигурации, который считывает раздел из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad027-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="ad027-118">Значение типа имеет синтаксис «fully-qualified-section-handler-class-name простое имя сборки».</span><span class="sxs-lookup"><span data-stu-id="ad027-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="ad027-119">Простое имя сборки является имя корневого файла без *.dll* расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="ad027-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="ad027-120">Необязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad027-120">Optional attributes</span></span>

<span data-ttu-id="ad027-121">Следующие атрибуты применимы только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ad027-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="ad027-122">Система конфигурации пропускает эти атрибуты для других типов приложений.</span><span class="sxs-lookup"><span data-stu-id="ad027-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="ad027-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ad027-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="ad027-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="ad027-124">**allowDefinition**</span></span> | <span data-ttu-id="ad027-125">Указывает, какой файл конфигурации, можно использовать в разделе.</span><span class="sxs-lookup"><span data-stu-id="ad027-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="ad027-126">Необходимо использовать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ad027-126">Use one of the following values:</span></span><br><br><span data-ttu-id="ad027-127">**Everywhere**</span><span class="sxs-lookup"><span data-stu-id="ad027-127">**Everywhere**</span></span><br><span data-ttu-id="ad027-128">Разрешает раздела для использования в любом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad027-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="ad027-129">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad027-129">This is the default.</span></span><br><span data-ttu-id="ad027-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="ad027-130">**MachineOnly**</span></span><br><span data-ttu-id="ad027-131">Разрешает использовать только в файле конфигурации компьютера раздела (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="ad027-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="ad027-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="ad027-132">**MachineToApplication**</span></span><br><span data-ttu-id="ad027-133">Разрешает раздела для использования в файле конфигурации компьютера или в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ad027-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="ad027-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="ad027-134">**allowLocation**</span></span>   | <span data-ttu-id="ad027-135">Определяет, может ли использоваться в разделе  **\<расположение >** элемента.</span><span class="sxs-lookup"><span data-stu-id="ad027-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="ad027-136">Необходимо использовать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ad027-136">Use one of the following values:</span></span><br><br><span data-ttu-id="ad027-137">**true**</span><span class="sxs-lookup"><span data-stu-id="ad027-137">**true**</span></span><br><span data-ttu-id="ad027-138">Разрешает использовать внутри раздела  **\<расположение >** элемента.</span><span class="sxs-lookup"><span data-stu-id="ad027-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="ad027-139">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad027-139">This is the default.</span></span><br><span data-ttu-id="ad027-140">**false**</span><span class="sxs-lookup"><span data-stu-id="ad027-140">**false**</span></span><br><span data-ttu-id="ad027-141">Разрешает использование раздела для использования в  **\<расположение >** элемента.</span><span class="sxs-lookup"><span data-stu-id="ad027-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="ad027-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad027-142">Parent elements</span></span>

|     | <span data-ttu-id="ad027-143">Описание</span><span class="sxs-lookup"><span data-stu-id="ad027-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ad027-144">**\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="ad027-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="ad027-145">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="ad027-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="ad027-146">**\<sectionGroup >** элемент</span><span class="sxs-lookup"><span data-stu-id="ad027-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="ad027-147">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad027-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="ad027-148">Объект  **\<раздел >** элемент является дочерним элементом любого  **\<configSections >** или  **\<sectionGroup >** , но не оба.</span><span class="sxs-lookup"><span data-stu-id="ad027-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="ad027-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad027-149">Child elements</span></span>

<span data-ttu-id="ad027-150">Нет</span><span class="sxs-lookup"><span data-stu-id="ad027-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ad027-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad027-151">Remarks</span></span>

<span data-ttu-id="ad027-152">Объявление раздела конфигурации фактически определяет новый элемент для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad027-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="ad027-153">Этот элемент содержит параметры, обработчик раздела конфигурации (то есть класс, реализующий <xref:System.Configuration.IConfigurationSectionHandler> интерфейса) считывает.</span><span class="sxs-lookup"><span data-stu-id="ad027-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="ad027-154">Атрибуты и дочерние элементы, определяемые раздела зависят от обработчика раздела, используемого для чтения параметров.</span><span class="sxs-lookup"><span data-stu-id="ad027-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="ad027-155">Объявление обработчика раздела конфигурации в *Machine.config* файл позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если не **allowDefinition**указывает атрибут, в противном случае.</span><span class="sxs-lookup"><span data-stu-id="ad027-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="ad027-156">Пример</span><span class="sxs-lookup"><span data-stu-id="ad027-156">Example</span></span>

<span data-ttu-id="ad027-157">Приведенный ниже показан способ определения раздела конфигурации и его параметров.</span><span class="sxs-lookup"><span data-stu-id="ad027-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ad027-158">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ad027-158">Configuration file</span></span>

<span data-ttu-id="ad027-159">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="ad027-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad027-160">См. также</span><span class="sxs-lookup"><span data-stu-id="ad027-160">See also</span></span>

[<span data-ttu-id="ad027-161">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad027-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
