---
title: Метод ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178902"
---
# <a name="icordebugframegetstackrange-method"></a>Метод ICorDebugFrame::GetStackRange
Получает абсолютный диапазон адресов этого стека кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pStart`  
 (ваут) Указатель на `CORDB_ADDRESS` указатель, который определяет начальный адрес кадра `ICorDebugFrame` стека, представленного этим объектом.  
  
 `pEnd`  
 (ваут) Указатель на `CORDB_ADDRESS` указатель, который определяет конечный адрес кадра `ICorDebugFrame` стека, представленного этим объектом.  
  
## <a name="remarks"></a>Remarks  
 Диапазон адресов стека полезен для склеивания взаимосвязанных следов стека, собранных из нескольких двигателей отладки. Числовой диапазон не содержит информации о содержимом кадра стека. Это имеет смысл только для сравнения расположения стек кадра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
