---
title: Алгоритм загрузки неуправляемых библиотек (.NET Core)
description: Подробные сведения об алгоритме загрузки неуправляемых сборок в .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "72303698"
---
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="2a0a6-103">Алгоритм загрузки неуправляемых (собственных) библиотек</span><span class="sxs-lookup"><span data-stu-id="2a0a6-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="2a0a6-104">Неуправляемые библиотеки обнаруживаются и загружаются по специальному алгоритму, который состоит из нескольких этапов.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="2a0a6-105">Следующий алгоритм описывает, как загружаются собственные сборки через `PInvoke`.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="2a0a6-106">Алгоритм `PInvoke` для загрузки библиотек</span><span class="sxs-lookup"><span data-stu-id="2a0a6-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="2a0a6-107">`PInvoke` использует следующий алгоритм при попытке загрузить неуправляемую сборку.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="2a0a6-108">Определяется `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="2a0a6-109">Для неуправляемой библиотеки `active` AssemblyLoadContext получает значение, соответствующее сборке, которая определяет `PInvoke`.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="2a0a6-110">Для `active` <xref:System.Runtime.Loader.AssemblyLoadContext> выполняется попытка найти сборку в следующем порядке приоритета:</span><span class="sxs-lookup"><span data-stu-id="2a0a6-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="2a0a6-111">Проверяется кэш.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-111">Checking its cache.</span></span>

    * <span data-ttu-id="2a0a6-112">Вызывается текущий делегат <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType>, заданный функцией <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="2a0a6-113">Вызывается функция <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> в `active` AssemblyLoadContext.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="2a0a6-114">Проверяется кэш экземпляров <xref:System.AppDomain> и выполняется логика [зондирования неуправляемой (собственной) библиотеки](default-probing.md#unmanaged-native-library-probing).</span><span class="sxs-lookup"><span data-stu-id="2a0a6-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="2a0a6-115">Вызывается событие <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> для `active` AssemblyLoadContext.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>
