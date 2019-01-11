---
title: Метод SqlStreamChars.Flush (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 13c4b9424b5fc16648628e2b1022a7f1621dee88
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221366"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="bc3a8-102">Метод SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="bc3a8-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="bc3a8-103">При переопределении в производном классе очищает все буферы данного потока и вызывает запись данных буферов в базовое устройство.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="bc3a8-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="bc3a8-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="bc3a8-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc3a8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc3a8-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="bc3a8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc3a8-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="bc3a8-109">`SqlStreamChars.Flush` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bc3a8-110">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc3a8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bc3a8-111">Requirements</span></span>

<span data-ttu-id="bc3a8-112">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="bc3a8-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="bc3a8-113">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="bc3a8-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="bc3a8-114">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-114">**.NET Framework versions:** Available since 2.0.</span></span>