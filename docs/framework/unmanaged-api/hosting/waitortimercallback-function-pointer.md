---
title: Указатель функции WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f938c7dcf08654eef1e2403426eb5c54d6d2a6b3
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490121"
---
# <a name="waitortimercallback-function-pointer"></a>Указатель функции WAITORTIMERCALLBACK
Указывает на функцию, которая уведомляет основное приложение, дескриптор ожидания (<xref:System.Threading.WaitHandle>) был сигнал или истекло время ожидания.  
  
 Этот указатель функции был объявлен устаревшим в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `lpParameter`  
 [in] Указатель на объект, содержащий сведения, определенные средой размещения.  
  
 `TimerOrWaitFired`  
 [in] `true` Если дескриптор ожидания истекло, или `false` Если объект получил сигнал.  
  
## <a name="remarks"></a>Примечания  
 Функция, которая `WAITORTIMERCALLBACK` точки — это функция обратного вызова и должны быть реализованы модулем записи ведущего приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** "Mscorwks.dll"  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
