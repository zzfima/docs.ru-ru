---
title: Метод SqlStreamChars.Close (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 942ee987f1c56abe2cb1718347886dd397e7217e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634345"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="31e89-102">Метод SqlStreamChars.Close</span><span class="sxs-lookup"><span data-stu-id="31e89-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="31e89-103">Закрывает текущий поток и освобождает все системные ресурсы, связанные с потоком.</span><span class="sxs-lookup"><span data-stu-id="31e89-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="31e89-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="31e89-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="31e89-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31e89-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="31e89-106"> Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="31e89-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="31e89-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="31e89-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="31e89-108">`SqlStreamChars.Close` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="31e89-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="31e89-109">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="31e89-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="31e89-110">Требования</span><span class="sxs-lookup"><span data-stu-id="31e89-110">Requirements</span></span>

<span data-ttu-id="31e89-111">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="31e89-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="31e89-112">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="31e89-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="31e89-113">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="31e89-113">**.NET Framework versions:** Available since 2.0.</span></span>
