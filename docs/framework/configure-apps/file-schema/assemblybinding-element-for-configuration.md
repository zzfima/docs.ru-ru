---
title: Элемент <assemblyBinding> для <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155483"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="a8529-102">\<сборкаСвязы> \<элемент для> конфигурации</span><span class="sxs-lookup"><span data-stu-id="a8529-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="a8529-103">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a8529-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="a8529-104">конфигурация &nbsp; &nbsp; [\*\* \<>\*\*](configuration-element.md) \*\* \<сборкиОбязательная>\*\*</span><span class="sxs-lookup"><span data-stu-id="a8529-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a8529-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8529-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="a8529-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a8529-106">Attribute</span></span>

|           | <span data-ttu-id="a8529-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a8529-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a8529-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="a8529-108">**xmlns**</span></span> | <span data-ttu-id="a8529-109">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8529-109">Required attribute.</span></span><br><br><span data-ttu-id="a8529-110">Задает пространство имен XML, необходимое для привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="a8529-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="a8529-111">Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="a8529-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="a8529-112">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="a8529-112">Parent element</span></span>

|     | <span data-ttu-id="a8529-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a8529-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a8529-114">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="a8529-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="a8529-115">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8529-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="a8529-116">Дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="a8529-116">Child element</span></span>

|     | <span data-ttu-id="a8529-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a8529-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a8529-118">**\<связаныКонфигурация>**</span><span class="sxs-lookup"><span data-stu-id="a8529-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="a8529-119">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="a8529-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a8529-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8529-120">Remarks</span></span>

<span data-ttu-id="a8529-121">[\*\* \<LinkedConfiguration>\*\*](linkedconfiguration-element.md) элемент упрощает управление сборками компонентов, позволяя файлам конфигурации приложений включать файлы конфигурации сборки в хорошо известных местах, а не дублировать настройки конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="a8529-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="a8529-122">\*\* \<Элемент linkedConfiguration>\*\* не поддерживается для приложений с windows бок о бок.</span><span class="sxs-lookup"><span data-stu-id="a8529-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="a8529-123">Пример</span><span class="sxs-lookup"><span data-stu-id="a8529-123">Example</span></span>

<span data-ttu-id="a8529-124">Ниже приводится следующий пример, как включить файл конфигурации на локальном жестком диске:</span><span class="sxs-lookup"><span data-stu-id="a8529-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a8529-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a8529-125">See also</span></span>

- [<span data-ttu-id="a8529-126">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="a8529-126">Configuration file schema for the .NET Framework</span></span>](index.md)
