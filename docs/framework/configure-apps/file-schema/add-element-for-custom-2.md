---
title: <add> элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 3bbe4ad6559e324db5853b95e797f50a7b908dcb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301434"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="15599-102">\<Добавить > элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="15599-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="15599-103">Добавляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="15599-103">Adds custom application settings.</span></span> <span data-ttu-id="15599-104">Каждый  **\<Добавить >** тег содержит пару ключ значение.</span><span class="sxs-lookup"><span data-stu-id="15599-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="15599-105">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="15599-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="15599-106">&nbsp;&nbsp;[ **\<параметра sectionName >** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="15599-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="15599-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="15599-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="15599-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15599-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="15599-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15599-109">Attributes</span></span>

| <span data-ttu-id="15599-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="15599-110">Attribute</span></span> | <span data-ttu-id="15599-111">Описание</span><span class="sxs-lookup"><span data-stu-id="15599-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="15599-112">**key**</span><span class="sxs-lookup"><span data-stu-id="15599-112">**key**</span></span>   | <span data-ttu-id="15599-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="15599-113">Required attribute.</span></span><br><br><span data-ttu-id="15599-114">Указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="15599-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="15599-115">**value**</span><span class="sxs-lookup"><span data-stu-id="15599-115">**value**</span></span> | <span data-ttu-id="15599-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="15599-116">Required attribute.</span></span><br><br><span data-ttu-id="15599-117">Задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="15599-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="15599-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="15599-118">Parent element</span></span>

| <span data-ttu-id="15599-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="15599-119">Element</span></span> | <span data-ttu-id="15599-120">Описание</span><span class="sxs-lookup"><span data-stu-id="15599-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="15599-121"> *\*\<параметра sectionName >** элемент</span><span class="sxs-lookup"><span data-stu-id="15599-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="15599-122">Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="15599-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="15599-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15599-123">Child elements</span></span>

<span data-ttu-id="15599-124">Нет</span><span class="sxs-lookup"><span data-stu-id="15599-124">None</span></span>

## <a name="example"></a><span data-ttu-id="15599-125">Пример</span><span class="sxs-lookup"><span data-stu-id="15599-125">Example</span></span>

<span data-ttu-id="15599-126">В следующем примере показано, как определение настраиваемого раздела конфигурации и использование  **\<Добавить >** элемент для задания параметров в разделе:</span><span class="sxs-lookup"><span data-stu-id="15599-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="15599-127">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="15599-127">Configuration file</span></span>

<span data-ttu-id="15599-128">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="15599-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="15599-129">См. также</span><span class="sxs-lookup"><span data-stu-id="15599-129">See also</span></span>

- [<span data-ttu-id="15599-130">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="15599-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
