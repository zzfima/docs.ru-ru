---
title: Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9de77f942a1b89b0ab11ef71229e491a5305cafc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue
Возвращает значение аргумента или локальной переменной, которая хранится в двух заданных регистрах этого кадра машинного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `highWordReg`  
 [in] Значение, указывающее регистр, содержащего и слово высокой значения перечисления «CorDebugRegister».  
  
 `lowWordReg`  
 [in] Значение `CorDebugRegister` перечисление, указывающее регистр, содержащего и слово низкого значения.  
  
 `cbSigBlob`  
 [in] Целое число, указывающее размер двоичную подпись метаданных которой ссылается `pvSigBlob` параметра.  
  
 `pvSigBlob`  
 [in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.  
  
 `ppValue`  
 [out] Указатель на адрес объекта «ICorDebugValue», представляющий возвращенного значения, которые хранятся в регистрах, указанного.  
  
## <a name="remarks"></a>Примечания  
 `GetLocalDoubleRegisterValue` Метод может использоваться в фрейм машинного кода или just-in-time (JIT)-компиляции кадра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
