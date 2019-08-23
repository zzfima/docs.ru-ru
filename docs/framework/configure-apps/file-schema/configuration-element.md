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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921250"
---
# <a name="configuration-element"></a><span data-ttu-id="f5677-102">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="f5677-102">\<configuration> element</span></span>

<span data-ttu-id="f5677-103">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5677-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="f5677-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="f5677-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f5677-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5677-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="f5677-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f5677-106">Attributes</span></span>

<span data-ttu-id="f5677-107">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f5677-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="f5677-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="f5677-108">Parent element</span></span>

<span data-ttu-id="f5677-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f5677-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="f5677-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f5677-110">Child elements</span></span>

|     | <span data-ttu-id="f5677-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f5677-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f5677-112"> **\<assemblyBinding >** </span><span class="sxs-lookup"><span data-stu-id="f5677-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="f5677-113">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5677-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="f5677-114">Схема параметров > запуска  **\<** </span><span class="sxs-lookup"><span data-stu-id="f5677-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="f5677-115">Все элементы в схеме параметров запуска.</span><span class="sxs-lookup"><span data-stu-id="f5677-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="f5677-116">Схема параметров **> среды выполнения \<** </span><span class="sxs-lookup"><span data-stu-id="f5677-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="f5677-117">Все элементы в схеме параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f5677-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="f5677-118">[Схема параметров **> System. Runtime. Remoting \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5677-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="f5677-119">Все элементы в схеме параметров удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f5677-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="f5677-120">Схема параметров **System > .NET \<** </span><span class="sxs-lookup"><span data-stu-id="f5677-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="f5677-121">Все элементы в схеме параметров сети.</span><span class="sxs-lookup"><span data-stu-id="f5677-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="f5677-122">Схема параметров > криптографисеттингс  **\<** </span><span class="sxs-lookup"><span data-stu-id="f5677-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="f5677-123">Все элементы в схеме параметров шифрования.</span><span class="sxs-lookup"><span data-stu-id="f5677-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="f5677-124">Схема разделов > конфигурации  **\<** </span><span class="sxs-lookup"><span data-stu-id="f5677-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="f5677-125">Все элементы в схеме параметров раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5677-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="f5677-126">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="f5677-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="f5677-127">Все элементы в схеме параметров трассировки и отладки.</span><span class="sxs-lookup"><span data-stu-id="f5677-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="f5677-128">[Схема параметров конфигурации ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5677-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="f5677-129">Все элементы в схеме конфигурации ASP.NET, включая элементы для настройки веб-сайтов и приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f5677-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="f5677-130">Используется в файлах *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="f5677-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="f5677-131">[Схема параметров > WebService  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5677-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="f5677-132">Все элементы в схеме параметров веб-служб.</span><span class="sxs-lookup"><span data-stu-id="f5677-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="f5677-133">Схема веб-параметров</span><span class="sxs-lookup"><span data-stu-id="f5677-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="f5677-134">Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS.</span><span class="sxs-lookup"><span data-stu-id="f5677-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="f5677-135">Используется в файлах *ASPNET. config* .</span><span class="sxs-lookup"><span data-stu-id="f5677-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f5677-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5677-136">Remarks</span></span>

<span data-ttu-id="f5677-137">Каждый файл конфигурации должен содержать ровно один  **\<элемент конфигурации >** .</span><span class="sxs-lookup"><span data-stu-id="f5677-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5677-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f5677-138">See also</span></span>

- [<span data-ttu-id="f5677-139">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f5677-139">Configuration file schema for the .NET Framework</span></span>](index.md)
