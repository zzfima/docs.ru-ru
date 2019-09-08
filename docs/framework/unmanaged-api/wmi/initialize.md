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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bc3688b30180bdcde0a87027955a789de749f90
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798439"
---
# <a name="initialize-function"></a><span data-ttu-id="040ba-103">Функция Initialize</span><span class="sxs-lookup"><span data-stu-id="040ba-103">Initialize function</span></span>

<span data-ttu-id="040ba-104">Инициализирует WMI.</span><span class="sxs-lookup"><span data-stu-id="040ba-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="040ba-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="040ba-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="040ba-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="040ba-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="040ba-107">окне `true` значение, чтобы указать, что вызовы QueryInterface на объекты WMI разрешены; `false` в противном случае — значение.</span><span class="sxs-lookup"><span data-stu-id="040ba-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="040ba-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="040ba-108">Return value</span></span>

<span data-ttu-id="040ba-109">Функция всегда возвращает `S_OK` значение (0).</span><span class="sxs-lookup"><span data-stu-id="040ba-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="040ba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="040ba-110">Requirements</span></span>

<span data-ttu-id="040ba-111">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="040ba-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="040ba-112">**Заголовок.** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="040ba-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="040ba-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="040ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="040ba-114">См. также</span><span class="sxs-lookup"><span data-stu-id="040ba-114">See also</span></span>

- [<span data-ttu-id="040ba-115">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="040ba-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
