---
title: Функция ResetSecurity (Неуправляемая справка API)
description: Функция ResetSecurity присваивает токен олицетворения текущему потоку.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ce74494455c6cc7fe382a4ea4ef2ff0c4e98c61b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174866"
---
# <a name="resetsecurity-function"></a>Функция ResetSecurity
Назначает предоставленный маркер олицетворения текущему потоку.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a>Параметры

`token`  
(в) Токен олицетворения для ассоциироваться с текущим потоком. Это значение может быть равно `null`.

## <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата `S_OK` (0).

Если функция выходит из строя, значение возврата является ненулевым кодом ошибки. Чтобы получить расширенную информацию об ошибке, позвоните в функцию [GetErrorInfo.](geterrorinfo.md)
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
