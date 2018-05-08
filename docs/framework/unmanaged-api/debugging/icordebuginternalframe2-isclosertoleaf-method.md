---
title: Метод ICorDebugInternalFrame2::IsCloserToLeaf
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d26d4dc046841a891c8a36530bd579d100b8f5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>Метод ICorDebugInternalFrame2::IsCloserToLeaf
Проверяет, является ли `this` ближе к конечному объекту, чем указанный объект ICorDebugFrame внутреннего фрейма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pFrameToCompare`  
 [in] Указатель на сравнении `ICorDebugFrame` объекта.  
  
 `pIsCloser`  
 [out] `true` Если `this` внутреннего фрейма ближе к конечному объекту, чем кадр, определяемый `pFrameToCompare`; в противном случае `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Сравнение успешно выполнено.|  
|E_FAIL|Не удалось выполнить сравнение.|  
|E_INVALIDARG|`pFrameToCompare` или `pIsCloser` равно null.|  
  
## <a name="remarks"></a>Примечания  
 `IsCloserToLeaf` можно использовать для реализации политики чередования внутренних кадров с другими кадрами в стеке.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
