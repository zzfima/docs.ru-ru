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
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133487"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Метод ICorDebugThread::GetCurrentException
Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppExceptionObject`  
 заполняет Указатель на адрес объекта `ICorDebugValue`, представляющий исключение, которое в данный момент вызывается управляемым кодом.  
  
## <a name="remarks"></a>Заметки  
 Объект исключения будет существовать с момента возникновения исключения до конца блока `catch`. Вычисление функции, выполняемое методами ICorDebugEval, очистит объект исключения при установке и восстановит его по завершении.  
  
 Исключения могут быть вложенными (например, если исключение создается в фильтре или в вычислении функции), поэтому в одном потоке может быть несколько необработанных исключений. `GetCurrentException` возвращает последнее исключение.  
  
 Объект и тип исключения могут меняться в течение всего времени существования исключения. Например, после возникновения исключения типа x среда CLR может закончится нехваткой памяти и повысить ее до исключения нехватки памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
