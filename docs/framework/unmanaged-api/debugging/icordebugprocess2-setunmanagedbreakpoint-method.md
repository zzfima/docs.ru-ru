---
title: Метод ICorDebugProcess2::SetUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b374720bd7bdad48222da006b809702de6462a62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948851"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::SetUnmanagedBreakpoint
Задает неуправляемую точку останова с указанным образов в машинном коде смещения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` , указывающий смещение образов в машинном коде.  
  
 `bufsize`  
 [in] Размер в байтах из `buffer` массива.  
  
 `buffer`  
 [out] Массив, содержащий код операции, который заменяется точки останова.  
  
 `bufLen`  
 [out] Указатель на число байтов, возвращаемых в `buffer` массива.  
  
## <a name="remarks"></a>Примечания  
 Если смещение образов в машинном коде в общеязыковой среде выполнения (CLR), точка останова будет игнорироваться. Это позволяет среде CLR избежать диспетчеризации точки останова каналу, если задана точка останова в отладчике.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
