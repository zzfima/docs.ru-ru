---
title: Интерфейс ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a40436fcf1485c5d08d175b0396af2b6870c19a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917019"
---
# <a name="icordebugilframe-interface"></a>Интерфейс ICorDebugILFrame

Представляет кадр стека кода промежуточного языка MSIL. Этот интерфейс является подклассом интерфейса ICorDebugFrame.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.|  
|[Метод EnumerateArguments](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Возвращает перечислитель для аргументов в этом кадре.|  
|[Метод EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Возвращает перечислитель для локальных переменных в этом кадре.|  
|[Метод GetArgument](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Возвращает значение указанного аргумента в этом кадре стека MSIL.|  
|[Метод GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.|  
|[Метод GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Возвращает значение указанной локальной переменной в этом кадре стека MSIL.|  
|[Метод GetStackDepth](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Не реализовано.|  
|[Метод GetStackValue](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Не реализовано.|  
|[Метод SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugILFrame` Интерфейс является специализированным интерфейсом ICorDebugFrame. Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT. JIT-скомпилированные кадры реализуют `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
