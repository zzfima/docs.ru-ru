---
title: Перечисление CorDebugInterfaceVersion
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 70d9ee06d64cc80306a1988aa6e28859cadb9ecf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778405"
---
# <a name="cordebuginterfaceversion-enumeration"></a>Перечисление CorDebugInterfaceVersion
Указывает интерфейс, версию платформы .NET Framework или версию платформы .NET Framework, в которой был представлен интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo   
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot   
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a>Участники  
 В следующей таблице каждое значение перечисления сопоставляется с соответствующим интерфейсом. Кроме того, в таблице указана первая версия платформы .NET Framework, в которой поддерживался интерфейс.  
  
|Член|Что определяет|Версия платформы .NET Framework|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|Недопустимая версия платформы .NET Framework.|-|  
|`CorDebugVersion_1_0`|Версия платформы .NET Framework (включая все пакеты обновления) — 1.0.|1,0|  
|`CorDebugVersion_1_1`|Версия платформы .NET Framework (включая все пакеты обновления) — 1.1.|1.1|  
|`CorDebugVersion_2_0`|Версия платформы .NET Framework (включая все пакеты обновления) — 2.0.|2.0|  
|`CorDebugVersion_4_0`|Версия платформы .NET Framework (включая все пакеты обновления) — 4.|4|  
|`CorDebugVersion_4_5`|Версия платформы .NET Framework (включая все пакеты обновления) — 4.5.|4.5|  
|`ver_ICorDebugManagedCallback`|[ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)|1,0|  
|`ver_ICorDebugUnmanagedCallback`|[икордебугунманажедкаллбакк](icordebugunmanagedcallback-interface.md)|1,0|  
|`ver_ICorDebug`|[ICorDebug](icordebug-interface.md)|1,0|  
|`ver_ICorDebugController`|[ICorDebugController](icordebugcontroller-interface.md)|1,0|  
|`ver_ICorDebugAppDomain`|[ICorDebugAppDomain](icordebugappdomain-interface.md)|1,0|  
|`ver_ICorDebugAssembly`|[ICorDebugAssembly](icordebugassembly-interface.md)|1,0|  
|`ver_ICorDebugProcess`|[ICorDebugProcess](icordebugprocess-interface.md)|1,0|  
|`ver_ICorDebugBreakpoint`|[икордебугбреакпоинт](icordebugbreakpoint-interface.md)|1,0|  
|`ver_ICorDebugFunctionBreakpoint`|[ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)|1,0|  
|`ver_ICorDebugModuleBreakpoint`|[икордебугмодулебреакпоинт](icordebugmodulebreakpoint-interface.md)|1,0|  
|`ver_ICorDebugValueBreakpoint`|[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)|1,0|  
|`ver_ICorDebugStepper`|[ICorDebugStepper](icordebugstepper-interface.md)|1,0|  
|`ver_ICorDebugRegisterSet`|[ICorDebugRegisterSet](icordebugregisterset-interface.md)|1,0|  
|`ver_ICorDebugThread`|[ICorDebugThread](icordebugthread-interface.md)|1,0|  
|`ver_ICorDebugChain`|[ICorDebugChain](icordebugchain-interface.md)|1,0|  
|`ver_ICorDebugFrame`|[ICorDebugFrame](icordebugframe-interface.md)|1,0|  
|`ver_ICorDebugILFrame`|[ICorDebugILFrame](icordebugilframe-interface.md)|1,0|  
|`ver_ICorDebugNativeFrame`|[ICorDebugNativeFrame](icordebugnativeframe-interface.md)|1,0|  
|`ver_ICorDebugModule`|[ICorDebugModule](icordebugmodule-interface.md)|1,0|  
|`ver_ICorDebugFunction`|[ICorDebugFunction](icordebugfunction-interface1.md)|1,0|  
|`ver_ICorDebugCode`|[ICorDebugCode](icordebugcode-interface1.md)|1,0|  
|`ver_ICorDebugClass`|[ICorDebugClass](icordebugclass-interface.md)|1,0|  
|`ver_ICorDebugEval`|[ICorDebugEval](icordebugeval-interface.md)|1,0|  
|`ver_ICorDebugValue`|[ICorDebugValue](icordebugvalue-interface.md)|1,0|  
|`ver_ICorDebugGenericValue`|[ICorDebugGenericValue](icordebuggenericvalue-interface.md)|1,0|  
|`ver_ICorDebugReferenceValue`|[ICorDebugReferenceValue](icordebugreferencevalue-interface.md)|1,0|  
|`ver_ICorDebugHeapValue`|[ICorDebugHeapValue](icordebugheapvalue-interface.md)|1,0|  
|`ver_ICorDebugObjectValue`|[ICorDebugObjectValue](icordebugobjectvalue-interface.md)|1,0|  
|`ver_ICorDebugBoxValue`|[икордебугбоксвалуе](icordebugboxvalue-interface.md)|1,0|  
|`ver_ICorDebugStringValue`|[ICorDebugStringValue](icordebugstringvalue-interface.md)|1,0|  
|`ver_ICorDebugArrayValue`|[ICorDebugArrayValue](icordebugarrayvalue-interface.md)|1,0|  
|`ver_ICorDebugContext`|[икордебугконтекст](icordebugcontext-interface.md)|1,0|  
|`ver_ICorDebugEnum`|[ICorDebugEnum](icordebugenum-interface1.md)|1,0|  
|`ver_ICorDebugObjectEnum`|[икордебугобжектенум](icordebugobjectenum-interface.md)|1,0|  
|`ver_ICorDebugBreakpointEnum`|[ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)|1,0|  
|`ver_ICorDebugStepperEnum`|[икордебугстепперенум](icordebugstepperenum-interface.md)|1,0|  
|`ver_ICorDebugProcessEnum`|[икордебугпроцессенум](icordebugprocessenum-interface.md)|1,0|  
|`ver_ICorDebugThreadEnum`|[икордебугсреаденум](icordebugthreadenum-interface1.md)|1,0|  
|`ver_ICorDebugFrameEnum`|[ICorDebugFrameEnum](icordebugframeenum-interface.md)|1,0|  
|`ver_ICorDebugChainEnum`|[икордебугчаиненум](icordebugchainenum-interface.md)|1,0|  
|`ver_ICorDebugModuleEnum`|[икордебугмодулинум](icordebugmoduleenum-interface.md)|1,0|  
|`ver_ICorDebugValueEnum`|[ICorDebugValueEnum](icordebugvalueenum-interface.md)|1,0|  
|`ver_ICorDebugCodeEnum`|[икордебугкодинум](icordebugcodeenum-interface.md)|1,0|  
|`ver_ICorDebugTypeEnum`|[ICorDebugTypeEnum](icordebugtypeenum-interface.md)|1,0|  
|`ver_ICorDebugErrorInfoEnum`|[ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)|1,0|  
|`ver_ICorDebugAppDomainEnum`|[икордебугаппдомаиненум](icordebugappdomainenum-interface.md)|1,0|  
|`ver_ICorDebugAssemblyEnum`|[ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)|1,0|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[икордебужедитандконтинуирроринфо](icordebugeditandcontinueerrorinfo-interface.md)|1,0|  
|`ver_ICorDebugEditAndContinueSnapshot`|[Метод icordebugeditandcontinuesnapshot](icordebugeditandcontinuesnapshot-interface.md)|1,0|  
|`ver_ICorDebugManagedCallback2`|[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)|2.0|  
|`ver_ICorDebugAppDomain2`|[ICorDebugAppDomain2](icordebugappdomain2-interface.md)|2.0|  
|`ver_ICorDebugProcess2`|[ICorDebugProcess2](icordebugprocess2-interface1.md)|2.0|  
|`ver_ICorDebugStepper2`|[ICorDebugStepper2](icordebugstepper2-interface1.md)|2.0|  
|`ver_ICorDebugRegisterSet2`|[ICorDebugRegisterSet2](icordebugregisterset2-interface.md)|2.0|  
|`ver_ICorDebugThread2`|[ICorDebugThread2](icordebugthread2-interface.md)|2.0|  
|`ver_ICorDebugILFrame2`|[ICorDebugILFrame2](icordebugilframe2-interface.md)|2.0|  
|`ver_ICorDebugModule2`|[ICorDebugModule2](icordebugmodule2-interface.md)|2.0|  
|`ver_ICorDebugFunction2`|[ICorDebugFunction2](icordebugfunction2-interface.md)|2.0|  
|`ver_ICorDebugCode2`|[ICorDebugCode2](icordebugcode2-interface.md)|2.0|  
|`ver_ICorDebugClass2`|ICorDebugClass2|2.0|  
|`ver_ICorDebugValue2`|"ICorDebugValue2"|2.0|  
|`ver_ICorDebugEval2`|"ICorDebugEval2".|2.0|  
|`ver_ICorDebugObjectValue2`|ICorDebugObjectValue2|2.0|  
|`ver_ICorDebugThread3`|[ICorDebugThread3](icordebugthread3-interface.md)|4|  
|`ver_ICorDebugThread4`|[ICorDebugThread4](icordebugthread4-interface.md)|4|  
|`ver_ICorDebugStackWalk`|[икордебугстакквалк](icordebugstackwalk-interface.md)|4|  
|`ver_ICorDebugNativeFrame2`|[ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)|4|  
|`ver_ICorDebugInternalFrame2`|[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)|4|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[икордебугрунтимеунвиндаблефраме](icordebugruntimeunwindableframe-interface.md)|4|  
|`ver_ICorDebugHeapValue3`|[Интерфейс ICorDebugHeapValue3](icordebugheapvalue3-interface.md)|4|  
|`ver_ICorDebugBlockingObjectEnum`|[Интерфейс ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)|4|  
|`ver_ICorDebugValue3`|[ICorDebugValue3](icordebugvalue3-interface.md)|4|  
|`ver_ICorDebugComObjectValue`|[икордебугкомобжектвалуе](icordebugcomobjectvalue-interface.md)|4.5|  
|`ver_ICorDebugAppDomain3`|[ICorDebugAppDomain3](icordebugappdomain3-interface.md)|4.5|  
|`ver_ICorDebugCode3`|[ICorDebugCode3](icordebugcode3-interface.md)|4.5|  
|`ver_ICorDebugILFrame3`|[ICorDebugILFrame3](icordebugilframe3-interface.md)|4.5|  
|`CorDebugLatestVersion`|Версия платформы .NET Framework (включая все пакеты обновления) — самая последняя.|-|  
  
## <a name="remarks"></a>Заметки  
 Отладчик может использовать перечисление `CorDebugInterfaceVersion` в функции [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) для указания самой последней версии .NET Framework, поддерживаемой отладчиком.  
  
## <a name="interface-names"></a>Имена интерфейсов  
 Число в конце каждого имени интерфейсов в API отладки (например, "3" в `ICorDebugThread3`) обозначает версию интерфейса, а не платформы .NET Framework. Все имена интерфейсов в API отладки, кроме интерфейсов, появившихся в платформе .NET Framework версии 1, включают номера версий. Любые совпадения между номерами версий интерфейсов и номерами версий платформы .NET Framework являются случайными.  
  
- Интерфейсы, представленные в платформе .NET Framework версии 1.0, не включают цифры, потому что все они имеют версию 1.  
  
- Платформа .NET Framework версии 1.1 использует интерфейсы версии 1.0 и не вводит никаких новых интерфейсов отладки.  
  
- Четырнадцать интерфейсов отладки, представленных в платформе .NET Framework версии 2.0, являются логическими расширениями версии 1, а их названия содержат число "2".  
  
- Платформы .NET Framework версий 3.0 и 3.5 используют существующие интерфейсы платформы .NET Framework версии 2.0 и не вводят никаких новых интерфейсов.  
  
- В .NET Framework 4 введены разные версии интерфейса. Например, и `ICorDebugThread3`, и `ICorDebugThread4` отображаются как третья и четвертая версии интерфейса `ICorDebugThread`. В .NET Framework 4 также введена первая версия интерфейса `ICorDebugStackWalk` и вторая версия интерфейса `ICorDebugNativeFrame` (`ICorDebugNativeFrame2`).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления отладки](debugging-enumerations.md)
