---
title: Метод ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d04bc67013a2227f295ac3a41be027b9f9b04e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478730"
---
# <a name="icordebugtypegetbase-method"></a>Метод ICorDebugType::GetBase
Получает указатель интерфейса на ICorDebugType, представляющей базовый тип, в том случае, если таковой имеется, типа, представленного этим объектом `ICorDebugType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBase`  
 [out] Указатель на адрес `ICorDebugType` , представляющий базовый тип.  
  
## <a name="remarks"></a>Примечания  
 Поиск базового типа для типа полезен для реализации общей функциональности отладчика, такие как печать все поля объекта или его родительских классов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
