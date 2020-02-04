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
ms.openlocfilehash: b5f6a830cbe601443f03cd91a356c7e49450e7f3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793728"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Метод ICLRDataTarget::GetThreadContext
Возвращает текущий контекст выполнения для данного потока в целевом процессе. Этот метод вызывается службами доступа к данным среды CLR.  
  
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
 окне Идентификатор операционной системы потока в целевом процессе.  
  
 `contextFlags`  
 окне Флаги, указывающие, какие части контекста должны быть возвращены. Реализация возвратит по крайней мере эти части контекста.  
  
 `contextSize`  
 окне Размер контекста.  
  
 `context`  
 заполняет Указатель на буфер, в который будет помещен контекст.  
  
 Данные в буфере `context` должны быть в формате структуры `CONTEXT` Win32. Контекст задает зависящие от процессора данные регистра, поэтому определение структуры `CONTEXT` Win32 зависит от архитектуры процессора. Описание структуры `CONTEXT` Win32 см. в файле заголовка WinNT. h.  
  
## <a name="remarks"></a>Заметки  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
