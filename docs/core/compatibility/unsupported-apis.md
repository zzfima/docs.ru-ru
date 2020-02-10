---
title: Неподдерживаемые API в .NET Core
titleSuffix: ''
description: Узнайте, какие API-интерфейсы из .NET Framework всегда вызывают исключение в .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: c4b94321d30cacd90d5c2ee23c258681683a6faa
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092971"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="d16db-103">API, которые всегда создают исключения в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d16db-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="d16db-104">Следующие API всегда будут вызывать исключение <xref:System.PlatformNotSupportedException> в .NET Core на всех платформах или на их подмножестве.</span><span class="sxs-lookup"><span data-stu-id="d16db-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="d16db-105">В этой статье затронутые члены API упорядочиваются по пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="d16db-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d16db-106">Эта статья все еще находится в процессе написания.</span><span class="sxs-lookup"><span data-stu-id="d16db-106">This article is a work-in-progress.</span></span> <span data-ttu-id="d16db-107">Это не полный список API-интерфейсов, создающих исключения в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d16db-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="d16db-108">В этой статье не рассматриваются явные реализации интерфейса для двоичной сериализации, которые вызываются в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d16db-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="d16db-109">Дополнительные сведения см. в разделе [Двоичная сериализация в .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="d16db-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="d16db-110">Система</span><span class="sxs-lookup"><span data-stu-id="d16db-110">System</span></span>

| <span data-ttu-id="d16db-111">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-111">Member</span></span> | <span data-ttu-id="d16db-112">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-113">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="d16db-114">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="d16db-115">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="d16db-116">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-117">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="d16db-118">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="d16db-119">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="d16db-120">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-121">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="d16db-122">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="d16db-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="d16db-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="d16db-124">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-124">Member</span></span> | <span data-ttu-id="d16db-125">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-126">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-127">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-128">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="d16db-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="d16db-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="d16db-130">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-130">Member</span></span> | <span data-ttu-id="d16db-131">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-132">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-133">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d16db-134">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="d16db-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="d16db-135">System.Configuration</span></span>

| <span data-ttu-id="d16db-136">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-136">Member</span></span> | <span data-ttu-id="d16db-137">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="d16db-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="d16db-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="d16db-139">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="d16db-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="d16db-140">System.Console</span></span>

| <span data-ttu-id="d16db-141">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-141">Member</span></span> | <span data-ttu-id="d16db-142">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="d16db-143">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-143">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-145">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-145">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-147">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-147">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-149">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-149">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="d16db-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="d16db-151">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-152">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-153">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-154">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-154">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-155"><xref:System.Console.Title?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="d16db-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="d16db-156">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-156">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-158">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-158">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-160">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-160">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-162">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-162">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-164">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="d16db-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="d16db-165">System.Data.Common</span></span>

| <span data-ttu-id="d16db-166">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-166">Member</span></span> | <span data-ttu-id="d16db-167">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="d16db-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (вызывает <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="d16db-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="d16db-169">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="d16db-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="d16db-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="d16db-171">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-171">Member</span></span> | <span data-ttu-id="d16db-172">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="d16db-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-174">Linux</span><span class="sxs-lookup"><span data-stu-id="d16db-174">Linux</span></span> |
| <span data-ttu-id="d16db-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-176">Linux</span><span class="sxs-lookup"><span data-stu-id="d16db-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="d16db-177">macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="d16db-178">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-179">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="d16db-180">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="d16db-181">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="d16db-182">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="d16db-183">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-183">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-185">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-185">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="d16db-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="d16db-187">macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-187">macOS</span></span> |
| <span data-ttu-id="d16db-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-189">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="d16db-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="d16db-190">System.IO</span></span>

| <span data-ttu-id="d16db-191">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-191">Member</span></span> | <span data-ttu-id="d16db-192">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-193">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-194">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="d16db-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="d16db-195">System.IO.Pipes</span></span>

| <span data-ttu-id="d16db-196">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-196">Member</span></span> | <span data-ttu-id="d16db-197">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="d16db-198">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="d16db-199">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="d16db-200">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="d16db-201">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-201">Linux and macOS</span></span> |
| <span data-ttu-id="d16db-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-203">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="d16db-204">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="d16db-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="d16db-205">System.Media</span></span>

| <span data-ttu-id="d16db-206">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-206">Member</span></span> | <span data-ttu-id="d16db-207">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-208">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="d16db-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="d16db-209">System.Net</span></span>

| <span data-ttu-id="d16db-210">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-210">Member</span></span> | <span data-ttu-id="d16db-211">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="d16db-212">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="d16db-213">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-214">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-215">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-216">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-217">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-218">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-219">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-220">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-221">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-222">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="d16db-223">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-224">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-225">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-226">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-227">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-228">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="d16db-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="d16db-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="d16db-230">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-230">Member</span></span> | <span data-ttu-id="d16db-231">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="d16db-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="d16db-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="d16db-233">System.Net.Sockets</span></span>

| <span data-ttu-id="d16db-234">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-234">Member</span></span> | <span data-ttu-id="d16db-235">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)?displayProperty=nameWithType> | <span data-ttu-id="d16db-236">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="d16db-237">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="d16db-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="d16db-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="d16db-239">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-239">Member</span></span> | <span data-ttu-id="d16db-240">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="d16db-241">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="d16db-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="d16db-242">System.Reflection</span></span>

| <span data-ttu-id="d16db-243">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-243">Member</span></span> | <span data-ttu-id="d16db-244">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-245">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-246">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-247">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d16db-248">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-249">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-250">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="d16db-251">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="d16db-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="d16db-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="d16db-253">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-253">Member</span></span> | <span data-ttu-id="d16db-254">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="d16db-255">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="d16db-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="d16db-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="d16db-257">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-257">Member</span></span> | <span data-ttu-id="d16db-258">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d16db-259">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="d16db-260">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="d16db-261">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="d16db-262">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-263">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="d16db-264">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="d16db-265">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="d16db-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="d16db-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="d16db-267">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-267">Member</span></span> | <span data-ttu-id="d16db-268">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="d16db-269">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="d16db-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="d16db-270">System.Security</span></span>

| <span data-ttu-id="d16db-271">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-271">Member</span></span> | <span data-ttu-id="d16db-272">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="d16db-273">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="d16db-274">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-275">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="d16db-276">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="d16db-277">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="d16db-278">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="d16db-279">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="d16db-280">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="d16db-281">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="d16db-282">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="d16db-283">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d16db-284">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="d16db-285">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="d16db-286">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="d16db-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="d16db-287">System.Security.Claims</span></span>

| <span data-ttu-id="d16db-288">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-288">Member</span></span> | <span data-ttu-id="d16db-289">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="d16db-290">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-291">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="d16db-292">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-293">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-294">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="d16db-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="d16db-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="d16db-296">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-296">Member</span></span> | <span data-ttu-id="d16db-297">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-298">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-299">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="d16db-300">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="d16db-301">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="d16db-302">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="d16db-303">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="d16db-304">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="d16db-305">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="d16db-306">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="d16db-307">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="d16db-308">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="d16db-309">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="d16db-310">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="d16db-311">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="d16db-312">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="d16db-313">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-314">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-315">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-316">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-317">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="d16db-318">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-319">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-320">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-321">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="d16db-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-322">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-323">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="d16db-324">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d16db-325">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="d16db-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="d16db-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="d16db-327">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-327">Member</span></span> | <span data-ttu-id="d16db-328">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="d16db-329">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="d16db-330">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="d16db-331">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="d16db-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="d16db-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="d16db-333">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-333">Member</span></span> | <span data-ttu-id="d16db-334">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-335">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-336">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-337">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-337">All</span></span> |
| <span data-ttu-id="d16db-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="d16db-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d16db-339">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="d16db-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="d16db-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="d16db-341">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-341">Member</span></span> | <span data-ttu-id="d16db-342">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-343">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="d16db-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="d16db-344">System.Security.Policy</span></span>

| <span data-ttu-id="d16db-345">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-345">Member</span></span> | <span data-ttu-id="d16db-346">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-347">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="d16db-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="d16db-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="d16db-349">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-349">Member</span></span> | <span data-ttu-id="d16db-350">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-351">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="d16db-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="d16db-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="d16db-353">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-353">Member</span></span> | <span data-ttu-id="d16db-354">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-355">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="d16db-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="d16db-356">System.Threading</span></span>

| <span data-ttu-id="d16db-357">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-357">Member</span></span> | <span data-ttu-id="d16db-358">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-359">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d16db-360">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="d16db-361">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="d16db-362">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="d16db-363">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="d16db-364">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="d16db-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d16db-365">System.Xml</span></span>

| <span data-ttu-id="d16db-366">Член</span><span class="sxs-lookup"><span data-stu-id="d16db-366">Member</span></span> | <span data-ttu-id="d16db-367">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="d16db-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="d16db-368">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="d16db-369">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="d16db-370">Все</span><span class="sxs-lookup"><span data-stu-id="d16db-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="d16db-371">См. также</span><span class="sxs-lookup"><span data-stu-id="d16db-371">See also</span></span>

- [<span data-ttu-id="d16db-372">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="d16db-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="d16db-373">Двоичная сериализация в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d16db-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="d16db-374">Анализатор переносимости .NET</span><span class="sxs-lookup"><span data-stu-id="d16db-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
