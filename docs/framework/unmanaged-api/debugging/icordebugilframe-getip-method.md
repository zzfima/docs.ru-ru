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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178827"
---
# <a name="icordebugilframegetip-method"></a>Метод ICorDebugILFrame::GetIP
Получает значение указателя инструкции и битое комбинированное значение, которое описывает, как было получено значение указателя инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pnOffset`  
 (ваут) Значение указателя инструкции.  
  
 `pMappingResult`  
 (ваут) Указатель на битную комбинацию значений перечисления CorDebugMappingResult, описывающих, как было получено значение указателя инструкции.  
  
## <a name="remarks"></a>Remarks  
 Значение указателя инструкции — это смещение кадра стека в промежуточный язык функции (MSIL). Если кадр стека активен, этот адрес является следующей инструкцией для выполнения. Если кадр стека не активен, этот адрес является следующей инструкцией для выполнения при повторной активации кадра стека.  
  
 Если этот кадр является точно в срок (JIT) скомпилированный кадр, значение указателя инструкции будет определено путем отображения назад от фактического указателя инструкции, так что значение может быть только приблизительным.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
