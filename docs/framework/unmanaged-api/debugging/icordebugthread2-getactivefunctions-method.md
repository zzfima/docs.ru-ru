---
title: "Метод ICorDebugThread2::GetActiveFunctions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ecd9446f642011b21f784019f583f49e3a70433a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2getactivefunctions-method"></a>Метод ICorDebugThread2::GetActiveFunctions
Получает сведения о активной функции, в каждой из рамок этот поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cFunctions`  
 [in] Размер массива `pFunctions`.  
  
 `pcFunctions`  
 [out] Указатель на число объектов, возвращаемых `pFunctions` массива. Число возвращенных объектов будет равно числу управляемые фреймы в стеке.  
  
 `pFunctions`  
 [in, out] Массив объектов COR_ACTIVE_FUNCTION, каждый из которых содержит сведения о функциях активные в рамках данного потока.  
  
 Первый элемент будет использоваться для конечного кадра и т. д. обратно в корень стека.  
  
## <a name="remarks"></a>Примечания  
 Если `pFunctions` имеет значение null, если на входе `GetActiveFunctions` возвращает количество функций, которые находятся в стеке. То есть если `pFunctions` имеет значение null, если на входе `GetActiveFunctions` возвращает значение только в `pcFunctions`.  
  
 `GetActiveFunctions` Метод предназначен для оптимизации за получение те же сведения из кадров в трассировке стека и содержит только кадры, которые бы объект ICorDebugILFrame для них в полную трассировку стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
