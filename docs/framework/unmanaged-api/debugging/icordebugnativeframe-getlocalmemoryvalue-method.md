---
title: Метод ICorDebugNativeFrame::GetLocalMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a8e5a1813a81a84eac612a53964d39b48f0c536
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746214"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a>Метод ICorDebugNativeFrame::GetLocalMemoryValue
Получает значение аргумента или локальной переменной, которая хранится в заданном расположении памяти для данного кадра машинного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее область памяти, содержащий значение.  
  
 `cbSigBlob`  
 [in] Целое число, указывающее размер двоичную подпись метаданных которого ссылается `pvSigBlob` параметра.  
  
 `pvSigBlob`  
 [in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.  
  
 `ppValue`  
 [out] Указатель на адрес объекта «ICorDebugValue», представляющего извлеченное значение, которое хранится в указанной области памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
