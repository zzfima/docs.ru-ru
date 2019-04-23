---
title: Метод ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9bd4cd44eca9b12ab8773fd75b6262579cfe8e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206087"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Метод ICorDebugAssembly3::GetContainerAssembly
Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAssembly`  
 Указатель на адрес ICorDebugAssembly объекта, представляющего контейнерную сборку, или **null** при сбое вызова метода.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если вызов метода выполнен успешно; в противном случае `S_FALSE`, и `ppAssembly` — **null**.  
  
## <a name="remarks"></a>Примечания  
 Если эта сборка была объединена с другими сборками внутри одиночной контейнерной сборки, этот метод возвращает контейнерную сборку. Дополнительные сведения и терминологию см. в разделе [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) раздела.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
