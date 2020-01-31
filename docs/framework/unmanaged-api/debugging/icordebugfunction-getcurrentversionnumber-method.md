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
ms.openlocfilehash: 5e080e9aa89816b24aa2eb1b6b1be823922e86fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794524"
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
 Номер версии последнего изменения, внесенного в эту функцию, может быть больше номера версии самой функции. Для получения номера версии функции используйте метод [ICorDebugFunction2:: жетверсионнумбер](icordebugfunction2-getversionnumber-method.md) или метод [ICorDebugCode:: жетверсионнумбер](icordebugcode-getversionnumber-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
