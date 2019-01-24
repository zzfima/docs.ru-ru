---
title: Функция VerifyClientKey (Справочник по неуправляемым API)
description: Функция VerifyClientKey гарантирует, что ключ клиента имеет неправильные параметры безопасности.
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
ms.openlocfilehash: 94d601125049f0c215b3b03bf8b13d2959872c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711763"
---
# <a name="verifyclientkey-function"></a>Функция VerifyClientKey
Проверяет, что ключ клиента имеет верные параметры безопасности.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно `ERROR_SUCCESS` (0).

Если функция завершается с ошибкой, возвращается код ошибки, определенный в *WinError.h*.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.def  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также
- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
