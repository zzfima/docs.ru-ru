---
title: Интерфейс ICorDebugRemoteTarget
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e2e6a4624403dcab30bdb7b6d3af0226204cac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744643"
---
# <a name="icordebugremotetarget-interface"></a>Интерфейс ICorDebugRemoteTarget
Предоставляет методы, позволяющие разработчикам отлаживать приложения на основе Silverlight в среде CLR (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorDebugRemoteTarget::GetHostName](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|Возвращает имя узла или IP-адрес удаленного компьютера.|  
  
## <a name="remarks"></a>Примечания  
 Отладка в смешанном режиме (то есть управляемого и машинного кода) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от — x86 (например, IA-64 и AMD64).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl  
  
 **Библиотека:** : CorGuids.lib  
  
 **Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
