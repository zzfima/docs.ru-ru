---
title: Метод ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139387"
---
# <a name="icordebugprocessistransitionstub-method"></a>Метод ICorDebugProcess::IsTransitionStub
Возвращает значение, указывающее, находится ли адрес в заглушке, что приведет к переходу в управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 окне Значение `CORDB_ADDRESS`, указывающее адрес в вопросе.  
  
 `pbTransitionStub`  
 заполняет Указатель на логическое значение, `true`, если указанный адрес находится внутри заглушки, которая приведет к переходу в управляемый код. в противном случае *`pbTransitionStub` `false`.  
  
## <a name="remarks"></a>Заметки  
 Метод `IsTransitionStub` может использоваться неуправляемым пошаговым кодом, чтобы решить, когда следует возвращать управление пошаговым выполнением в управляемое средство Организации.  
  
 Вы также можете идентифицировать заглушки перехода, просмотрев информацию в переносимом исполняемом файле (PE).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
