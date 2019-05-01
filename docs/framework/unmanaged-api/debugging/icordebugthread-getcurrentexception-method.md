---
title: Метод ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4baa4eb4da48b923ab0137ca25d9d819c94e33d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994036"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Метод ICorDebugThread::GetCurrentException
Получает указатель на интерфейс ICorDebugValue объект, представляющий исключение, которое в настоящее время возникающего исключения в управляемом коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppExceptionObject`  
 [out] Указатель на адрес `ICorDebugValue` , представляющий исключение, которое в настоящее время вызвано управляемого кода.  
  
## <a name="remarks"></a>Примечания  
 Объект исключения будет существовать с момента, возникает исключение, до конца `catch` блока. Вычисление функции, который выполняется с помощью методов ICorDebugEval будет очистить объекта исключения при установке и восстановите ее после завершения.  
  
 Исключения могут быть вложенными, (например, если создается исключение в фильтре или при вычислении функции), поэтому может существовать несколько необработанных исключений в одном потоке. `GetCurrentException` Возвращает наиболее текущее исключение.  
  
 Объект исключения и тип может изменяться в течение жизненного цикла. Например после типа x создается исключение, общеязыковой среды выполнения (CLR) может возникнуть нехватка памяти и повысить его уровень до исключение out of memory.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
