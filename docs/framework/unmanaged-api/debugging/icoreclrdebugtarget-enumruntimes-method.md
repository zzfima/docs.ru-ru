---
title: Метод ICoreClrDebugTarget::EnumRuntimes
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afb31646d21ec7e15f79601f5fe83ea6ce44fa90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986717"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>Метод ICoreClrDebugTarget::EnumRuntimes
Перечисляет среды CLR в указанном процессе, который выполняется на удаленном компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>Параметры  
 `dwInternalProcessID`  
 [in] Внутренний идентификатор процесса, для которого требуется перечислить среды выполнения. Это будет `m_dwInternalID` из соответствующего [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).  
  
 `pcRuntimes`  
 [out] Число сред выполнения, возвращаемых в `ppRuntimes`. Это значение может быть 0 (ноль).  
  
 `ppRuntimes`  
 [out] Массив [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) структуры, которые представляют среды выполнения, загруженных в удаленном целевом процессе.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Выполнено.  
  
 S_FALSE  
 `dwInternalProcessID` не соответствует ни одному процессу, который выполняется на компьютере, возможно потому, что этот процесс был завершен. `pcRuntimes` и `ppRuntimes` будут иметь значение null.  
  
 E_OUTOFMEMORY  
 Не удается выделить достаточно памяти для `ppRuntimes`.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="remarks"></a>Примечания  
 Чтобы освободить память, выделенную этим методом, вызовите [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
