---
title: Загрузка зависимостей (.NET Core)
description: Общие сведения об управляемой и неуправляемой загрузке зависимостей в .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: f6b5fc1f92171b61dcab162b782ca7212c602d76
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73416657"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="7b110-103">Загрузка зависимостей в .NET Core</span><span class="sxs-lookup"><span data-stu-id="7b110-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="7b110-104">Каждое приложение .NET Core имеет некоторые зависимости.</span><span class="sxs-lookup"><span data-stu-id="7b110-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="7b110-105">Даже самое простое приложение `hello world` зависит от нескольких разделов в библиотеках классов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b110-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="7b110-106">Понимание стандартной логики загрузки сборок .NET Core поможет разобраться в типичных проблемах с развертыванием и отлаживать их.</span><span class="sxs-lookup"><span data-stu-id="7b110-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="7b110-107">В некоторых приложениях зависимости загружаются динамически в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="7b110-107">In some applications, dependencies are dynamically determined at runtime.</span></span> <span data-ttu-id="7b110-108">В таких ситуациях важно понимать, как загружаются управляемые и неуправляемые сборки.</span><span class="sxs-lookup"><span data-stu-id="7b110-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="7b110-109">Основные сведения об AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="7b110-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="7b110-110">API <xref:System.Runtime.Loader.AssemblyLoadContext> является важнейшей частью системы загрузки в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b110-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="7b110-111">Статья [Основные сведения об AssemblyLoadContext](understanding-assemblyloadcontext.md) содержит высокоуровневое описание этой системы.</span><span class="sxs-lookup"><span data-stu-id="7b110-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="7b110-112">Загрузка сведений</span><span class="sxs-lookup"><span data-stu-id="7b110-112">Loading details</span></span>

<span data-ttu-id="7b110-113">Сведения об алгоритме загрузки кратко упоминаются в нескольких статьях:</span><span class="sxs-lookup"><span data-stu-id="7b110-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="7b110-114">Алгоритм загрузки управляемых сборок</span><span class="sxs-lookup"><span data-stu-id="7b110-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="7b110-115">Алгоритм загрузки вспомогательных сборок</span><span class="sxs-lookup"><span data-stu-id="7b110-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="7b110-116">Алгоритм загрузки неуправляемых (собственных) библиотек</span><span class="sxs-lookup"><span data-stu-id="7b110-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="7b110-117">Стандартное зондирование</span><span class="sxs-lookup"><span data-stu-id="7b110-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="7b110-118">Создание приложения .NET Core с подключаемыми модулями</span><span class="sxs-lookup"><span data-stu-id="7b110-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="7b110-119">В руководстве [Создание приложения .NET Core с подключаемыми модулями](../tutorials/creating-app-with-plugin-support.md) описывается создание настраиваемого AssemblyLoadContext.</span><span class="sxs-lookup"><span data-stu-id="7b110-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="7b110-120">Он использует <xref:System.Runtime.Loader.AssemblyDependencyResolver> для разрешения зависимостей подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="7b110-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="7b110-121">Этот учебник правильно изолирует зависимости подключаемого модуля от ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="7b110-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="7b110-122">Использование и отладка сборок с возможностью выгрузки в .NET Core</span><span class="sxs-lookup"><span data-stu-id="7b110-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="7b110-123">Пошаговые инструкции см. в статье [Использование и отладка сборок с возможностью выгрузки в .NET Core](../../standard/assembly/unloadability.md).</span><span class="sxs-lookup"><span data-stu-id="7b110-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="7b110-124">В ней показано, как загрузить приложение .NET Core, выполнить и выгрузить его.</span><span class="sxs-lookup"><span data-stu-id="7b110-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="7b110-125">Также в этой статье есть рекомендации по отладке.</span><span class="sxs-lookup"><span data-stu-id="7b110-125">The article also provides debugging tips.</span></span>
