---
title: "Метод ICorDebugChain::GetStackRange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce5e42bb9374f22ad29ef0e97a141a796f087a98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetstackrange-method"></a>Метод ICorDebugChain::GetStackRange
Возвращает диапазон адресов сегмента стека для этой цепи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStart`  
 [out] Указатель на `CORDB_ADDRESS` значение, которое начальный адрес сегмента стека.  
  
 `pEnd`  
 [out] Указатель на `CORDB_ADDRESS` значение, которое конечный адрес сегмента стека.  
  
## <a name="remarks"></a>Примечания  
 Числовой диапазон имеет смысл только для сравнения расположений кадров стека. Нельзя делать никаких предположений о том, что фактически хранятся в стеке.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
