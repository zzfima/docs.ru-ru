---
title: Метод ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf3998d7430348cb71af8e7dd75cf2203d380ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769031"
---
# <a name="icordebugthread2getactivefunctions-method"></a>Метод ICorDebugThread2::GetActiveFunctions
Получает сведения о активной функции в каждом из кадров этот поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cFunctions`  
 [in] Размер массива `pFunctions`.  
  
 `pcFunctions`  
 [out] Указатель на число объектов, возвращаемых в `pFunctions` массива. Количество возвращенных объектов будет равно числу управляемые фреймы в стеке.  
  
 `pFunctions`  
 [in, out] Массив объектов COR_ACTIVE_FUNCTION, каждый из которых содержит сведения об активных функциях в рамках этого потока.  
  
 Первый элемент будет использоваться для фрейме конечного узла и т. д. обратно в корень стека.  
  
## <a name="remarks"></a>Примечания  
 Если `pFunctions` имеет значение null, если во входных данных, `GetActiveFunctions` возвращает количество функций, которые находятся в стеке. То есть если `pFunctions` имеет значение null, если во входных данных, `GetActiveFunctions` возвращает значение только в `pcFunctions`.  
  
 `GetActiveFunctions` Метод предназначен для оптимизации за получение те же сведения из кадров в трассировке стека и включает в себя только кадры, которые бы объект ICorDebugILFrame для них в полную трассировку стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
