---
title: Неподдерживаемые API в .NET Core
description: Узнайте, какие API-интерфейсы из .NET Framework всегда вызывают исключение в .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: f27aeca31226a95dacf100813762eedb56876fbd
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936970"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="142b2-103">API, которые всегда создают исключения в .NET Core</span><span class="sxs-lookup"><span data-stu-id="142b2-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="142b2-104">Следующие API всегда будут вызывать исключение <xref:System.PlatformNotSupportedException> в .NET Core на всех платформах или на их подмножестве.</span><span class="sxs-lookup"><span data-stu-id="142b2-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="142b2-105">В этой статье затронутые члены API упорядочиваются по пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="142b2-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="142b2-106">Эта статья все еще находится в процессе написания.</span><span class="sxs-lookup"><span data-stu-id="142b2-106">This article is a work-in-progress.</span></span> <span data-ttu-id="142b2-107">Это не полный список API-интерфейсов, создающих исключения в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="142b2-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="142b2-108">В этой статье не рассматриваются явные реализации интерфейса для двоичной сериализации, которые вызываются в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="142b2-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="142b2-109">Дополнительные сведения см. в разделе [Двоичная сериализация в .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="142b2-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="142b2-110">Система</span><span class="sxs-lookup"><span data-stu-id="142b2-110">System</span></span>

| <span data-ttu-id="142b2-111">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-111">Member</span></span> | <span data-ttu-id="142b2-112">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-113">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="142b2-114">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="142b2-115">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="142b2-116">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-117">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="142b2-118">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="142b2-119">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="142b2-120">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-121">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="142b2-122">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="142b2-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="142b2-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="142b2-124">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-124">Member</span></span> | <span data-ttu-id="142b2-125">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-126">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-127">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-128">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="142b2-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="142b2-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="142b2-130">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-130">Member</span></span> | <span data-ttu-id="142b2-131">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-132">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-133">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="142b2-134">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="142b2-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="142b2-135">System.Configuration</span></span>

| <span data-ttu-id="142b2-136">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-136">Member</span></span> | <span data-ttu-id="142b2-137">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="142b2-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="142b2-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="142b2-139">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="142b2-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="142b2-140">System.Console</span></span>

| <span data-ttu-id="142b2-141">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-141">Member</span></span> | <span data-ttu-id="142b2-142">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="142b2-143">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-143">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-145">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-145">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-147">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-147">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-149">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-149">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="142b2-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="142b2-151">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-152">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-153">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-154">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-154">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-155"><xref:System.Console.Title?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="142b2-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="142b2-156">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-156">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-158">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-158">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-160">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-160">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-162">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-162">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-164">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="142b2-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="142b2-165">System.Data.Common</span></span>

| <span data-ttu-id="142b2-166">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-166">Member</span></span> | <span data-ttu-id="142b2-167">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="142b2-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (вызывает <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="142b2-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="142b2-169">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="142b2-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="142b2-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="142b2-171">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-171">Member</span></span> | <span data-ttu-id="142b2-172">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="142b2-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-174">Linux</span><span class="sxs-lookup"><span data-stu-id="142b2-174">Linux</span></span> |
| <span data-ttu-id="142b2-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-176">Linux</span><span class="sxs-lookup"><span data-stu-id="142b2-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="142b2-177">macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="142b2-178">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-179">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="142b2-180">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="142b2-181">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="142b2-182">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="142b2-183">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-183">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-185">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-185">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="142b2-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="142b2-187">macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-187">macOS</span></span> |
| <span data-ttu-id="142b2-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-189">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="142b2-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="142b2-190">System.IO</span></span>

| <span data-ttu-id="142b2-191">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-191">Member</span></span> | <span data-ttu-id="142b2-192">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-193">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-194">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="142b2-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="142b2-195">System.IO.Pipes</span></span>

| <span data-ttu-id="142b2-196">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-196">Member</span></span> | <span data-ttu-id="142b2-197">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="142b2-198">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="142b2-199">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="142b2-200">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="142b2-201">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-201">Linux and macOS</span></span> |
| <span data-ttu-id="142b2-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-203">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="142b2-204">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="142b2-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="142b2-205">System.Media</span></span>

| <span data-ttu-id="142b2-206">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-206">Member</span></span> | <span data-ttu-id="142b2-207">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-208">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="142b2-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="142b2-209">System.Net</span></span>

| <span data-ttu-id="142b2-210">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-210">Member</span></span> | <span data-ttu-id="142b2-211">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="142b2-212">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="142b2-213">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-214">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-215">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-216">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-217">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-218">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-219">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-220">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-221">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-222">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="142b2-223">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-224">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-225">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-226">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-227">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-228">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="142b2-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="142b2-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="142b2-230">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-230">Member</span></span> | <span data-ttu-id="142b2-231">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="142b2-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="142b2-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="142b2-233">System.Net.Sockets</span></span>

| <span data-ttu-id="142b2-234">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-234">Member</span></span> | <span data-ttu-id="142b2-235">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="142b2-236">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="142b2-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="142b2-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="142b2-238">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-238">Member</span></span> | <span data-ttu-id="142b2-239">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-239">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="142b2-240">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="142b2-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="142b2-241">System.Reflection</span></span>

| <span data-ttu-id="142b2-242">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-242">Member</span></span> | <span data-ttu-id="142b2-243">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-243">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-244">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-245">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-246">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="142b2-247">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-248">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-249">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="142b2-250">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="142b2-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="142b2-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="142b2-252">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-252">Member</span></span> | <span data-ttu-id="142b2-253">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-253">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="142b2-254">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="142b2-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="142b2-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="142b2-256">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-256">Member</span></span> | <span data-ttu-id="142b2-257">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-257">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="142b2-258">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="142b2-259">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="142b2-260">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="142b2-261">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-262">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="142b2-263">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="142b2-264">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="142b2-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="142b2-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="142b2-266">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-266">Member</span></span> | <span data-ttu-id="142b2-267">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-267">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="142b2-268">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="142b2-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="142b2-269">System.Security</span></span>

| <span data-ttu-id="142b2-270">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-270">Member</span></span> | <span data-ttu-id="142b2-271">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-271">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="142b2-272">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="142b2-273">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-274">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="142b2-275">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="142b2-276">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="142b2-277">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="142b2-278">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="142b2-279">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="142b2-280">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="142b2-281">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="142b2-282">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="142b2-283">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="142b2-284">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="142b2-285">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="142b2-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="142b2-286">System.Security.Claims</span></span>

| <span data-ttu-id="142b2-287">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-287">Member</span></span> | <span data-ttu-id="142b2-288">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-288">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="142b2-289">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-290">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="142b2-291">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-292">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-293">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="142b2-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="142b2-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="142b2-295">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-295">Member</span></span> | <span data-ttu-id="142b2-296">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-296">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-297">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-298">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="142b2-299">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="142b2-300">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="142b2-301">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="142b2-302">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="142b2-303">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="142b2-304">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="142b2-305">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="142b2-306">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="142b2-307">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="142b2-308">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="142b2-309">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="142b2-310">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="142b2-311">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-312">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="142b2-313">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-314">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-315">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-316">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-317">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="142b2-318">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-319">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-320">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-321">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="142b2-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-322">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-323">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="142b2-324">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="142b2-325">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="142b2-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="142b2-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="142b2-327">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-327">Member</span></span> | <span data-ttu-id="142b2-328">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="142b2-329">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="142b2-330">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="142b2-331">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="142b2-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="142b2-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="142b2-333">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-333">Member</span></span> | <span data-ttu-id="142b2-334">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-335">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-336">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-337">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-337">All</span></span> |
| <span data-ttu-id="142b2-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="142b2-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="142b2-339">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="142b2-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="142b2-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="142b2-341">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-341">Member</span></span> | <span data-ttu-id="142b2-342">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-343">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="142b2-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="142b2-344">System.Security.Policy</span></span>

| <span data-ttu-id="142b2-345">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-345">Member</span></span> | <span data-ttu-id="142b2-346">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-347">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="142b2-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="142b2-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="142b2-349">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-349">Member</span></span> | <span data-ttu-id="142b2-350">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-351">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="142b2-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="142b2-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="142b2-353">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-353">Member</span></span> | <span data-ttu-id="142b2-354">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-355">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="142b2-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="142b2-356">System.Threading</span></span>

| <span data-ttu-id="142b2-357">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-357">Member</span></span> | <span data-ttu-id="142b2-358">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-359">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="142b2-360">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="142b2-361">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="142b2-362">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="142b2-363">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="142b2-364">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="142b2-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="142b2-365">System.Xml</span></span>

| <span data-ttu-id="142b2-366">Член</span><span class="sxs-lookup"><span data-stu-id="142b2-366">Member</span></span> | <span data-ttu-id="142b2-367">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="142b2-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="142b2-368">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="142b2-369">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="142b2-370">Все</span><span class="sxs-lookup"><span data-stu-id="142b2-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="142b2-371">См. также</span><span class="sxs-lookup"><span data-stu-id="142b2-371">See also</span></span>

- [<span data-ttu-id="142b2-372">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="142b2-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="142b2-373">Двоичная сериализация в .NET Core</span><span class="sxs-lookup"><span data-stu-id="142b2-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="142b2-374">Анализатор переносимости .NET</span><span class="sxs-lookup"><span data-stu-id="142b2-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
