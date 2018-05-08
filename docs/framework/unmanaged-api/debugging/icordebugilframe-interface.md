---
title: ICorDebugILFrame интерфейс1
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
ms.openlocfilehash: 4a97704e00278e19181df569f108f428cb1ec90f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframe-interface1"></a>ICorDebugILFrame интерфейс1
Представляет кадр стека кода промежуточного языка MSIL. Этот интерфейс является подклассом ICorDebugFrame-интерфейс.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Возвращает значение, указывающее, можно ли безопасно значение указателя инструкций заданное расположение смещения.|  
|[Метод EnumerateArguments](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Получает перечислитель для аргументов в кадре.|  
|[Метод EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Получает перечислитель для локальных переменных в кадре.|  
|[Метод GetArgument](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Возвращает значение указанного аргумента в кадре стека MSIL.|  
|[Метод GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, каким образом было получено значение указателя инструкций.|  
|[Метод GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Получает значение указанной локальной переменной в кадре стека MSIL.|  
|[Метод GetStackDepth](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Не реализовано.|  
|[Метод GetStackValue](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Не реализовано.|  
|[Метод SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Задает указатель инструкций заданное расположение смещения в MSIL-код.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugILFrame` Специализированный интерфейс ICorDebugFrame. Он используется для фреймов кода MSIL или для just-in-time (JIT) компиляции кадры. Кадры JIT-компиляции реализовывать `ICorDebugILFrame` интерфейс и ICorDebugNativeFrame-интерфейс.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
