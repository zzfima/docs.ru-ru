---
title: Метод ICorDebugNativeFrame::GetLocalRegisterMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc179236f5453724639d47558770179a1e80f706
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746196"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a>Метод ICorDebugNativeFrame::GetLocalRegisterMemoryValue
Получает значение аргумента или локальной переменной, из которых младшее слово и старшее слово хранятся в расположении в памяти и указанный регистр, соответственно, для данного кадра машинного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `highWordReg`  
 [in] Значение, указывающее регистр, содержащий старшее слово значение перечисления «CorDebugRegister».  
  
 `lowWordAddress`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее область памяти, содержащий значение младшее слово.  
  
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
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
