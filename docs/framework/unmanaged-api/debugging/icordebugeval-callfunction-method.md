---
title: Метод ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugevalcallfunction-method"></a>Метод ICorDebugEval::CallFunction
Настраивает вызов указанной функции.  
  
 Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pFunction`  
 [in] Указатель на объект ICorDebugFunction, который задает вызываемую функцию.  
  
 `nArgs`  
 [in] Число аргументов для функции.  
  
 `ppArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, который указывает аргумент, передаваемый в функцию.  
  
## <a name="remarks"></a>Примечания  
 Если функция является виртуальной, `CallFunction` выполнит виртуальной отправки. Если функция находится в другом домене приложения, будет выполнен переход при условии, что все аргументы также имеются в этом домене приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** WindowSee [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также  
 [Метод CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
