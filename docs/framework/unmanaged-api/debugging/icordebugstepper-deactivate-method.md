---
title: Метод ICorDebugStepper::Deactivate
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 1d75897e00c36bd5c484e837ee68e54443168e77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131755"
---
# <a name="icordebugstepperdeactivate-method"></a>Метод ICorDebugStepper::Deactivate
Заставляет этот объект ICorDebugStepper отменить последнюю полученную команду шага.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Заметки  
 Новая команда пошагового выполнения может быть выдана после отмены последней полученной команды Step.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
