---
title: Элемент <linkedConfiguration>
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
ms.openlocfilehash: a0b56ac66302f11c59c149197a84bb96691282a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921017"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="03715-102">\<Элемент > Линкедконфигуратион</span><span class="sxs-lookup"><span data-stu-id="03715-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="03715-103">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="03715-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="03715-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="03715-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="03715-105">&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="03715-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="03715-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Линкедконфигуратион >**</span><span class="sxs-lookup"><span data-stu-id="03715-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="03715-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03715-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="03715-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="03715-108">Attribute</span></span>

|           | <span data-ttu-id="03715-109">Описание</span><span class="sxs-lookup"><span data-stu-id="03715-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="03715-110">**href**</span><span class="sxs-lookup"><span data-stu-id="03715-110">**href**</span></span>  | <span data-ttu-id="03715-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="03715-111">Required attribute.</span></span><br><br><span data-ttu-id="03715-112">URL-адрес файла конфигурации, который необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="03715-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="03715-113">Единственным форматом, поддерживаемым для атрибута href `file://`, является.</span><span class="sxs-lookup"><span data-stu-id="03715-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="03715-114">Поддерживаются локальные файлы и файлы в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="03715-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="03715-115">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="03715-115">Parent element</span></span>

|     | <span data-ttu-id="03715-116">Описание</span><span class="sxs-lookup"><span data-stu-id="03715-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03715-117">элемент  **>\<assemblyBinding**</span><span class="sxs-lookup"><span data-stu-id="03715-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="03715-118">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="03715-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="03715-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03715-119">Child elements</span></span>

<span data-ttu-id="03715-120">None</span><span class="sxs-lookup"><span data-stu-id="03715-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="03715-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="03715-121">Remarks</span></span>

<span data-ttu-id="03715-122">Элемент > линкедконфигуратион упрощает обслуживание сборок компонентов.  **\<**</span><span class="sxs-lookup"><span data-stu-id="03715-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="03715-123">Если одно или несколько приложений используют сборку с файлом конфигурации, находящимся в известном расположении, файлы конфигурации приложений, использующих эту сборку, могут использовать  **\<элемент > линкедконфигуратион** для включения файл конфигурации сборки, а не непосредственное включение сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="03715-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="03715-124">При обслуживании сборки компонента обновление общего файла конфигурации предоставляет обновленные сведения о конфигурации всем приложениям, которые используют сборку.</span><span class="sxs-lookup"><span data-stu-id="03715-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="03715-125">Элемент **линкедконфигуратион > не поддерживается для приложений с параллельными манифестами Windows. \<**</span><span class="sxs-lookup"><span data-stu-id="03715-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="03715-126">Следующие правила управляют использованием связанных файлов конфигурации:</span><span class="sxs-lookup"><span data-stu-id="03715-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="03715-127">Параметры в включаемых файлах конфигурации влияют только на политику привязки загрузчика и используются только загрузчиком.</span><span class="sxs-lookup"><span data-stu-id="03715-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="03715-128">Включаемые файлы конфигурации могут иметь параметры, отличные от политик привязки, но эти параметры не оказывают никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="03715-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="03715-129">Единственным форматом, поддерживаемым `href` для атрибута `file://`, является.</span><span class="sxs-lookup"><span data-stu-id="03715-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="03715-130">Поддерживаются локальные файлы и файлы в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="03715-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="03715-131">Ограничений на количество связанных конфигураций для каждого файла конфигурации не существует.</span><span class="sxs-lookup"><span data-stu-id="03715-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="03715-132">Все связанные файлы конфигурации объединяются в один файл, аналогично поведению `#include` директивы в C/.C++</span><span class="sxs-lookup"><span data-stu-id="03715-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="03715-133">Элемент линкедконфигуратион > разрешен только в файлах конфигурации приложения. он игнорируется в *файле Machine. config*.  **\<**</span><span class="sxs-lookup"><span data-stu-id="03715-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="03715-134">Обнаружены и завершаются циклические ссылки.</span><span class="sxs-lookup"><span data-stu-id="03715-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="03715-135">То есть, если  **\<линкедконфигуратион >** элементы ряда файлов конфигурации формируют цикл, цикл будет обнаружен и остановлен.</span><span class="sxs-lookup"><span data-stu-id="03715-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="03715-136">Пример</span><span class="sxs-lookup"><span data-stu-id="03715-136">Example</span></span>

<span data-ttu-id="03715-137">В следующем примере показано, как включить файл конфигурации с локального жесткого диска:</span><span class="sxs-lookup"><span data-stu-id="03715-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="03715-138">См. также</span><span class="sxs-lookup"><span data-stu-id="03715-138">See also</span></span>

- [<span data-ttu-id="03715-139">элемент  **>\<assemblyBinding**</span><span class="sxs-lookup"><span data-stu-id="03715-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="03715-140">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="03715-140">Configuration file schema for the .NET Framework</span></span>](index.md)
