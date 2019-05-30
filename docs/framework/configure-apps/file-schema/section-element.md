---
title: <section> элемент
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 64556054df2689ff758f52c7e98556997a3e9d3d
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301174"
---
# <a name="section-element"></a><span data-ttu-id="ed81f-102">\<раздел > элемент</span><span class="sxs-lookup"><span data-stu-id="ed81f-102">\<section> element</span></span>

<span data-ttu-id="ed81f-103">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed81f-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="ed81f-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ed81f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ed81f-105">&nbsp;&nbsp;[ **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ed81f-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="ed81f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<раздел >**</span><span class="sxs-lookup"><span data-stu-id="ed81f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="ed81f-107">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ed81f-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ed81f-108">&nbsp;&nbsp;[ **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ed81f-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="ed81f-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="ed81f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="ed81f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<раздел >**</span><span class="sxs-lookup"><span data-stu-id="ed81f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ed81f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed81f-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="ed81f-112">Обязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed81f-112">Required attributes</span></span>

|           | <span data-ttu-id="ed81f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ed81f-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ed81f-114">**name**</span><span class="sxs-lookup"><span data-stu-id="ed81f-114">**name**</span></span>  | <span data-ttu-id="ed81f-115">Задает имя раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed81f-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="ed81f-116">**type**</span><span class="sxs-lookup"><span data-stu-id="ed81f-116">**type**</span></span>  | <span data-ttu-id="ed81f-117">Задает имя класса обработчика раздела конфигурации, изучает раздел из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed81f-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="ed81f-118">Значение типа имеет синтаксис «fully-qualified-section-handler-class-name, простое имя сборки».</span><span class="sxs-lookup"><span data-stu-id="ed81f-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="ed81f-119">Простое имя сборки — это имя корневого файла без *.dll* расширение файла.</span><span class="sxs-lookup"><span data-stu-id="ed81f-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="ed81f-120">Необязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed81f-120">Optional attributes</span></span>

<span data-ttu-id="ed81f-121">Следующие атрибуты применимы только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ed81f-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="ed81f-122">Система конфигурации пропускает эти атрибуты для других типов приложений.</span><span class="sxs-lookup"><span data-stu-id="ed81f-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="ed81f-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ed81f-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="ed81f-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="ed81f-124">**allowDefinition**</span></span> | <span data-ttu-id="ed81f-125">Указывает, какой файл конфигурации, можно использовать в разделе.</span><span class="sxs-lookup"><span data-stu-id="ed81f-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="ed81f-126">Необходимо использовать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ed81f-126">Use one of the following values:</span></span><br><br><span data-ttu-id="ed81f-127">**Везде**</span><span class="sxs-lookup"><span data-stu-id="ed81f-127">**Everywhere**</span></span><br><span data-ttu-id="ed81f-128">Разрешает использовать в любом файле конфигурации раздела.</span><span class="sxs-lookup"><span data-stu-id="ed81f-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="ed81f-129">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ed81f-129">This is the default.</span></span><br><span data-ttu-id="ed81f-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="ed81f-130">**MachineOnly**</span></span><br><span data-ttu-id="ed81f-131">Разрешает использовать только в файле конфигурации компьютера раздела (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="ed81f-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="ed81f-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="ed81f-132">**MachineToApplication**</span></span><br><span data-ttu-id="ed81f-133">Разрешает раздела для использования в файле конфигурации компьютера или файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ed81f-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="ed81f-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="ed81f-134">**allowLocation**</span></span>   | <span data-ttu-id="ed81f-135">Определяет, используется ли в разделе  **\<расположение >** элемент.</span><span class="sxs-lookup"><span data-stu-id="ed81f-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="ed81f-136">Необходимо использовать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ed81f-136">Use one of the following values:</span></span><br><br><span data-ttu-id="ed81f-137">**true**</span><span class="sxs-lookup"><span data-stu-id="ed81f-137">**true**</span></span><br><span data-ttu-id="ed81f-138">Разрешает использовать внутри раздела  **\<расположение >** элемент.</span><span class="sxs-lookup"><span data-stu-id="ed81f-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="ed81f-139">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ed81f-139">This is the default.</span></span><br><span data-ttu-id="ed81f-140">**false**</span><span class="sxs-lookup"><span data-stu-id="ed81f-140">**false**</span></span><br><span data-ttu-id="ed81f-141">Не поддерживает раздел для использования внутри  **\<расположение >** элемент.</span><span class="sxs-lookup"><span data-stu-id="ed81f-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="ed81f-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed81f-142">Parent elements</span></span>

|     | <span data-ttu-id="ed81f-143">Описание</span><span class="sxs-lookup"><span data-stu-id="ed81f-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ed81f-144"> *\*\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="ed81f-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="ed81f-145">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="ed81f-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="ed81f-146"> *\*\<sectionGroup >** элемент</span><span class="sxs-lookup"><span data-stu-id="ed81f-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="ed81f-147">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed81f-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="ed81f-148">Объект  **\<разделе >** элемент является дочерним элементом элемента либо  **\<configSections >** или  **\<sectionGroup >** , но не оба.</span><span class="sxs-lookup"><span data-stu-id="ed81f-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="ed81f-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed81f-149">Child elements</span></span>

<span data-ttu-id="ed81f-150">None</span><span class="sxs-lookup"><span data-stu-id="ed81f-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ed81f-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed81f-151">Remarks</span></span>

<span data-ttu-id="ed81f-152">По сути объявление раздела конфигурации определяет новый элемент для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed81f-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="ed81f-153">Новый элемент содержит параметры, что обработчик раздела конфигурации (то есть класс, реализующий <xref:System.Configuration.IConfigurationSectionHandler> интерфейс) считывает.</span><span class="sxs-lookup"><span data-stu-id="ed81f-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="ed81f-154">Атрибуты и дочерние элементы раздела вами зависят от обработчика раздела, используемого для чтения параметров.</span><span class="sxs-lookup"><span data-stu-id="ed81f-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="ed81f-155">Объявление обработчик раздела конфигурации в *Machine.config* файла позволяет использовать раздел конфигурации в файле конфигурации приложения на этом компьютере, если не **allowDefinition**атрибут указано иное.</span><span class="sxs-lookup"><span data-stu-id="ed81f-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="ed81f-156">Пример</span><span class="sxs-lookup"><span data-stu-id="ed81f-156">Example</span></span>

<span data-ttu-id="ed81f-157">В следующем примере показано, как определения раздела конфигурации и его параметров:</span><span class="sxs-lookup"><span data-stu-id="ed81f-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ed81f-158">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ed81f-158">Configuration file</span></span>

<span data-ttu-id="ed81f-159">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="ed81f-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed81f-160">См. также</span><span class="sxs-lookup"><span data-stu-id="ed81f-160">See also</span></span>

- [<span data-ttu-id="ed81f-161">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed81f-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
