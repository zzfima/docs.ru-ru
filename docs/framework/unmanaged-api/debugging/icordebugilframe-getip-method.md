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
ms.openlocfilehash: 7e1605eede55360e72d65da6744bc1dcce4f107f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130988"
---
# <a name="icordebugilframegetip-method"></a>Метод ICorDebugILFrame::GetIP
Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pnOffset`  
 заполняет Значение указателя инструкции.  
  
 `pMappingResult`  
 заполняет Указатель на побитовую комбинацию значений перечисления Кордебугмаппингресулт, описывающих, как было получено значение указателя инструкции.  
  
## <a name="remarks"></a>Заметки  
 Значение указателя инструкции является смещением кадра стека в коде MSIL для функции. Если кадр стека активен, то этот адрес является следующей инструкцией для выполнения. Если кадр стека неактивен, этот адрес является следующей инструкцией для выполнения при повторной активации кадра стека.  
  
 Если этот кадр является JIT-скомпилированным кадром, то значение указателя инструкции будет определяться в обратном направлении от фактического указателя инструкций в машинном виде, поэтому значение может быть только приблизительным.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
