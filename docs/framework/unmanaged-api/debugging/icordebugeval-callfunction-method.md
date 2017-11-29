---
title: "Метод ICorDebugEval::CallFunction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72713d81931b53e8d61fb39cee146fd30a59bfcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
