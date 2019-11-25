---
title: <linkedConfiguration> - элемент
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087965"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="78e1c-102">\<Линкедконфигуратион > элемент</span><span class="sxs-lookup"><span data-stu-id="78e1c-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="78e1c-103">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="78e1c-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="78e1c-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78e1c-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="78e1c-105">&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="78e1c-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="78e1c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<линкедконфигуратион >**</span><span class="sxs-lookup"><span data-stu-id="78e1c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="78e1c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78e1c-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="78e1c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="78e1c-108">Attribute</span></span>

|           | <span data-ttu-id="78e1c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="78e1c-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="78e1c-110">**href**</span><span class="sxs-lookup"><span data-stu-id="78e1c-110">**href**</span></span>  | <span data-ttu-id="78e1c-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="78e1c-111">Required attribute.</span></span><br><br><span data-ttu-id="78e1c-112">URL-адрес файла конфигурации, который необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="78e1c-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="78e1c-113">Единственным форматом, поддерживаемым для атрибута **href** , является `file://`.</span><span class="sxs-lookup"><span data-stu-id="78e1c-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="78e1c-114">Поддерживаются локальные файлы и файлы в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="78e1c-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="78e1c-115">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="78e1c-115">Parent element</span></span>

|     | <span data-ttu-id="78e1c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="78e1c-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="78e1c-117"> **\<assemblyBinding >** Дерев</span><span class="sxs-lookup"><span data-stu-id="78e1c-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="78e1c-118">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="78e1c-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="78e1c-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78e1c-119">Child elements</span></span>

<span data-ttu-id="78e1c-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="78e1c-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="78e1c-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="78e1c-121">Remarks</span></span>

<span data-ttu-id="78e1c-122">Элемент **\<линкедконфигуратион >** упрощает обслуживание сборок компонентов.</span><span class="sxs-lookup"><span data-stu-id="78e1c-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="78e1c-123">Если одно или несколько приложений используют сборку с файлом конфигурации, находящимся в хорошо известном расположении, файлы конфигурации приложений, использующих эту сборку, могут использовать элемент **\<линкедконфигуратион >** для включения файла конфигурации сборки, вместо того чтобы включать сведения о конфигурации напрямую.</span><span class="sxs-lookup"><span data-stu-id="78e1c-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="78e1c-124">При обслуживании сборки компонента обновление общего файла конфигурации предоставляет обновленные сведения о конфигурации всем приложениям, которые используют сборку.</span><span class="sxs-lookup"><span data-stu-id="78e1c-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="78e1c-125">Элемент **\<линкедконфигуратион >** не поддерживается для приложений с параллельными манифестами Windows.</span><span class="sxs-lookup"><span data-stu-id="78e1c-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="78e1c-126">Следующие правила управляют использованием связанных файлов конфигурации:</span><span class="sxs-lookup"><span data-stu-id="78e1c-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="78e1c-127">Параметры в включаемых файлах конфигурации влияют только на политику привязки загрузчика и используются только загрузчиком.</span><span class="sxs-lookup"><span data-stu-id="78e1c-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="78e1c-128">Включаемые файлы конфигурации могут иметь параметры, отличные от политик привязки, но эти параметры не оказывают никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="78e1c-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="78e1c-129">Единственным форматом, поддерживаемым для атрибута `href`, является `file://`.</span><span class="sxs-lookup"><span data-stu-id="78e1c-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="78e1c-130">Поддерживаются локальные файлы и файлы в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="78e1c-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="78e1c-131">Ограничений на количество связанных конфигураций для каждого файла конфигурации не существует.</span><span class="sxs-lookup"><span data-stu-id="78e1c-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="78e1c-132">Все связанные файлы конфигурации объединяются в один файл, аналогично поведению директивы `#include` в C/C++.</span><span class="sxs-lookup"><span data-stu-id="78e1c-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="78e1c-133">Элемент **\<линкедконфигуратион >** разрешен только в файлах конфигурации приложения. он игнорируется в *файле Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="78e1c-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="78e1c-134">Обнаружены и завершаются циклические ссылки.</span><span class="sxs-lookup"><span data-stu-id="78e1c-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="78e1c-135">То есть, если **\<линкедконфигуратион >** элементы ряда файлов конфигурации формируют цикл, цикл будет обнаружен и остановлен.</span><span class="sxs-lookup"><span data-stu-id="78e1c-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="78e1c-136">Пример</span><span class="sxs-lookup"><span data-stu-id="78e1c-136">Example</span></span>

<span data-ttu-id="78e1c-137">В следующем примере показано, как включить файл конфигурации с локального жесткого диска:</span><span class="sxs-lookup"><span data-stu-id="78e1c-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="78e1c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="78e1c-138">See also</span></span>

- [<span data-ttu-id="78e1c-139"> **\<assemblyBinding >** Дерев</span><span class="sxs-lookup"><span data-stu-id="78e1c-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="78e1c-140">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78e1c-140">Configuration file schema for the .NET Framework</span></span>](index.md)
