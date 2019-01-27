---
title: '&lt;assemblyBinding&gt; элемент для &lt;конфигурации&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083903"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="c0a54-102">\<assemblyBinding > элемент для \<configuration ></span><span class="sxs-lookup"><span data-stu-id="c0a54-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="c0a54-103">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c0a54-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="c0a54-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c0a54-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="c0a54-105">&nbsp;&nbsp;**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="c0a54-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c0a54-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0a54-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="c0a54-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c0a54-107">Attribute</span></span>

|           | <span data-ttu-id="c0a54-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0a54-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c0a54-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="c0a54-109">**xmlns**</span></span> | <span data-ttu-id="c0a54-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c0a54-110">Required attribute.</span></span><br><br><span data-ttu-id="c0a54-111">Задает пространство имен XML, необходимое для привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="c0a54-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="c0a54-112">Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="c0a54-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="c0a54-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="c0a54-113">Parent element</span></span>

|     | <span data-ttu-id="c0a54-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0a54-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c0a54-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="c0a54-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="c0a54-116">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0a54-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="c0a54-117">Дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="c0a54-117">Child element</span></span>

|     | <span data-ttu-id="c0a54-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0a54-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c0a54-119">**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="c0a54-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="c0a54-120">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="c0a54-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c0a54-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0a54-121">Remarks</span></span>

<span data-ttu-id="c0a54-122">[  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) элемент упрощает управление сборки компонентов, позволяя файлы конфигурации в файлах конфигурации приложения, чтобы включить сборку хорошо известного расположения, а не дублировать параметры конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="c0a54-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="c0a54-123"> *\*\<LinkedConfiguration >** элемент не поддерживается для приложений с манифестами side-by-side Windows.</span><span class="sxs-lookup"><span data-stu-id="c0a54-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="c0a54-124">Пример</span><span class="sxs-lookup"><span data-stu-id="c0a54-124">Example</span></span>

<span data-ttu-id="c0a54-125">Приведенный ниже показано, как включить файл конфигурации на локальном жестком диске:</span><span class="sxs-lookup"><span data-stu-id="c0a54-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c0a54-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c0a54-126">See also</span></span>

- [<span data-ttu-id="c0a54-127">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0a54-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
