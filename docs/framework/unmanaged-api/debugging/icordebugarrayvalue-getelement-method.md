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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 500e01955666c7a8e2bd1dcf9d34afe3aeb6b421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugarrayvaluegetelement-method"></a>Метод ICorDebugArrayValue::GetElement
Получает значение заданного элемента массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cdim`  
 [in] Размерность этого `ICorDebugArrayValue` объекта.  
  
 Этот параметр также имеет размер `indices` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.  
  
 `indices`  
 [in] Массив значений индекса, каждая из которых задает измерение, позиция в массиве `ICorDebugArrayValue` объекта.  
  
 Это значение не может иметь значение null.  
  
 `ppValue`  
 [out] Указатель на адрес объекта ICorDebugValue, представляющее значение указанного элемента.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
