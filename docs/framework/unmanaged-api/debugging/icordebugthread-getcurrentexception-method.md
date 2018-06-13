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
ms.openlocfilehash: 82686fdd14783257987ec5bf9a24db7d87049d42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421750"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Метод ICorDebugThread::GetCurrentException
Получает указатель на интерфейс ICorDebugValue объекта, который представляет исключение, которое в настоящее время возникшего исключения в управляемом коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppExceptionObject`  
 [out] Указатель на адрес `ICorDebugValue` объект, который представляет исключение, которое в настоящее время вызвано управляемого кода.  
  
## <a name="remarks"></a>Примечания  
 Объект исключения будет существовать с момента исключения до конца `catch` блока. Вычисление функции, которая выполняется с помощью методов ICorDebugEval будет очистить объекта исключения при установке и восстановите ее завершения.  
  
 Исключения могут быть вложенными (например, если исключение создается в фильтре или при вычислении функции), поэтому может существовать несколько необработанных исключений в одном потоке. `GetCurrentException` Возвращает наиболее текущее исключение.  
  
 Объект и тип исключения могут меняться на протяжении жизненного цикла. Например после типа x создается исключение, общеязыковой среды выполнения (CLR) может возникнуть нехватка памяти и повысить уровень до исключения нехватки памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
