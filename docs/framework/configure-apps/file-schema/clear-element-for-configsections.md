---
title: Элемент <clear> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155431"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="b32d5-102">\<четкий элемент \<> для конфигурации></span><span class="sxs-lookup"><span data-stu-id="b32d5-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="b32d5-103">Очищает все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="b32d5-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="b32d5-104">&nbsp; &nbsp; &nbsp; &nbsp; [\*\* \<конфигурация\*\*](configuration-element.md) &nbsp; &nbsp; [**>\<конфигурации>**](configsections-element-for-configuration.md) **ясной>\<**</span><span class="sxs-lookup"><span data-stu-id="b32d5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b32d5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b32d5-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="b32d5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b32d5-106">Attribute</span></span>

|           | <span data-ttu-id="b32d5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b32d5-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b32d5-108">**name**</span><span class="sxs-lookup"><span data-stu-id="b32d5-108">**name**</span></span>  | <span data-ttu-id="b32d5-109">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b32d5-109">Required attribute.</span></span><br><br><span data-ttu-id="b32d5-110">Уотек названия группы раздела или раздела для удаления.</span><span class="sxs-lookup"><span data-stu-id="b32d5-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b32d5-111">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="b32d5-111">Parent element</span></span>

|     | <span data-ttu-id="b32d5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b32d5-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b32d5-113">\*\* \<конфигурации>\*\* Элемент</span><span class="sxs-lookup"><span data-stu-id="b32d5-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="b32d5-114">Содержит раздел конфигурации и декларации пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b32d5-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b32d5-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b32d5-115">Child elements</span></span>

<span data-ttu-id="b32d5-116">None</span><span class="sxs-lookup"><span data-stu-id="b32d5-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b32d5-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="b32d5-117">Remarks</span></span>

<span data-ttu-id="b32d5-118">\*\* \<Четкое>\*\* элемент удаляет все разделы и группы разделов из приложения, которые были определены ранее в текущем файле конфигурации или на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b32d5-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="b32d5-119">Пример</span><span class="sxs-lookup"><span data-stu-id="b32d5-119">Example</span></span>

<span data-ttu-id="b32d5-120">Этот пример определяет файл конфигурации машины и файл конфигурации приложения и показывает, как использовать \*\* \<элемент четкой>\*\* в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации машины.</span><span class="sxs-lookup"><span data-stu-id="b32d5-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="b32d5-121">Следующий файл конфигурации машины код объявляет два раздела, \*\* \<sampleSection>\*\* и \*\* \<другойSampleSection>\*\*, которые читаются перед файлом конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="b32d5-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="b32d5-122">Следующий файл конфигурации приложения очищает все ранее заявленные разделы.</span><span class="sxs-lookup"><span data-stu-id="b32d5-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="b32d5-123">Приложение не может использовать или извлекать настройки ни в одном из разделов, которые были заявлены в файле конфигурации машины.</span><span class="sxs-lookup"><span data-stu-id="b32d5-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="b32d5-124">Тем не менее, он может использовать настройки из \*\* \<другогораздела>,\*\* потому что он приходит после \*\* \<четкого>\*\* элемента.</span><span class="sxs-lookup"><span data-stu-id="b32d5-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b32d5-125">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="b32d5-125">Configuration file</span></span>

<span data-ttu-id="b32d5-126">Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="b32d5-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b32d5-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b32d5-127">See also</span></span>

- [<span data-ttu-id="b32d5-128">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="b32d5-128">Configuration file schema for the .NET Framework</span></span>](index.md)
