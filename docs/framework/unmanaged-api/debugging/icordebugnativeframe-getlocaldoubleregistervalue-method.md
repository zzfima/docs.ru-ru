---
title: "Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75b8c4d5551c9624852f1e0f730d1215236608de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
