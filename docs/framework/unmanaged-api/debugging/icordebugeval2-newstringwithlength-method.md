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
ms.openlocfilehash: 6b3b77a0ffc7af3b3640d1b255bd3be522f45a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413554"
---
# <a name="icordebugeval2newstringwithlength-method"></a>Метод ICorDebugEval2::NewStringWithLength
Создает строку указанной длины с указанным содержимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `string`  
 [in] Указатель на строковое значение.  
  
 `uiLength`  
 [in] Длина строки.  
  
## <a name="remarks"></a>Примечания  
 Если строка замыкающие символ null должно быть в строке управляемый код, вызывающий `NewStringWithLength` метода необходимо убедиться, что длина строки включает конечный символ null.  
  
 Строка всегда создается в домене приложения, в котором в настоящее время выполняется поток.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
