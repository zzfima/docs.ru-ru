---
title: Функция BeginEnumeration (Справочник по неуправляемым API)
description: Функция BeginEnumeration Сбрасывает перечислитель до начала перечисления
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
ms.openlocfilehash: 9e467234a45ae702a5b77a5f0fa8b75d4ff03c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124134"
---
# <a name="beginenumeration-function"></a>Функция BeginEnumeration
Сбрасывает перечислитель обратно в начало перечисления.  

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
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lEnumFlags`\
окне Побитовое сочетание флагов или значений, описанных в разделе « [Примечания](#remarks) », которое управляет свойствами, входящими в перечисление.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимое сочетание флагов в `lEnumFlags` или указан недопустимый аргумент. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `BeginEnumeration` был выполнен без промежуточного вызова [`EndEnumeration`](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

Флаги, которые могут быть переданы в качестве аргумента `lEnumFlags`, определяются в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.  Можно объединить один флаг из каждой группы с любым флагом из любой другой группы. Однако флаги из одной и той же группы являются взаимоисключающими. 

**Группа 1**

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Включить свойства, которые составляют только ключ. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Включить свойства, которые являются только ссылками на объекты. |

**Группа 2**

Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Ограничьте перечисление только системными свойствами. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Включить локальные и распространенные свойства, но исключить системные свойства из перечисления. |

Для классов:

Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Ограничьте перечисление свойствами, переопределенными в определении класса. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Ограничьте перечисление свойствами, переопределенными в текущем определении класса, и новыми свойствами, определенными в классе. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Маска (а не флаг), применяемая к `lEnumFlags`ному значению для проверки того, задан ли параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничьте перечисление свойствами, которые определены или изменены в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничьте перечисление свойствами, унаследованными от базовых классов. |

Для экземпляров:

Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничьте перечисление свойствами, которые определены или изменены в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничьте перечисление свойствами, унаследованными от базовых классов. |

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
