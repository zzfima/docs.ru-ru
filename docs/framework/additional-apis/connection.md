---
title: "Класс Connection"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02303a584aca738718d3e69a0071b40690fa055a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="connection-class"></a><span data-ttu-id="09cb8-102">Класс Connection</span><span class="sxs-lookup"><span data-stu-id="09cb8-102">Connection Class</span></span>

<span data-ttu-id="09cb8-103">`Connection` Ответов сервера анализирует класс очереди запросов и конвейера запросов.</span><span class="sxs-lookup"><span data-stu-id="09cb8-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="09cb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09cb8-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="09cb8-105">`Connection` Класса является внутренним и не предназначены для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="09cb8-105">The `Connection` class is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="09cb8-106">В реальном приложении ни при каких обстоятельствах корпорация Майкрософт не поддерживает использование этого класса.</span><span class="sxs-lookup"><span data-stu-id="09cb8-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="09cb8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="09cb8-107">Requirements</span></span>

<span data-ttu-id="09cb8-108">**Пространство имен:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="09cb8-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="09cb8-109">**Сборка:** системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="09cb8-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="09cb8-110">**Версии платформы .NET framework:** доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="09cb8-110">**.NET Framework versions:** Available since 2.0.</span></span>
