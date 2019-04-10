---
title: Интерфейс ICorDebugStepper
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
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212522"
---
# <a name="icordebugstepper-interface"></a>Интерфейс ICorDebugStepper
Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|В результате `ICorDebugStepper` для отмены последней команды шага, оно получено.|  
|[Метод IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Получает значение, указывающее, является ли это `ICorDebugStepper` в данный момент выполняет этап.|  
|[Метод SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Задает CorDebugIntercept значение, указывающее типы кода, который осуществляется пошаговое.|  
|[Метод SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Задает значение, указывающее, является ли вызовы [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) значения аргументов, машинному коду или код на промежуточном языке (MSIL) метода, который является в настоящее время шаг.|  
|[Метод SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Задает CorDebugUnmappedStop значение, указывающее тип кода, в котором выполнение будет остановлено.|  
|[Метод Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|В результате `ICorDebugStepper` на один шаг через содержащую и при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.|  
|[Метод StepOut](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|В результате `ICorDebugStepper` один шаг через содержащую и завершенной, если текущий кадр возвращает управление в вызывающий кадр.|  
|[Метод StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|В результате `ICorDebugStepper` на один шаг через содержащую и возвратить при достижении кода за последним из указанных диапазонов.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugStepper` Интерфейс выполняет следующие функции:  
  
-   Он выступает в качестве идентификатора между командой шага, выданный и выполнении этой команды.  
  
-   Он обеспечивает центральный интерфейс для инкапсуляции всех пошагового выполнения, которое может быть выполнено.  
  
-   Она позволяет преждевременно отменить были выполнены вышеуказанные операции.  
  
 Может существовать несколько шагов на поток. Например могут быть точки останова при шаг с обходом функции и пользователь может потребоваться начать новую операцию пошагового выполнения внутри этой функции. Это отладчик для определения способа обработки такой ситуации. Отладчик может потребоваться отменить пошагового выполнения исходной операции или вложить две операции. `ICorDebugStepper` Интерфейс поддерживает две возможности.  
  
 Шаг может мигрировать между потоками, если среда CLR (CLR) делает вызов нескольких потоков, маршалируется.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
