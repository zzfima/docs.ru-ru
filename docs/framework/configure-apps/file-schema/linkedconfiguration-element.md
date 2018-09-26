---
title: '&lt;linkedConfiguration&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c5186aa94993ba551252db6fef55853b5b554789
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170825"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="f57f9-102">\<linkedConfiguration > элемент</span><span class="sxs-lookup"><span data-stu-id="f57f9-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="f57f9-103">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="f57f9-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="f57f9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f57f9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f57f9-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f57f9-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="f57f9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="f57f9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f57f9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f57f9-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="f57f9-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f57f9-108">Attribute</span></span>

|           | <span data-ttu-id="f57f9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f57f9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f57f9-110">**href**</span><span class="sxs-lookup"><span data-stu-id="f57f9-110">**href**</span></span>  | <span data-ttu-id="f57f9-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f57f9-111">Required attribute.</span></span><br><br><span data-ttu-id="f57f9-112">URL-адрес файла конфигурации для включения.</span><span class="sxs-lookup"><span data-stu-id="f57f9-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="f57f9-113">Единственным форматом, поддерживаемым для **href** атрибут `file://`.</span><span class="sxs-lookup"><span data-stu-id="f57f9-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="f57f9-114">Поддерживаются локальные файлы и файлы UNC.</span><span class="sxs-lookup"><span data-stu-id="f57f9-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f57f9-115">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="f57f9-115">Parent element</span></span>

|     | <span data-ttu-id="f57f9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f57f9-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f57f9-117">**\<assemblyBinding >** элемент</span><span class="sxs-lookup"><span data-stu-id="f57f9-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="f57f9-118">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f57f9-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f57f9-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f57f9-119">Child elements</span></span>

<span data-ttu-id="f57f9-120">Нет</span><span class="sxs-lookup"><span data-stu-id="f57f9-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f57f9-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="f57f9-121">Remarks</span></span>

<span data-ttu-id="f57f9-122">**\<LinkedConfiguration >** элемент упрощает обслуживание сборки компонентов.</span><span class="sxs-lookup"><span data-stu-id="f57f9-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="f57f9-123">Если один или несколько приложений используют сборку, которая имеет файл конфигурации, которая находится в хорошо известного расположения, можно использовать файлы конфигурации приложений, использующих сборку  **\<linkedConfiguration >** элемент для включения файла конфигурации сборки, вместо того чтобы включать сведения о конфигурации напрямую.</span><span class="sxs-lookup"><span data-stu-id="f57f9-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="f57f9-124">При обслуживании сборки компонентов, обновление общего файла конфигурации предоставляет обновленные сведения о конфигурации для всех приложений, использующих сборку.</span><span class="sxs-lookup"><span data-stu-id="f57f9-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="f57f9-125">**\<LinkedConfiguration >** элемент не поддерживается для приложений с манифестами side-by-side Windows.</span><span class="sxs-lookup"><span data-stu-id="f57f9-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="f57f9-126">Следующие правила определяют использование связанных файлов конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f57f9-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="f57f9-127">Параметры в файлах конфигурации, включенный только влияет на политику привязки загрузчика и используются только загрузчиком.</span><span class="sxs-lookup"><span data-stu-id="f57f9-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="f57f9-128">Включенные файлы конфигурации могут иметь параметры, отличные от политики привязки, но эти параметры не оказывает никакого воздействия.</span><span class="sxs-lookup"><span data-stu-id="f57f9-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="f57f9-129">Единственным форматом, поддерживаемым для `href` атрибут `file://`.</span><span class="sxs-lookup"><span data-stu-id="f57f9-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="f57f9-130">Поддерживаются локальные файлы и файлы UNC.</span><span class="sxs-lookup"><span data-stu-id="f57f9-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="f57f9-131">Не имеет ограничений на количество связанных конфигураций для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f57f9-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="f57f9-132">Все связанные файлы конфигурации объединяются в один файл, аналогично поведению `#include` директив в C/C++.</span><span class="sxs-lookup"><span data-stu-id="f57f9-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="f57f9-133">**\<LinkedConfiguration >** элемент допускается только в файлах конфигурации приложения; он игнорируется в *Machine.config*.</span><span class="sxs-lookup"><span data-stu-id="f57f9-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="f57f9-134">Циклические ссылки обнаружены и удалены.</span><span class="sxs-lookup"><span data-stu-id="f57f9-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="f57f9-135">То есть если  **\<linkedConfiguration >** элементы из ряда файлов конфигурации образуют цикл, цикл обнаруживается остановлена.</span><span class="sxs-lookup"><span data-stu-id="f57f9-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="f57f9-136">Пример</span><span class="sxs-lookup"><span data-stu-id="f57f9-136">Example</span></span>

<span data-ttu-id="f57f9-137">В следующем примере показано, как включить файл конфигурации с локального жесткого диска:</span><span class="sxs-lookup"><span data-stu-id="f57f9-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f57f9-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f57f9-138">See also</span></span>

<span data-ttu-id="f57f9-139">[**\<assemblyBinding >** элемент](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f57f9-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="f57f9-140">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f57f9-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
