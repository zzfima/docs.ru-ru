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
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137284"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue
Возвращает значение аргумента или локальной переменной, из которых младшее слово и верхнее слово хранятся в указанном регистре и расположении в памяти соответственно для этого кадра машинного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне Значение `CORDB_ADDRESS`, указывающее место в памяти, содержащее старшее слово значения.  
  
 `lowWordRegister`  
 окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий нижнее слово значения.  
  
 `cbSigBlob`  
 окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается параметр `pvSigBlob`.  
  
 `pvSigBlob`  
 окне Значение `PCCOR_SIGNATURE`, которое указывает на сигнатуру двоичных метаданных для типа значения.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанном регистре и расположении в памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
