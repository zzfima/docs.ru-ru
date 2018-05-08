---
title: Метод ICorDebugObjectValue2::GetVirtualMethodAndType
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9a6978f35b5ea9fb71f8e933dbc7a08b1c390ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a>Метод ICorDebugObjectValue2::GetVirtualMethodAndType
Этот метод еще не реализован.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a>Примечания  
 Получает указатели интерфейса на «ICorDebugFunction» и «ICorDebugType» экземпляры, которые представляют наиболее производного метода и тип для ссылки на указанный элемент.  
  
## <a name="see-also"></a>См. также  
    
 
