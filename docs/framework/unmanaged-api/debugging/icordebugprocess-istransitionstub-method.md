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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06dc35998a2874ed1d2f76725078874817e94d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420099"
---
# <a name="icordebugprocessistransitionstub-method"></a>Метод ICorDebugProcess::IsTransitionStub
Получает значение, указывающее, является ли адрес в заглушке, что вызовет переход к управляемому коду.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее адрес в вопросе.  
  
 `pbTransitionStub`  
 [out] Указатель на значение типа Boolean, `true` Если указанный адрес находится в пределах заглушки, которая вызовет переход к управляемому коду; в противном случае *`pbTransitionStub` — `false`.  
  
## <a name="remarks"></a>Примечания  
 `IsTransitionStub` Метод может использоваться в неуправляемом коде пошагового выполнения для определения момента возвращения управления пошаговым выполнением в управляемый шаг.  
  
 Вы также можете заглушки перехода удостоверений, просмотрев информацию в переносимом исполняемом (PE) файле.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
