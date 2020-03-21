---
title: Наследуетот функции (Неуправляемая ссылка API)
description: Функция InheritsFrom определяет, является ли класс или экземпляр производным от определенного родительского класса.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174944"
---
# <a name="inheritsfrom-function"></a>Функция InheritsFrom
Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszAncestor`  
(в) Название класса. `wszAncestor`должны указать `LPCWSTR`на допустимый .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | Текущий объект наследует от `wszAncestor`.  |
| `WBEM_S_FALSE` | 1 | Текущий объект не `wszAncestor`наследует от . |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр `wszAncestor` равен `null`. |
  
## <a name="remarks"></a>Remarks

Эта функция обертывает вызов на [IWbemClassObject::НаследуетОт](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) метода.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
