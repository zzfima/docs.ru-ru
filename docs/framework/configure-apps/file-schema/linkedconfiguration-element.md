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
ms.openlocfilehash: e5c8449e72414775c40ced2c344e12d5137ac03f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546417"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="31e10-102">\<linkedConfiguration > элемент</span><span class="sxs-lookup"><span data-stu-id="31e10-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="31e10-103">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="31e10-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="31e10-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="31e10-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="31e10-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="31e10-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="31e10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="31e10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="31e10-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31e10-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="31e10-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="31e10-108">Attribute</span></span>

|           | <span data-ttu-id="31e10-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="31e10-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="31e10-110">**href**</span><span class="sxs-lookup"><span data-stu-id="31e10-110">**href**</span></span>  | <span data-ttu-id="31e10-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="31e10-111">Required attribute.</span></span><br><br><span data-ttu-id="31e10-112">URL-адрес файла конфигурации для включения.</span><span class="sxs-lookup"><span data-stu-id="31e10-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="31e10-113">Единственным форматом, поддерживаемым для **href** атрибут `file://`.</span><span class="sxs-lookup"><span data-stu-id="31e10-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="31e10-114">Поддерживаются локальные файлы и файлы UNC.</span><span class="sxs-lookup"><span data-stu-id="31e10-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="31e10-115">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="31e10-115">Parent element</span></span>

|     | <span data-ttu-id="31e10-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="31e10-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="31e10-117">**\<assemblyBinding >** элемент</span><span class="sxs-lookup"><span data-stu-id="31e10-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="31e10-118">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="31e10-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="31e10-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="31e10-119">Child elements</span></span>

<span data-ttu-id="31e10-120">Нет</span><span class="sxs-lookup"><span data-stu-id="31e10-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="31e10-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="31e10-121">Remarks</span></span>

<span data-ttu-id="31e10-122"> *\*\<LinkedConfiguration >** элемент упрощает обслуживание сборки компонентов.</span><span class="sxs-lookup"><span data-stu-id="31e10-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="31e10-123">Если один или несколько приложений используют сборку, которая имеет файл конфигурации, которая находится в хорошо известного расположения, можно использовать файлы конфигурации приложений, использующих сборку  **\<linkedConfiguration >** элемент для включения файла конфигурации сборки, вместо того чтобы включать сведения о конфигурации напрямую.</span><span class="sxs-lookup"><span data-stu-id="31e10-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="31e10-124">При обслуживании сборки компонентов, обновление общего файла конфигурации предоставляет обновленные сведения о конфигурации для всех приложений, использующих сборку.</span><span class="sxs-lookup"><span data-stu-id="31e10-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="31e10-125"> *\*\<LinkedConfiguration >** элемент не поддерживается для приложений с манифестами side-by-side Windows.</span><span class="sxs-lookup"><span data-stu-id="31e10-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="31e10-126">Следующие правила определяют использование связанных файлов конфигурации:</span><span class="sxs-lookup"><span data-stu-id="31e10-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="31e10-127">Параметры в файлах конфигурации, включенный только влияет на политику привязки загрузчика и используются только загрузчиком.</span><span class="sxs-lookup"><span data-stu-id="31e10-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="31e10-128">Включенные файлы конфигурации могут иметь параметры, отличные от политики привязки, но эти параметры не оказывает никакого воздействия.</span><span class="sxs-lookup"><span data-stu-id="31e10-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="31e10-129">Единственным форматом, поддерживаемым для `href` атрибут `file://`.</span><span class="sxs-lookup"><span data-stu-id="31e10-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="31e10-130">Поддерживаются локальные файлы и файлы UNC.</span><span class="sxs-lookup"><span data-stu-id="31e10-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="31e10-131">Не имеет ограничений на количество связанных конфигураций для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="31e10-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="31e10-132">Все связанные файлы конфигурации объединяются в один файл, аналогично поведению `#include` директив в C/C++.</span><span class="sxs-lookup"><span data-stu-id="31e10-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="31e10-133"> *\*\<LinkedConfiguration >** элемент допускается только в файлах конфигурации приложения; он игнорируется в \*Machine.config\*.</span><span class="sxs-lookup"><span data-stu-id="31e10-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="31e10-134">Циклические ссылки обнаружены и удалены.</span><span class="sxs-lookup"><span data-stu-id="31e10-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="31e10-135">То есть если  **\<linkedConfiguration >** элементы из ряда файлов конфигурации образуют цикл, цикл обнаруживается остановлена.</span><span class="sxs-lookup"><span data-stu-id="31e10-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="31e10-136">Пример</span><span class="sxs-lookup"><span data-stu-id="31e10-136">Example</span></span>

<span data-ttu-id="31e10-137">В следующем примере показано, как включить файл конфигурации с локального жесткого диска:</span><span class="sxs-lookup"><span data-stu-id="31e10-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="31e10-138">См. также</span><span class="sxs-lookup"><span data-stu-id="31e10-138">See also</span></span>

- [<span data-ttu-id="31e10-139">**\<assemblyBinding >** элемент</span><span class="sxs-lookup"><span data-stu-id="31e10-139">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="31e10-140">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="31e10-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
