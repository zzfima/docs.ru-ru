---
title: Метод ICorDebugHeapValue2::CreateHandle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c69d1f83a4591df4d2dcb7fb9724fa582ea28387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugheapvalue2createhandle-method"></a>Метод ICorDebugHeapValue2::CreateHandle
Создает дескриптор указанного типа для значения кучи, представленный этим объектом ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 [in] Значение cordebughandletype-перечисление, указывающее тип дескриптора.  
  
 `ppHandle`  
 [out] Указатель на адрес объекта ICorDebugHandleValue, который представляет новый маркер для этого значения кучи.  
  
## <a name="remarks"></a>Примечания  
 Дескриптор создается в домене приложения, связанный со значением кучи и станут недопустимыми, если момента выгрузки домена приложения.  
  
 Несколько вызовов этой функции для одного значения кучи создадут множественные дескрипторы. Так как дескрипторы влияют на производительность сборщика мусора, отладчик должен задать ограничение относительно небольшого числа дескрипторов (около 256), которые активны одновременно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
