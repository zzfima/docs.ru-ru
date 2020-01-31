---
title: Перечисление CorDebugRegister
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
ms.openlocfilehash: 9af265144c9e38ffe132c16a318c374b08a920e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778255"
---
# <a name="cordebugregister-enumeration"></a>Перечисление CorDebugRegister
Указывает регистры, связанные с данной архитектурой процессора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|Регистр указателя инструкции на любом процессоре.|  
|`REGISTER_STACK_POINTER`|Регистр указателя стека на любом процессоре.|  
|`REGISTER_FRAME_POINTER`|Регистр указателя кадра на любом процессоре.|  
|`REGISTER_X86_EIP`|Регистр указателя инструкции на процессоре x86.|  
|`REGISTER_X86_ESP`|Регистр указателя стека на процессоре x86.|  
|`REGISTER_X86_EBP`|Регистр базового указателя на процессоре x86.|  
|`REGISTER_X86_EAX`|Регистр данных A на процессоре x86.|  
|`REGISTER_X86_ECX`|Регистр данных C на процессоре x86.|  
|`REGISTER_X86_EDX`|Регистр данных D на процессоре x86.|  
|`REGISTER_X86_EBX`|Регистр данных B на процессоре x86.|  
|`REGISTER_X86_ESI`|Регистр индекса источника на процессоре x86.|  
|`REGISTER_X86_EDI`|Регистр индекса назначения на процессоре x86.|  
|`REGISTER_X86_FPSTACK_0`|Нулевой регистр стека на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_1`|Регистр стека #1 на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_2`|Регистр стека #2 на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_3`|Регистр стека #3 на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_4`|Регистр стека #4 на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_5`|Регистр стека #5 на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_6`|Регистр стека #6 на процессоре x86 с плавающей запятой.|  
|`REGISTER_X86_FPSTACK_7`|Регистр стека #7 на процессоре x86 с плавающей запятой.|  
|`REGISTER_AMD64_RIP`|Регистр указателя инструкции на процессоре AMD64.|  
|`REGISTER_AMD64_RSP`|Регистр указателя стека на процессоре AMD64.|  
|`REGISTER_AMD64_RBP`|Регистр базового указателя на процессоре AMD64.|  
|`REGISTER_AMD64_RAX`|Регистр данных A на процессоре AMD64.|  
|`REGISTER_AMD64_RCX`|Регистр данных C на процессоре AMD64.|  
|`REGISTER_AMD64_RDX`|Регистр данных D на процессоре AMD64.|  
|`REGISTER_AMD64_RBX`|Регистр данных B на процессоре AMD64.|  
|`REGISTER_AMD64_RSI`|Регистр индекса источника на процессоре AMD64.|  
|`REGISTER_AMD64_RDI`|Регистр индекса назначения на процессоре AMD64.|  
|`REGISTER_AMD64_R8`|Регистр данных #8 на процессоре AMD64.|  
|`REGISTER_AMD64_R9`|Регистр данных #9 на процессоре AMD64.|  
|`REGISTER_AMD64_R10`|Регистр данных #10 на процессоре AMD64.|  
|`REGISTER_AMD64_R11`|Регистр данных #11 на процессоре AMD64.|  
|`REGISTER_AMD64_R12`|Регистр данных #12 на процессоре AMD64.|  
|`REGISTER_AMD64_R13`|Регистр данных #13 на процессоре AMD64.|  
|`REGISTER_AMD64_R14`|Регистр данных #14 на процессоре AMD64.|  
|`REGISTER_AMD64_R15`|Регистр данных #15 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM0`|Регистр мультимедиа #0 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM1`|Регистр мультимедиа #1 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM2`|Регистр мультимедиа #2 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM3`|Регистр мультимедиа #3 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM4`|Регистр мультимедиа #4 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM5`|Регистр мультимедиа #5 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM6`|Регистр мультимедиа #6 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM7`|Регистр мультимедиа #7 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM8`|Регистр мультимедиа #8 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM9`|Регистр мультимедиа #9 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM10`|Регистр мультимедиа #10 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM11`|Регистр мультимедиа #11 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM12`|Регистр мультимедиа #12 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM13`|Регистр мультимедиа #13 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM14`|Регистр мультимедиа #14 на процессоре AMD64.|  
|`REGISTER_AMD64_XMM15`|Регистр мультимедиа #15 на процессоре AMD64.|  
|`REGISTER_IA64_BSP`|Регистр указателя стека на процессоре IA-64.|  
|`REGISTER_IA64_R0`|Регистр данных #0 на процессоре IA-64.|  
|`REGISTER_IA64_F0`|Регистр данных с плавающей запятой #0 на процессоре IA-64.|  
|`REGISTER_ARM_PC`|Регистр счетчика команд (R15) на процессоре ARM.|  
|`REGISTER_ARM_SP`|Регистр указателя стека (R13) на процессоре ARM.|  
|`REGISTER_ARM_R0`|Регистр данных R0 на процессоре ARM.|  
|`REGISTER_ARM_R1`|Регистр данных R1 на процессоре ARM.|  
|`REGISTER_ARM_R2`|Регистр данных R2 на процессоре ARM.|  
|`REGISTER_ARM_R3`|Регистр данных R3 на процессоре ARM.|  
|`REGISTER_ARM_R4`|Регистр R4 на процессоре ARM.|  
|`REGISTER_ARM_R5`|Регистр R5 на процессоре ARM.|  
|`REGISTER_ARM_R6`|Регистр R6 на процессоре ARM.|  
|`REGISTER_ARM_R7`|Регистр R7 (указатель кадра THUMB) на процессоре ARM.|  
|`REGISTER_ARM_R8`|Регистр R8 на процессоре ARM.|  
|`REGISTER_ARM_R9`|Регистр R9 на процессоре ARM.|  
|`REGISTER_ARM_R10`|Регистр R10 на процессоре ARM.|  
|`REGISTER_ARM_R11`|Указатель кадра на процессоре ARM.|  
|`REGISTER_ARM_R12`|Регистр R12 на процессоре ARM.|  
|`REGISTER_ARM_LR`|Регистр связи (R14) на процессоре ARM.|  
  
## <a name="remarks"></a>Заметки  
 На процессоре IA-64 имеются 128 регистров данных общего назначения и 128 регистров данных с плавающей запятой, но используются только значения `REGISTER_IA64_R0` и `REGISTER_IA64_F0`. Другие значения можно определить следующим образом.  
  
- Добавьте номер регистра к `REGISTER_IA64_R0` для значений от `REGISTER_IA64_R1` до `REGISTER_IA64_R127`, которые соответствуют регистрам данных от #1 до #127 на процессоре IA-64.  
  
- Добавьте номер регистра к `REGISTER_IA64_F0` для значений от `REGISTER_IA64_F1` до `REGISTER_IA64_F127`, которые соответствуют регистрам данных с плавающей запятой от #1 до #127 на процессоре IA-64.  
  
 Например, если необходимо указать регистр данных #83 на процессоре IA-64, добавьте к `REGISTER_IA64_R0` число 83.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления отладки](debugging-enumerations.md)
