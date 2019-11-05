---
title: Метод ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 21da69d4bff0f17eb607dda45fb7dbafea8c59f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128774"
---
# <a name="icordebugprocessisossuspended-method"></a>Метод ICorDebugProcess::IsOSSuspended
Возвращает значение, указывающее, был ли заданный поток приостановлен в результате остановки этого процесса отладчиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 окне Идентификатор рассматриваемого потока.  
  
 `pbSuspended`  
 заполняет Указатель на логическое значение, которое `true`, если указанный поток был приостановлен; в противном случае *`pbSuspended` `false`.  
  
## <a name="remarks"></a>Заметки  
 Если указанный поток был приостановлен в результате остановки этого процесса отладчиком, счетчик приостановки Win32 указанного потока увеличивается на единицу. Пользовательский интерфейс отладчика может захотеть использовать эту информацию при отображении счетчика приостановки операционной системы (ОС) для пользователя.  
  
 Метод `IsOSSuspended` имеет смысл только в контексте неуправляемой отладки. Во время управляемой отладки потоки приостанавливаются совместно, а не с приостановленной ОС.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
