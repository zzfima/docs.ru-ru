---
title: "Метод ICorDebugILFrame::GetIP"
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
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79b18c6fe15e28b2cec07ef9dfaa06ee295ab42d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetip-method"></a>Метод ICorDebugILFrame::GetIP
Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, каким образом было получено значение указателя инструкций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pnOffset`  
 [out] Значение указателя инструкций.  
  
 `pMappingResult`  
 [out] Указатель на побитовое сочетание значений перечисления CorDebugMappingResult, которые описывают, каким образом было получено значение указателя инструкций.  
  
## <a name="remarks"></a>Примечания  
 Значение указателя инструкций — смещение кадра стека функции код на промежуточном языке (MSIL). Если кадр стека активен, этот адрес будет следующую инструкцию для выполнения. Если кадр стека не активен, этот адрес будет следующую инструкцию для выполнения при повторной активации кадра стека.  
  
 Если этот кадр кадр скомпилированных just-in-time (JIT), значение указателя инструкций будет определяться обратного сопоставления фактического собственный указатель инструкции, поэтому значение может быть только приблизительным.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
