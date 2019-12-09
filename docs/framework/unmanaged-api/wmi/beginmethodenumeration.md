---
title: Функция Бегинмесоденумератион (Справочник по неуправляемым API)
description: Функция Бегинмесоденумератион начинает перечислить методы объекта
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: be1e86e0b760ab403cf42ac19da03f84769a85cf
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884427"
---
# <a name="beginmethodenumeration-function"></a>Функция BeginMethodEnumeration
Начинает перечисление методов, доступных для объекта.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lEnumFlags`  
окне Ноль (0) для всех методов или флаг, указывающий область перечисления. Следующие флаги определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

постоянное значение.  |{2&gt;Value&lt;2}  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Ограничьте перечисление методами, определенными в самом классе. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Ограничьте перечисление свойствами, унаследованными от базовых классов. |

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|постоянное значение.  |{2&gt;Value&lt;2}  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lEnnumFlags` не равно нулю и не является одним из указанных флагов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: бегинмесоденумератион](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) .

Этот вызов метода поддерживается, только если текущий объект является определением класса. Управление методами недоступно из [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры. Порядок, в котором перечисляются методы, гарантированно является инвариантным для заданного экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также:

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
