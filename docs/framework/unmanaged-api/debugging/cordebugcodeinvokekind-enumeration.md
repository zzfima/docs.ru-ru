---
title: Перечисление CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: 54332f5b3383f1c1513242a79cbd81eb8aa5c4f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179253"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>Перечисление CorDebugCodeInvokeKind
Описывает, каким образом экспортируемая функция вызывает управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,
    CODE_INVOKE_KIND_RETURN,
    CODE_INVOKE_KIND_TAILCALL,
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Если любой управляемый код вызывается этим методом, он должен находиться после явно заданных событий или точек останова.<br /><br /> — или —<br /><br /> Мы можем просто пропустить некоторую часть управляемого кода, который вызывает этот метод, так как не существует никакого простого способа останова на нем.<br /><br /> — или —<br /><br /> Метод может никогда не вызвать управляемый код.|  
|`CODE_INVOKE_KIND_RETURN`|Этот метод будет вызывать управляемый код с помощью инструкции return. Режим пропуска должен начаться в следующем управляемом коде.|  
|`CODE_INVOKE_KIND_TAILCALL`|Этот метод будет вызывать управляемый код с помощью вызова с префиксом tail. Пошаговый режим и режим пропуска любых инструкций вызова должны поступать в управляемый код.|  
  
## <a name="remarks"></a>Remarks  
 Этот перечисление используется методом [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) для предоставления информации о прохождении управляемого кода.  
  
> [!NOTE]
> Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления отладки](debugging-enumerations.md)
- [Отладки](index.md)
