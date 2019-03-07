---
title: Метод ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46852ed8ac53c3a7720edff4833f3dc3cce42bbb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475792"
---
# <a name="icordebugilframegetargument-method"></a>Метод ICorDebugILFrame::GetArgument
Получает значение указанного аргумента в кадре стека промежуточного языка MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwIndex`  
 [in] Индекс аргумента в кадре стека MSIL.  
  
 `ppValue`  
 [out] Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.  
  
## <a name="remarks"></a>Примечания  
 `GetArgument` Метод может использоваться в кадре стека MSIL или во фрейме скомпилированного just-in-time (JIT).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
