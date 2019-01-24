---
title: Интерфейс1 ICorDebugILFrame
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
ms.openlocfilehash: 73cf7f26b228fa5aa458a6de312df3bf777e0206
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580516"
---
# <a name="icordebugilframe-interface1"></a>Интерфейс1 ICorDebugILFrame
Представляет кадр стека кода промежуточного языка MSIL. Этот интерфейс является подклассом ICorDebugFrame-интерфейс.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Получает значение, указывающее, является ли он безопасным задать указатель инструкций в указанное расположение смещения.|  
|[Метод EnumerateArguments](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Получает перечислитель для аргументов в кадре.|  
|[Метод EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Получает перечислитель для локальных переменных в кадре.|  
|[Метод GetArgument](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Получает значение указанного аргумента в кадре стека MSIL.|  
|[Метод GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, как было получено значение указателя инструкций.|  
|[Метод GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Получает значение указанной локальной переменной в кадре стека MSIL.|  
|[Метод GetStackDepth](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Не реализовано.|  
|[Метод GetStackValue](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Не реализовано.|  
|[Метод SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Задает указатель инструкций в указанное расположение смещения в MSIL-код.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugILFrame` Это специализированный интерфейс ICorDebugFrame. Он используется для фреймов кода MSIL или just-in-time (JIT) компиляции кадров. Кадры JIT-компиляции реализовывать `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
