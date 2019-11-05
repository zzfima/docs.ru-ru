---
title: Функция Верификлиенткэй (Справочник по неуправляемым API)
description: Функция Верификлиенткэй обеспечивает правильную защиту ключа клиента.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0a0680651eb192e2798ede00048599c5130e63f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107359"
---
# <a name="verifyclientkey-function"></a>Функция Верификлиенткэй
Проверяет, что ключ клиента имеет верные параметры безопасности.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Возвращаемое значение

Если функция выполнена удачно, возвращается значение `ERROR_SUCCESS` (0).

Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в *файле Winerror. h*.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. def  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
