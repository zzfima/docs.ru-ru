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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b65a621541f2b4a800f6b3708a6b257374c5866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessisossuspended-method"></a>Метод ICorDebugProcess::IsOSSuspended
Возвращает значение, указывающее, приостановлено ли заданный поток в результате остановки этого процесса отладчиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока в вопросе.  
  
 `pbSuspended`  
 [out] Указатель на значение типа Boolean, `true` если заданный поток был приостановлен; в противном случае значение *`pbSuspended` — `false`.  
  
## <a name="remarks"></a>Примечания  
 При приостановке указанного потока в результате остановки этого процесса отладчиком счетчика приостановок Win32 указанного потока увеличивается на единицу. Пользовательский интерфейс (UI) отладчик может потребоваться учесть эти сведения учетной записи, если она отображает операционной системы (ОС) число приостановок работы потока для пользователя.  
  
 `IsOSSuspended` Метод имеет смысл только в контексте неуправляемой отладки. При отладке управляемого кода, потоки совместно приостановленном, а не приостановлен ОС.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
