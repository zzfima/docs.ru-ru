---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153738"
---
# <a name="section-element"></a><span data-ttu-id="7b8b7-102">\<раздел> элемент</span><span class="sxs-lookup"><span data-stu-id="7b8b7-102">\<section> element</span></span>

<span data-ttu-id="7b8b7-103">Содержит декларацию раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="7b8b7-104">[**\<конфигурация>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="7b8b7-105">&nbsp;&nbsp;[**\<конфигурации>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="7b8b7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел>**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="7b8b7-107">[**\<конфигурация>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="7b8b7-108">&nbsp;&nbsp;[**\<конфигурации>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="7b8b7-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<разделГруппа>**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="7b8b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел>**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7b8b7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b8b7-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="7b8b7-112">Требуемые атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b8b7-112">Required attributes</span></span>

|           | <span data-ttu-id="7b8b7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7b8b7-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7b8b7-114">**name**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-114">**name**</span></span>  | <span data-ttu-id="7b8b7-115">Упогоняет название раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="7b8b7-116">**тип**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-116">**type**</span></span>  | <span data-ttu-id="7b8b7-117">Упогоняет название класса обработчика раздела конфигурации, который читает раздел из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="7b8b7-118">Значение типа имеет синтаксис "полностью квалифицированный раздел-обработчик-класс-имя, просто-сборка-имя".</span><span class="sxs-lookup"><span data-stu-id="7b8b7-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="7b8b7-119">Простое имя сборки — это корневое имя файла без расширения файла *.dll.*</span><span class="sxs-lookup"><span data-stu-id="7b8b7-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="7b8b7-120">Дополнительные атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b8b7-120">Optional attributes</span></span>

<span data-ttu-id="7b8b7-121">Следующие атрибуты применимы только для ASP.NET приложений.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="7b8b7-122">Система конфигурации игнорирует эти атрибуты для других типов приложений.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="7b8b7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7b8b7-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="7b8b7-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-124">**allowDefinition**</span></span> | <span data-ttu-id="7b8b7-125">Определяет, в какой конфигурации можно использовать файл раздела.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="7b8b7-126">Используйте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7b8b7-126">Use one of the following values:</span></span><br><br><span data-ttu-id="7b8b7-127">**Везде**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-127">**Everywhere**</span></span><br><span data-ttu-id="7b8b7-128">Позволяет использовать раздел в любом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="7b8b7-129">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-129">This is the default.</span></span><br><span data-ttu-id="7b8b7-130">**МашинаТолько**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-130">**MachineOnly**</span></span><br><span data-ttu-id="7b8b7-131">Позволяет использовать раздел только в файле конфигурации машины *(Machine.config).*</span><span class="sxs-lookup"><span data-stu-id="7b8b7-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="7b8b7-132">**Машинное применение**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-132">**MachineToApplication**</span></span><br><span data-ttu-id="7b8b7-133">Позволяет использовать раздел в файле конфигурации машины или файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="7b8b7-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-134">**allowLocation**</span></span>   | <span data-ttu-id="7b8b7-135">Определяет, можно ли использовать раздел в \*\* \<пределах элемента>местоположения.\*\*</span><span class="sxs-lookup"><span data-stu-id="7b8b7-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="7b8b7-136">Используйте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7b8b7-136">Use one of the following values:</span></span><br><br><span data-ttu-id="7b8b7-137">**true**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-137">**true**</span></span><br><span data-ttu-id="7b8b7-138">Позволяет использовать раздел в \*\* \<пределах элемента>местоположения.\*\*</span><span class="sxs-lookup"><span data-stu-id="7b8b7-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="7b8b7-139">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-139">This is the default.</span></span><br><span data-ttu-id="7b8b7-140">**false**</span><span class="sxs-lookup"><span data-stu-id="7b8b7-140">**false**</span></span><br><span data-ttu-id="7b8b7-141">Не позволяет использовать раздел в \*\* \<элементе>местоположения.\*\*</span><span class="sxs-lookup"><span data-stu-id="7b8b7-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="7b8b7-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b8b7-142">Parent elements</span></span>

|     | <span data-ttu-id="7b8b7-143">Описание</span><span class="sxs-lookup"><span data-stu-id="7b8b7-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7b8b7-144">\*\* \<конфигурации>\*\* Элемент</span><span class="sxs-lookup"><span data-stu-id="7b8b7-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="7b8b7-145">Содержит раздел конфигурации и декларации пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="7b8b7-146">\*\* \<разделГруппа>\*\* Элемент</span><span class="sxs-lookup"><span data-stu-id="7b8b7-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="7b8b7-147">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="7b8b7-148">\*\* \<Раздел>\*\* элемент является элементом ребенка либо \*\* \<configSections>\*\* или \*\* \<разделаГруппа>\*\* но не оба.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="7b8b7-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b8b7-149">Child elements</span></span>

<span data-ttu-id="7b8b7-150">None</span><span class="sxs-lookup"><span data-stu-id="7b8b7-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="7b8b7-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b8b7-151">Remarks</span></span>

<span data-ttu-id="7b8b7-152">Объявление раздела конфигурации по существу определяет новый элемент для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="7b8b7-153">Новый элемент содержит настройки, которые читает обработчик раздела <xref:System.Configuration.IConfigurationSectionHandler> конфигурации (т.е. класс, реализующий интерфейс).</span><span class="sxs-lookup"><span data-stu-id="7b8b7-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="7b8b7-154">Атрибуты и элементы ребенка в определенном разделе зависят от обработчика раздела, который вы используете для чтения настроек.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="7b8b7-155">Объявление обработчика раздела конфигурации в файле *Machine.config* позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если атрибут **allowDefinition** не указывает обратное.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="7b8b7-156">Пример</span><span class="sxs-lookup"><span data-stu-id="7b8b7-156">Example</span></span>

<span data-ttu-id="7b8b7-157">В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела:</span><span class="sxs-lookup"><span data-stu-id="7b8b7-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="7b8b7-158">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="7b8b7-158">Configuration file</span></span>

<span data-ttu-id="7b8b7-159">Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b8b7-160">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7b8b7-160">See also</span></span>

- [<span data-ttu-id="7b8b7-161">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="7b8b7-161">Configuration file schema for the .NET Framework</span></span>](index.md)
