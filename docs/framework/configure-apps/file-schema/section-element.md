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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7147173dc9f132fa2dd14d20526d59927a183bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115256"
---
# <a name="section-element"></a><span data-ttu-id="c5148-102">\<раздела > элемента</span><span class="sxs-lookup"><span data-stu-id="c5148-102">\<section> element</span></span>

<span data-ttu-id="c5148-103">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5148-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="c5148-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c5148-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="c5148-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c5148-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="c5148-106">раздел &nbsp;&nbsp;&nbsp;&nbsp; **\<**</span><span class="sxs-lookup"><span data-stu-id="c5148-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="c5148-107">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c5148-107">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="c5148-108">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c5148-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="c5148-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="c5148-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="c5148-110">&nbsp; **&nbsp;&nbsp;** &nbsp;&nbsp;&nbsp;\<</span><span class="sxs-lookup"><span data-stu-id="c5148-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c5148-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5148-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="c5148-112">Обязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="c5148-112">Required attributes</span></span>

|           | <span data-ttu-id="c5148-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c5148-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c5148-114">**name**</span><span class="sxs-lookup"><span data-stu-id="c5148-114">**name**</span></span>  | <span data-ttu-id="c5148-115">Задает имя раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5148-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="c5148-116">**type**</span><span class="sxs-lookup"><span data-stu-id="c5148-116">**type**</span></span>  | <span data-ttu-id="c5148-117">Указывает имя класса обработчика раздела конфигурации, считывающего раздел из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5148-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="c5148-118">Значение типа имеет синтаксис "полное имя-раздела-класса-обработчика", простое-Assembly-Name ".</span><span class="sxs-lookup"><span data-stu-id="c5148-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="c5148-119">В качестве простого имени сборки используется имя корневого файла без расширения *DLL* .</span><span class="sxs-lookup"><span data-stu-id="c5148-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="c5148-120">Необязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="c5148-120">Optional attributes</span></span>

<span data-ttu-id="c5148-121">Следующие атрибуты применимы только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c5148-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="c5148-122">Система конфигурации пропускает эти атрибуты для других типов приложений.</span><span class="sxs-lookup"><span data-stu-id="c5148-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="c5148-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c5148-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="c5148-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="c5148-124">**allowDefinition**</span></span> | <span data-ttu-id="c5148-125">Указывает файл конфигурации, в котором может использоваться раздел.</span><span class="sxs-lookup"><span data-stu-id="c5148-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="c5148-126">Необходимо использовать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="c5148-126">Use one of the following values:</span></span><br><br><span data-ttu-id="c5148-127">**Везде**</span><span class="sxs-lookup"><span data-stu-id="c5148-127">**Everywhere**</span></span><br><span data-ttu-id="c5148-128">Позволяет использовать раздел в любом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5148-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="c5148-129">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5148-129">This is the default.</span></span><br><span data-ttu-id="c5148-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="c5148-130">**MachineOnly**</span></span><br><span data-ttu-id="c5148-131">Позволяет использовать раздел только в файле конфигурации компьютера (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="c5148-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="c5148-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="c5148-132">**MachineToApplication**</span></span><br><span data-ttu-id="c5148-133">Позволяет использовать раздел в файле конфигурации компьютера или файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="c5148-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="c5148-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="c5148-134">**allowLocation**</span></span>   | <span data-ttu-id="c5148-135">Определяет, можно ли использовать раздел в элементе **\<location >** .</span><span class="sxs-lookup"><span data-stu-id="c5148-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="c5148-136">Необходимо использовать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="c5148-136">Use one of the following values:</span></span><br><br><span data-ttu-id="c5148-137">**true**</span><span class="sxs-lookup"><span data-stu-id="c5148-137">**true**</span></span><br><span data-ttu-id="c5148-138">Позволяет использовать раздел в элементе **\<расположение >** .</span><span class="sxs-lookup"><span data-stu-id="c5148-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="c5148-139">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5148-139">This is the default.</span></span><br><span data-ttu-id="c5148-140">**false**</span><span class="sxs-lookup"><span data-stu-id="c5148-140">**false**</span></span><br><span data-ttu-id="c5148-141">Не разрешает использование раздела в элементе **\<location >** .</span><span class="sxs-lookup"><span data-stu-id="c5148-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="c5148-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c5148-142">Parent elements</span></span>

|     | <span data-ttu-id="c5148-143">Описание</span><span class="sxs-lookup"><span data-stu-id="c5148-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c5148-144"> **\<configSections >** Дерев</span><span class="sxs-lookup"><span data-stu-id="c5148-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="c5148-145">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="c5148-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="c5148-146"> **\<sectionGroup >** Дерев</span><span class="sxs-lookup"><span data-stu-id="c5148-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="c5148-147">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5148-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="c5148-148">**\<раздел >** является дочерним элементом либо **\<configSections >** , либо **\<sectionGroup >** , но не оба.</span><span class="sxs-lookup"><span data-stu-id="c5148-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="c5148-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c5148-149">Child elements</span></span>

<span data-ttu-id="c5148-150">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c5148-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c5148-151">Заметки</span><span class="sxs-lookup"><span data-stu-id="c5148-151">Remarks</span></span>

<span data-ttu-id="c5148-152">Объявление раздела конфигурации фактически определяет новый элемент для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5148-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="c5148-153">Новый элемент содержит параметры, которые выполняет обработчик раздела конфигурации (то есть класс, реализующий интерфейс <xref:System.Configuration.IConfigurationSectionHandler>).</span><span class="sxs-lookup"><span data-stu-id="c5148-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="c5148-154">Атрибуты и дочерние элементы определяемого раздела зависят от обработчика раздела, используемого для чтения параметров.</span><span class="sxs-lookup"><span data-stu-id="c5148-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="c5148-155">Объявление обработчика раздела конфигурации в файле *Machine. config* позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если в атрибуте **allowDefinition** не указано иное.</span><span class="sxs-lookup"><span data-stu-id="c5148-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="c5148-156">Пример</span><span class="sxs-lookup"><span data-stu-id="c5148-156">Example</span></span>

<span data-ttu-id="c5148-157">В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c5148-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="c5148-158">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="c5148-158">Configuration file</span></span>

<span data-ttu-id="c5148-159">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="c5148-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5148-160">См. также</span><span class="sxs-lookup"><span data-stu-id="c5148-160">See also</span></span>

- [<span data-ttu-id="c5148-161">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c5148-161">Configuration file schema for the .NET Framework</span></span>](index.md)
