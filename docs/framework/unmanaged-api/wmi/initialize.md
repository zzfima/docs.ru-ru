---
title: Initialize-функция (Справочник по неуправляемым API)
description: Функцию инициализации выполняет инициализацию WMI.
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
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049301"
---
# <a name="initialize-function"></a><span data-ttu-id="a0243-103">Initialize-функция</span><span class="sxs-lookup"><span data-stu-id="a0243-103">Initialize function</span></span>

<span data-ttu-id="a0243-104">Инициализирует WMI.</span><span class="sxs-lookup"><span data-stu-id="a0243-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a0243-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0243-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="a0243-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0243-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="a0243-107">[in] `true` для указания, что разрешены вызовы QueryInterface для объектов WMI; `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="a0243-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="a0243-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0243-108">Return value</span></span>

<span data-ttu-id="a0243-109">Функция всегда возвращает `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="a0243-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="a0243-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a0243-110">Requirements</span></span>

<span data-ttu-id="a0243-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0243-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a0243-112">**Заголовок.** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="a0243-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="a0243-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0243-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a0243-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a0243-114">See also</span></span>

- [<span data-ttu-id="a0243-115">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="a0243-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
