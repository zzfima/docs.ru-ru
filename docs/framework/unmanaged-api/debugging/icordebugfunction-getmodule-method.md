---
title: Метод ICorDebugFunction::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cefe84c482df3b20b5939e031ad76647f295d3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995622"
---
# <a name="icordebugfunctiongetmodule-method"></a>Метод ICorDebugFunction::GetModule
Возвращает модуль, в котором определена эта функция.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppModule`  
 [out] Указатель на адрес ICorDebugModule объект, представляющий модуль, в котором определена эта функция.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
