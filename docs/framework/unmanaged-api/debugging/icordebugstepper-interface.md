---
title: ICorDebugStepper интерфейс1
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 339b823e5e9f38ffd175c79e379e28ccc3565c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepper-interface1"></a>ICorDebugStepper интерфейс1
Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|В результате `ICorDebugStepper` для отмены последней команды шага, оно получено.|  
|[Метод IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Возвращает значение, указывающее, является ли это `ICorDebugStepper` в данный момент выполняет этап.|  
|[Метод SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Задает CorDebugIntercept значение, указывающее типы кода, для которого осуществляется пошаговое.|  
|[Метод SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Задает значение, указывающее, является ли вызовы [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) значения аргументов относительно машинный код или код на промежуточном языке (MSIL) метода, который является в настоящее время шаг.|  
|[Метод SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Задает значение CorDebugUnmappedStop, которое указывает тип несопоставимого кода, в котором выполнение будет остановлено.|  
|[Метод Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|В результате `ICorDebugStepper` на один шаг через содержащую и, при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.|  
|[Метод StepOut](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|В результате `ICorDebugStepper` один шаг через содержащую и завершается, когда текущий кадр возвращает управление в вызывающий кадр.|  
|[Метод StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|В результате `ICorDebugStepper` на один шаг через содержащую и возвратить при достижении кода за последним из указанных диапазонов.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugStepper` Интерфейс выполняет следующие функции:  
  
-   Он служит идентификатором на промежутке между выданный командой шага и завершением этой команды.  
  
-   Он обеспечивает центральный интерфейс для инкапсулирования всех шагов, которое может быть выполнено.  
  
-   Он предоставляет способ преждевременно отменить пошагового выполнения операции.  
  
 Может существовать несколько шагов на поток. Например может быть достигнута точка останова при шаг с обходом функции и пользователь может потребоваться запустить новую операцию пошагового выполнения внутри этой функции. Именно отладчика для определения способа обработки этой ситуации. Отладчик может потребоваться отменить исходную шаговую операцию или вложить две операции. `ICorDebugStepper` Интерфейс поддерживает две возможности.  
  
 Шаг может мигрировать между потоками, если общеязыковая среда выполнения (CLR) вызывает между потоками, упакованы.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
