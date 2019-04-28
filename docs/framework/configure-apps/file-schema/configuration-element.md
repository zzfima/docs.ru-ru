---
title: Элемент <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705419"
---
# <a name="configuration-element"></a><span data-ttu-id="2980d-102">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="2980d-102">\<configuration> element</span></span>

<span data-ttu-id="2980d-103">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2980d-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="2980d-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="2980d-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2980d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2980d-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="2980d-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2980d-106">Attributes</span></span>

<span data-ttu-id="2980d-107">Нет</span><span class="sxs-lookup"><span data-stu-id="2980d-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="2980d-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="2980d-108">Parent element</span></span>

<span data-ttu-id="2980d-109">Нет</span><span class="sxs-lookup"><span data-stu-id="2980d-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="2980d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2980d-110">Child elements</span></span>

|     | <span data-ttu-id="2980d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2980d-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2980d-112">**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="2980d-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="2980d-113">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2980d-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="2980d-114">**\<Startup >** параметры схемы</span><span class="sxs-lookup"><span data-stu-id="2980d-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="2980d-115">Все элементы в схеме параметров запуска.</span><span class="sxs-lookup"><span data-stu-id="2980d-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="2980d-116">**\<Среда выполнения >** параметры схемы</span><span class="sxs-lookup"><span data-stu-id="2980d-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="2980d-117">Все элементы в схеме параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2980d-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="2980d-118">[**\<System.Runtime.Remoting >** параметры схемы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2980d-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="2980d-119">Все элементы в схеме параметров удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2980d-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="2980d-120">**\<system.Net >** параметры схемы</span><span class="sxs-lookup"><span data-stu-id="2980d-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="2980d-121">Все элементы в схеме параметров сети.</span><span class="sxs-lookup"><span data-stu-id="2980d-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="2980d-122">**\<cryptographySettings >** параметры схемы</span><span class="sxs-lookup"><span data-stu-id="2980d-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="2980d-123">Все элементы в схеме параметров криптографии.</span><span class="sxs-lookup"><span data-stu-id="2980d-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="2980d-124">**\<Конфигурация >** Схема разделов</span><span class="sxs-lookup"><span data-stu-id="2980d-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="2980d-125">Все элементы в схеме параметров раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2980d-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="2980d-126">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="2980d-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="2980d-127">Все элементы в схеме параметров трассировки и отладки.</span><span class="sxs-lookup"><span data-stu-id="2980d-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="2980d-128">[Схема параметров конфигурации ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2980d-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="2980d-129">Все элементы схемы конфигурации ASP.NET, в том числе элементы настройки веб-сайтов ASP.NET и приложений.</span><span class="sxs-lookup"><span data-stu-id="2980d-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="2980d-130">Используется в *Web.config* файлов.</span><span class="sxs-lookup"><span data-stu-id="2980d-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="2980d-131">[**\<веб-службы >** параметры схемы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2980d-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="2980d-132">Все элементы в схеме параметров веб-служб.</span><span class="sxs-lookup"><span data-stu-id="2980d-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="2980d-133">Схема веб-параметров</span><span class="sxs-lookup"><span data-stu-id="2980d-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="2980d-134">Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS.</span><span class="sxs-lookup"><span data-stu-id="2980d-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="2980d-135">Используется в *aspnet.config* файлов.</span><span class="sxs-lookup"><span data-stu-id="2980d-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2980d-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="2980d-136">Remarks</span></span>

<span data-ttu-id="2980d-137">Каждый файл конфигурации должен содержать ровно один  **\<конфигурации >** элемент.</span><span class="sxs-lookup"><span data-stu-id="2980d-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="2980d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="2980d-138">See also</span></span>

- [<span data-ttu-id="2980d-139">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2980d-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
