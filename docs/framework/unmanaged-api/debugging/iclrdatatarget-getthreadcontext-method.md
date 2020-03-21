---
title: Метод ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179180"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Метод ICLRDataTarget::GetThreadContext
Получает текущий контекст выполнения для данного потока в процессе целевого. Этот метод вызывается службами общего времени выполнения данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 (в) Идентификатор операционной системы потока в процессе целевого.  
  
 `contextFlags`  
 (в) Флаги, указывающие, какие части контекста вернуть. Реализация вернет по крайней мере эти части контекста.  
  
 `contextSize`  
 (в) Размер контекста.  
  
 `context`  
 (ваут) Указатель на буфер, в котором можно разместить контекст.  
  
 Данные в `context` буфере должны быть в формате структуры Win32. `CONTEXT` Контекст определяет данные регистра для процессоров, поэтому определение `CONTEXT` структуры Win32 зависит от архитектуры процессора. Обратитесь к файлу заголовка WinNT.h для `CONTEXT` определения структуры Win32.  
  
## <a name="remarks"></a>Remarks  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
