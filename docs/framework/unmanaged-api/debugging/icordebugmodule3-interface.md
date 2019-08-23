---
title: Интерфейс ICorDebugModule3
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e51ff64115ce3417087eee6845aa802ad64f2a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960997"
---
# <a name="icordebugmodule3-interface"></a>Интерфейс ICorDebugModule3
Создает средство чтения символов для динамического модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorDebugModule3::CreateReaderForInMemorySymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|Создает средство чтения символов (обычно [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс логически расширяет интерфейсы "ICorDebugModule" и "ICorDebugModule2".  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **.NET Framework версии:** 4,5, 4, 3,5 SP1
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
