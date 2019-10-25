---
title: Свойство Пуледстреам. NetworkStream (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847232"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="315ec-102">Пуледстреам. NetworkStream, свойство</span><span class="sxs-lookup"><span data-stu-id="315ec-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="315ec-103">Возвращает или задает сетевой поток для сокета `PooledStream`.</span><span class="sxs-lookup"><span data-stu-id="315ec-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="315ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="315ec-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="315ec-105">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="315ec-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="315ec-106">Сетевой поток для сокета `PooledStream`.</span><span class="sxs-lookup"><span data-stu-id="315ec-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="315ec-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="315ec-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="315ec-108">Свойство `PooledStream.NetworkStream` является внутренним и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="315ec-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="315ec-109">Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="315ec-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="315ec-110">Требования</span><span class="sxs-lookup"><span data-stu-id="315ec-110">Requirements</span></span>

<span data-ttu-id="315ec-111">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="315ec-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="315ec-112">**Сборка:** Система (в System. dll)</span><span class="sxs-lookup"><span data-stu-id="315ec-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="315ec-113">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="315ec-113">**.NET Framework versions:** Available since 2.0.</span></span>
