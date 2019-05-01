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
ms.openlocfilehash: b27e40618d6128c21e99745ca45e139a9c21c843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988998"
---
# <a name="icordebugeval2createvaluefortype-method"></a>Метод ICorDebugEval2::CreateValueForType
Возвращает указатель на новый ICorDebugValue указанного типа, с начальным значением, равным нулю или null.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pType`  
 [in] Указатель на объект, представляющий тип ICorDebugType.  
  
 `ppValue`  
 [out] Указатель на адрес `ICorDebugValue` объект, представляющий значение.  
  
## <a name="remarks"></a>Примечания  
 `CreateValueForType` обобщает [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) , позволяя указывать тип произвольный объект, включая созданный типы например `List<int>`. Этот метод предназначена исключительно для создания значения, который может быть передан на вычисление функции.  
  
 Тип должен быть классом или типом значения. Этот метод нельзя использовать для создания значений массива или строковых значений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
