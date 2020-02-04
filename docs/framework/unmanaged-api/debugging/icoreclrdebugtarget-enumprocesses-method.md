---
title: Метод ICoreClrDebugTarget::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 11b1072b3467f7d0a3f223fbc2151ec9ccf461ad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790805"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a>Метод ICoreClrDebugTarget::EnumProcesses
Перечисляет процессы, работающие на удаленном компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pcProcs`  
 [out] Число процессов, возвращаемых в `ppProcs`. Это значение может быть 0 (ноль).  
  
 `ppProcs`  
 заполняет Массив структур [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) , представляющих процессы, выполняемые на удаленном компьютере.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Выполнено.  
  
 E_OUTOFMEMORY  
 Не удается выделить достаточно памяти для `ppProcs`.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="remarks"></a>Заметки  
 Чтобы освободить память, выделенную этим методом, вызовите метод [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86. dll  
  
 **.NET Framework версии:** 3,5 SP1  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)
