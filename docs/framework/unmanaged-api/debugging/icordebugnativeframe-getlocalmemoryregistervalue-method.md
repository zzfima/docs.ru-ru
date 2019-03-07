---
title: Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abaa543299dec74d769b91ca3b21d76863624f13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484944"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue
Получает значение аргумента или локальной переменной, из которых младшее слово и старшее слово хранятся в указанном регистре и расположение в памяти, соответственно, для данного кадра машинного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `highWordAddress`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее область памяти, содержащий старшее слово значения.  
  
 `lowWordRegister`  
 [in] Значение, указывающее регистр, содержащий младшее слово значение перечисления «CorDebugRegister».  
  
 `cbSigBlob`  
 [in] Целое число, указывающее размер двоичную подпись метаданных которого ссылается `pvSigBlob` параметра.  
  
 `pvSigBlob`  
 [in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.  
  
 `ppValue`  
 [out] Указатель на адрес объекта «ICorDebugValue», представляющего извлеченное значение, которое хранится в указанном расположении регистра и памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

