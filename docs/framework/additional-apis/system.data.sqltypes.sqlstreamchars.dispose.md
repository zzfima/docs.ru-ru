---
title: Метод SqlStreamChars.Dispose(Boolean) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3f2180d9a1893e651f174fff6d0f073df651e712
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152567"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="98b46-102">Метод SqlStreamChars.Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="98b46-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="98b46-103">При переопределении в производном классе, освобождает ресурсы, используемые в поток.</span><span class="sxs-lookup"><span data-stu-id="98b46-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="98b46-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="98b46-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="98b46-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98b46-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="98b46-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="98b46-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="98b46-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="98b46-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="98b46-108">Значение `true` позволяет освободить как управляемые, так и неуправляемые ресурсы; значение `false` освобождает только неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="98b46-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="98b46-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="98b46-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="98b46-110">`SqlStreamChars.Dispose` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="98b46-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="98b46-111">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="98b46-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="98b46-112">Требования</span><span class="sxs-lookup"><span data-stu-id="98b46-112">Requirements</span></span>

<span data-ttu-id="98b46-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="98b46-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="98b46-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="98b46-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="98b46-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="98b46-115">**.NET Framework versions:** Available since 2.0.</span></span>