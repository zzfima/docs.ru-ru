---
title: Метод ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737855"
---
# <a name="icordebugappdomaingetobject-method"></a>Метод ICorDebugAppDomain::GetObject
Получает указатель интерфейса на домен приложения среды выполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppObject`  
 [out] Указатель на адрес объекта интерфейса ICorDebugValue, который представляет домен приложения среды CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект еще не был создан для этого домена приложения, метод возвращает `S_FALSE` и помещает `NULL` в `*ppObject`.  
  
## <a name="remarks"></a>Примечания  
 Каждый домен приложения в процессе может иметь управляемый <xref:System.AppDomain?displayProperty=nameWithType> объекта в среде выполнения, который ее представляет. Эта функция возвращает объект интерфейс ICorDebugValue, соответствующий этому управляемых <xref:System.AppDomain?displayProperty=nameWithType> объекта.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
