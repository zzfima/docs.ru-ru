---
title: Метод ICorDebugEval2::CreateValueForType
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 683457c249915708becadaeda9dec265666e2023
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412111"
---
# <a name="icordebugeval2createvaluefortype-method"></a>Метод ICorDebugEval2::CreateValueForType
Возвращает указатель на новый ICorDebugValue заданного типа с начальным значением, равным нулю или null.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pType`  
 [in] Указатель на объект ICorDebugType, который представляет тип.  
  
 `ppValue`  
 [out] Указатель на адрес `ICorDebugValue` объект, представляющий значение.  
  
## <a name="remarks"></a>Примечания  
 `CreateValueForType` обобщает [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) , позволяя указывать тип произвольный объект, включая составить типы например `List<int>`. Этот метод предназначен только для создания значения, который может быть передан на вычисление функции.  
  
 Тип должен быть классом или типом значения. Этот метод нельзя использовать для создания массива значений или строковых значений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
