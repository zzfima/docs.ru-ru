---
title: Метод ICorDebugArrayValue::GetElement
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: adcb7b5a27f3b8c63dbbb660a23b5c891f84ac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179012"
---
# <a name="icordebugarrayvaluegetelement-method"></a>Метод ICorDebugArrayValue::GetElement
Получает значение данного элемента массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cdim`  
 (в) Количество размеров этого `ICorDebugArrayValue` объекта.  
  
 Это значение также является `indices` размером массива, поскольку его размер `ICorDebugArrayValue` равен количеству размеров объекта.  
  
 `indices`  
 (в) Массив значений индекса, каждое из которых определяет положение в `ICorDebugArrayValue` измерении объекта.  
  
 Это значение не должно быть нулевым.  
  
 `ppValue`  
 (ваут) Указатель на адрес объекта ICorDebugValue, представляющий значение указанного элемента.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
