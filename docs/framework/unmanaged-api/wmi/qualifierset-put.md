---
title: Функция QualifierSet_Put (Справочник по неуправляемым API)
description: Функция QualifierSet_Put записывает именованный квалификатор и его значение.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40688a0e4273233245d00fcd927f95945a43f712
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798274"
---
# <a name="qualifierset_put-function"></a>Функция QualifierSet_Put

Записывает именованный квалификатор и значение. Новый квалификатор перезаписывает предыдущее значение с тем же именем. Если квалификатор не существует, он создается.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName`\
окне Имя записываемого описателя.

`pVal`\
окне Указатель на допустимое `VARIANT` значение, содержащее квалификатор для записи. Этот параметр не может `null`быть.

`lFlavor`\
окне Одна из следующих констант, определяющая нужные флаги квалификаторов для этого квалификатора. Значение по умолчанию `WBEM_FLAVOR_OVERRIDABLE` — (0).

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Квалификатор можно переопределить в производном классе или экземпляре. **Это значение по умолчанию.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Квалификатор распространяется в экземпляры. |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Квалификатор распространяется на производные классы. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | Квалификатор невозможно переопределить в производном классе или экземпляре. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | Квалификатор локализован. |

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Недопустимая попытка указать квалификатор **ключа** для свойства, которое не может быть ключом. Ключи задаются в определении класса для объекта и не могут быть изменены отдельно для каждого экземпляра. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | `pVal` Параметр не является допустимым типом квалификатора. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Невозможно вызвать `QualifierSet_Put` метод квалификатора, так как объект-владелец не допускает переопределения. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает вызов метода [ивбемкуалифиерсет::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) .

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
