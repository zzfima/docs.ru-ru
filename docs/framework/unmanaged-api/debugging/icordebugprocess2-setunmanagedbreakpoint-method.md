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
ms.openlocfilehash: d4326c6d8a3ee780cf63652badc8c527f55a075c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::SetUnmanagedBreakpoint
Задает неуправляемую точку останова с позиции указанного образа в машинном коде.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` , указывающий смещение образов в машинном коде.  
  
 `bufsize`  
 [in] Размер в байтах для `buffer` массива.  
  
 `buffer`  
 [out] Массив, содержащий код операции, который заменяется точки останова.  
  
 `bufLen`  
 [out] Указатель на число байтов, возвращенных в `buffer` массива.  
  
## <a name="remarks"></a>Примечания  
 Если смещение образа в машинном коде в общеязыковой среде выполнения (CLR), точка останова будет игнорироваться. Это позволяет среде CLR избежать диспетчеризации точки останова по внешнему каналу, когда задана точка останова в отладчике.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
