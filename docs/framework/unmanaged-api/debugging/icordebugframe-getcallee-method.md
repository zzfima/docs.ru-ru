---
title: Метод ICorDebugFrame::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d62f4f8a34123bcd3f0cbe56f1c1b958bcaa6ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugframegetcallee-method"></a>Метод ICorDebugFrame::GetCallee
Возвращает указатель на объект ICorDebugFrame в текущей цепи, вызванной этим кадром.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppFrame`  
 [out] Указатель на адрес `ICorDebugFrame` , представляющий вызываемый кадр. Это значение равно null, если вызывающий кадр является самым внутренним кадром в текущей цепи.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
