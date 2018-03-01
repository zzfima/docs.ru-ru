---
title: "Метод ICorDebugProcess::IsTransitionStub"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
