---
title: Метод ICorDebugILFrame::GetIP
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a7b8985e7580282d0e38205f9b1d6078f86cee6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479770"
---
# <a name="icordebugilframegetip-method"></a>Метод ICorDebugILFrame::GetIP
Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, как было получено значение указателя инструкций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pnOffset`  
 [out] Значение указателя инструкций.  
  
 `pMappingResult`  
 [out] Указатель на побитовое сочетание значений перечисления CorDebugMappingResult, которые описывают, каким образом было получено значение указателя инструкций.  
  
## <a name="remarks"></a>Примечания  
 Значение указателя инструкций — это смещение кадра стека в код на промежуточном языке (MSIL) функции. Если кадр стека активен, этот адрес является следующей инструкции для выполнения. Если кадр стека не активен, этот адрес соответствует следующей инструкции для выполнения при повторной активации кадра стека.  
  
 Если этого кадра кадр скомпилированного just-in-time (JIT), значение указателя инструкций будет определяться путем обратного сопоставления фактического собственный указатель инструкции, поэтому значение может быть только приблизительное.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
