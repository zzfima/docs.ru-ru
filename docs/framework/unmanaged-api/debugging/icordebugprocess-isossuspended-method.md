---
title: "Метод ICorDebugProcess::IsOSSuspended"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
