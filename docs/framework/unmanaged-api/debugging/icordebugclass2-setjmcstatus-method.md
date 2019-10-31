---
title: Метод ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125690"
---
# <a name="icordebugclass2setjmcstatus-method"></a>Метод ICorDebugClass2::SetJMCStatus
Для каждого метода класса задает значение, указывающее, является ли метод определяемым пользователем кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bIsJustMyCode`  
 окне Задайте значение `true`, чтобы указать, что метод является определяемым пользователем кодом; в противном случае задайте значение `false`.  
  
## <a name="remarks"></a>Заметки  
 Средство "только мой код" (JMC) пропускает код, не определенный пользователем. Определяемый пользователем код должен быть подмножеством отлаживаемого кода.  
  
 `SetJMCStatus` возвращает значение HRESULT, равное S_FALSE, если не удается задать значение для какого бы то ни было метода, даже если оно успешно задает значение для всех других методов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
