---
title: Метод ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7685d1b6d5458a4405fc5a4abdb2f3134618f01c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794405"
---
# <a name="icordebugheapvalueisvalid-method"></a>Метод ICorDebugHeapValue::IsValid
Возвращает значение, указывающее, является ли допустимым объект, представленный этим ICorDebugHeapValue.  
  
 Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbValid`  
 заполняет Указатель на логическое значение, указывающее, является ли значение в куче допустимым.  
  
## <a name="remarks"></a>Заметки  
 Значение недопустимо, если оно было освобождено сборщиком мусора.  
  
 Этот метод использовать не рекомендуется. В .NET Framework 2,0 все значения являются допустимыми до тех пор, пока не будет вызван метод [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , после чего значения становятся недействительными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
