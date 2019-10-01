---
title: Метод ICorDebugCode::IsIL
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700798"
---
# <a name="icordebugcodeisil-method"></a>Метод ICorDebugCode::IsIL

Возвращает значение, указывающее, представляет ли этот "ICorDebugCode" код, скомпилированный на языке MSIL.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a>Параметры
 `pbIL`  
 [out] `true`, если этот `ICorDebugCode` представляет код, скомпилированный в MSIL; в противном случае `false`.

## <a name="requirements"></a>Требования

 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  

 **Заголовок.** CorDebug. idl, CorDebug. h  

 **Библиотечная** Коргуидс. lib  

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
 
