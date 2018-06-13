---
title: Метод ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d17ac4230296674381c87851377fcb535837ad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416823"
---
# <a name="icordebugnativeframegetip-method"></a>Метод ICorDebugNativeFrame::GetIP
Возвращает расположение, к которому в настоящее время имеет значение указателя инструкций смещения в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pnOffset`  
 [out] Указатель на расположение смещения в машинном коде.  
  
## <a name="remarks"></a>Примечания  
 Если кадр стека, представленный «ICorDebugNativeFrame» активен, смещение — это адрес следующую инструкцию для выполнения. Если этот кадр стека не активен, смещение — это адрес следующую инструкцию для выполнения при повторной активации кадра стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
