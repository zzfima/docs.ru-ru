---
title: Метод ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63300f65a811b80132e6569a599044ff2d480acd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471586"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a>Метод ICorDebugProcess6::MarkDebuggerAttached
Изменяет внутреннее состояние отлаживаемого кода таким образом, что метод <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> в библиотеке классов платформы .NET Framework возвращает `true`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `fIsAttached`  
 `true`, если метод <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> должен указать, что отладчик присоединен; в противном случае, `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод может возвращать значения, перечисленные в следующей таблице.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`S_OK`|Отлаживаемый код успешно обновлен.|  
|`CORDBG_E_MODULE_NOT_LOADED`|Сборка, содержащая метод <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>, не загружена, или другие ошибки, например, отсутствующие метаданные не позволяют ее распознать.<br /><br /> Эта ошибка является общей и носит информационный характер. Метод следует вызвать снова при загрузке дополнительных сборок.|  
|Другие ошибочные значения `HRESULT`.|Скорее всего, другие значения указывают некорректно работающие компоненты отладчика или компилятора.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
