---
title: Интерфейс ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8f3a881a1beceb7d4aa35e2bd9a5e9e5419a391
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654871"
---
# <a name="icordebugloadedmodule-interface"></a>Интерфейс ICorDebugLoadedModule
Предоставляет сведения о загруженном модуле.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод GetBaseAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|Получает базовый адрес загруженного модуля.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|Получает имя загруженного модуля.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|Возвращает размер загруженного модуля в байтах.|  
  
## <a name="remarks"></a>Примечания  
 Интерфейс `ICorDebugLoadedModule` реализуется с помощью отладчика и используется интерфейсами отладки среды CLR для получения сведений о загруженном модуле из отладчика.  
  
> [!NOTE]
>  Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
