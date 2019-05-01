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
# <a name="initialize-function"></a>Initialize-функция

Инициализирует WMI.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a>Параметры

`bAllowIManagementObjectQI`

[in] `true` для указания, что разрешены вызовы QueryInterface для объектов WMI; `false` в противном случае.

## <a name="return-value"></a>Возвращаемое значение

Функция всегда возвращает `S_OK` (0).

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** WMINet_Utils.def

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
