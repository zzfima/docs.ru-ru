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
# <a name="initialize-function"></a>Функция Initialize

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

окне `true` значение, чтобы указать, что вызовы QueryInterface на объекты WMI разрешены; `false` в противном случае — значение.

## <a name="return-value"></a>Возвращаемое значение

Функция всегда возвращает `S_OK` значение (0).

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. def

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
