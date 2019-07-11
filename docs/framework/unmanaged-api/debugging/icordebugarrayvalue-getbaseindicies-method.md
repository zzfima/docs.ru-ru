---
title: Метод ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f4ecb700a19a4e06f9f0056881fe3cdb9753aae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737607"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a>Метод ICorDebugArrayValue::GetBaseIndicies
Получает базовый индекс каждого измерения в массиве.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cdim`  
 [in] Размерность данного `ICorDebugArrayValue` объекта. Этот параметр также имеет размер `indicies` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.  
  
 `indicies`  
 [out] Массив целых чисел, каждое из которых является базовый индекс (то есть, начальный индекс) измерения данного `ICorDebugArrayValue` объекта.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
