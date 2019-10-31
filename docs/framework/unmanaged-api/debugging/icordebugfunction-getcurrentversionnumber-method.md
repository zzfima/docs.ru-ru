---
title: Метод ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: 0530ba742a739003bfa33079ad75cb1e6f5f5e59
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124023"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>Метод ICorDebugFunction::GetCurrentVersionNumber
Возвращает номер версии последнего изменения, внесенного в функцию, представленную этим объектом ICorDebugFunction.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pnCurrentVersion`  
 заполняет Указатель на целочисленное значение, которое является номером версии последнего изменения, внесенного в эту функцию.  
  
## <a name="remarks"></a>Заметки  
 Номер версии последнего изменения, внесенного в эту функцию, может быть больше номера версии самой функции. Для получения номера версии функции используйте метод [ICorDebugFunction2:: жетверсионнумбер](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) или метод [ICorDebugCode:: жетверсионнумбер](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
