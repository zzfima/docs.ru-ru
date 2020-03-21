---
title: Функция startEnumeration (Неуправляемая справка API)
description: Функция BeginEnumeration сбрасывает регистратор к началу перечисления
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176881"
---
# <a name="beginenumeration-function"></a>Функция BeginEnumeration
Сброс исчисляется пересчетом обратно в начало перечисления.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a>Параметры

`vFunc`\
(в) Этот параметр не используется.

`ptr`\
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lEnumFlags`\
(в) Биттаевая комбинация флагов или значений, описанных в разделе [Замечания,](#remarks) который контролирует свойства, включенные в перечисление.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Комбинация флагов `lEnumFlags` в является недействительным, или недействительный аргумент был указан. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй звонок `BeginEnumeration` был сделан без вмешательства вызова [`EndEnumeration`](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти доступно для начала нового перечисления. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов [iWbemClassObject::BeginEnumeration.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

Флаги, которые могут `lEnumFlags` быть переданы в качестве аргумента, определяются в файле заголовка *WbemCli.h,* или вы можете определить их как константы в коде.  Вы можете объединить один флаг из каждой группы с любым флагом из любой другой группы. Тем не менее, флаги из той же группы являются взаимоисключающими.

**Группа 1**

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Включите свойства, которые составляют только ключ. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Включите свойства, которые являются только ссылками на объекты. |

**Группа 2**

Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Ограничьте перечисление только системными свойствами. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Включите локальные и распространяемые свойства, но исключите свойства системы из перечисления. |

Для занятий:

Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Ограничьте перечисление свойствами, переопределенными в определении класса. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Ограничьте перечисление свойствами, переопределенными в определении текущего класса, и новыми свойствами, определенными в классе. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Маска (а не флаг), чтобы `lEnumFlags` применить против значения, чтобы проверить, если либо `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` установлен. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничьте перечисление свойствами, которые определены или изменены в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничьте перечисление свойствами, унаследованными от базовых классов. |

В случаях:

Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничьте перечисление свойствами, которые определены или изменены в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничьте перечисление свойствами, унаследованными от базовых классов. |

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
