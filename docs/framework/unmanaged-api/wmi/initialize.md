---
title: Функция Initialize (Справочник по неуправляемым интерфейсам API)
description: Функция Initialize выполняет инициализацию WMI.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127394"
---
# <a name="initialize-function"></a><span data-ttu-id="56e7d-103">Функция Initialize</span><span class="sxs-lookup"><span data-stu-id="56e7d-103">Initialize function</span></span>

<span data-ttu-id="56e7d-104">Инициализирует WMI.</span><span class="sxs-lookup"><span data-stu-id="56e7d-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="56e7d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56e7d-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="56e7d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="56e7d-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="56e7d-107">[in] `true`, чтобы указать, что вызовы QueryInterface на объекты WMI разрешены; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="56e7d-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="56e7d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56e7d-108">Return value</span></span>

<span data-ttu-id="56e7d-109">Функция всегда возвращает `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="56e7d-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="56e7d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="56e7d-110">Requirements</span></span>

<span data-ttu-id="56e7d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56e7d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="56e7d-112">**Заголовок:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="56e7d-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="56e7d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56e7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="56e7d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="56e7d-114">See also</span></span>

- [<span data-ttu-id="56e7d-115">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="56e7d-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
