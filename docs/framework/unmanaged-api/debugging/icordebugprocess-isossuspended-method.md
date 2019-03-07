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
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492079"
---
# <a name="icordebugprocessisossuspended-method"></a>Метод ICorDebugProcess::IsOSSuspended
Получает значение, указывающее, приостановлено ли указанный поток в результате остановки этого процесса отладчиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока в вопросе.  
  
 `pbSuspended`  
 [out] Указатель на логическое значение, которое является `true` значение, если указанный поток приостановленной; в противном случае *`pbSuspended` является `false`.  
  
## <a name="remarks"></a>Примечания  
 Если указанного потока приостановлено из-за остановки этого процесса отладчиком, счетчик приостановок Win32 указанного потока увеличивается на единицу. Пользовательский интерфейс отладчика (UI) может потребоваться учесть эти сведения учетной записи, если она отображает операционной системы (ОС) приостановка счетчика для пользователя.  
  
 `IsOSSuspended` Метод имеет смысл только в контексте отладка неуправляемого кода. При отладке управляемого кода, потоки, совместно приостановленной вместо ОС.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
