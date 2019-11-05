---
title: Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137241"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
Удаляет ранее установленную точку останова по указанному адресу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 окне Значение `CORDB_ADDRESS`, указывающее адрес, по которому была задана точка останова.  
  
## <a name="remarks"></a>Заметки  
 Указанная точка останова была ранее задана предыдущим вызовом метода [ICorDebugProcess2:: сетунманажедбреакпоинт](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Метод `ClearUnmanagedBreakpoint` можно вызвать во время выполнения отлаживаемого процесса.  
  
 Метод `ClearUnmanagedBreakpoint` возвращает код ошибки, если отладчик присоединен в режиме "только управляемый" или если в указанном адресе не существует точки останова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
