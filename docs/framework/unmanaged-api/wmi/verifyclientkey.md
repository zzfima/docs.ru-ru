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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b674e959ab93cf76b84e2af41e875a50b7d115f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798186"
---
# <a name="verifyclientkey-function"></a>Функция Верификлиенткэй
Проверяет, что ключ клиента имеет верные параметры безопасности.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение равно `ERROR_SUCCESS` (0).

Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в *файле Winerror. h*.

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils. def  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
