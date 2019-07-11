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
ms.openlocfilehash: 275f62c8211f71f067d310dd4b3af2ddb11e93d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755460"
---
# <a name="icordebugprocessisossuspended-method"></a>Метод ICorDebugProcess::IsOSSuspended
Получает значение, указывающее, приостановлено ли указанный поток в результате остановки этого процесса отладчиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
