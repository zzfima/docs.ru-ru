---
title: Метод ICorDebugInternalFrame::GetFrameType
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7e5fceacc3fefa9267a9d7f989e745c392322e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414129"
---
# <a name="icordebuginternalframegetframetype-method"></a>Метод ICorDebugInternalFrame::GetFrameType
Получает тип данного внутреннего фрейма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pType`  
 [out] Указатель на значение перечисления CorDebugInternalFrameType, которое указывает тип внутреннего фрейма, представленный этим `ICorDebugInternalFrame` объекта.  
  
## <a name="remarks"></a>Примечания  
 Тип внутреннего фрейма STUBFRAME_NONE никогда не будет. Отладчики правильно учитывать типы нераспознанный внутреннего фрейма.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
