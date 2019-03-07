---
title: Метод ICorDebugEval2::NewStringWithLength
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b84a2fad53feda2996515781035c0eaad5828d54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473439"
---
# <a name="icordebugeval2newstringwithlength-method"></a>Метод ICorDebugEval2::NewStringWithLength
Создает строку указанной длины, с указанным содержимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `string`  
 [in] Указатель на строковое значение.  
  
 `uiLength`  
 [in] Длина строки.  
  
## <a name="remarks"></a>Примечания  
 Если в конце строки нуль-символ должен быть в управляемую строку, объект, вызывающий `NewStringWithLength` метода необходимо убедиться, что длина строки включает конечный символ null.  
  
 Строка всегда создается в домене приложения, в котором в настоящее время выполняется поток.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
