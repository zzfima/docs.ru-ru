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
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775524"
---
# <a name="icordebugprocessistransitionstub-method"></a>Метод ICorDebugProcess::IsTransitionStub
Получает значение, указывающее, является ли адрес в заглушке, вызовет переход к управляемому коду.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее адрес в вопросе.  
  
 `pbTransitionStub`  
 [out] Указатель на логическое значение, которое является `true` Если указанный адрес находится внутри заглушку, вызовет переход к управляемому коду; в противном случае *`pbTransitionStub` является `false`.  
  
## <a name="remarks"></a>Примечания  
 `IsTransitionStub` Метод может использоваться в неуправляемом коде пошагового выполнения для принятия решения о возвращения управления пошаговым управляемый шаг.  
  
 Вы также можете заглушки перехода удостоверений, просмотрев сведения в переносимый исполняемый файл (PE).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
