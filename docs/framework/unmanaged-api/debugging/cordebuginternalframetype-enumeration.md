---
title: Перечисление CorDebugInternalFrameType
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
ms.openlocfilehash: 2be827e12db765485ee889d6a4a19a982dad5d54
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778367"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="4b0b8-102">Перечисление CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="4b0b8-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="4b0b8-103">Указывает тип кадра стека.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="4b0b8-104">Это перечисление используется методом [ICorDebugInternalFrame:: GetFrameType](icordebuginternalframe-getframetype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4b0b8-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b0b8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b0b8-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="4b0b8-106">Участники</span><span class="sxs-lookup"><span data-stu-id="4b0b8-106">Members</span></span>  
  
|<span data-ttu-id="4b0b8-107">Член</span><span class="sxs-lookup"><span data-stu-id="4b0b8-107">Member</span></span>|<span data-ttu-id="4b0b8-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4b0b8-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="4b0b8-109">Значение Null.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-109">A null value.</span></span> <span data-ttu-id="4b0b8-110">Метод `ICorDebugInternalFrame::GetFrameType` никогда не возвращает это значение.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="4b0b8-111">Фрейм заглушки "управляемый-к-неуправляемый".</span><span class="sxs-lookup"><span data-stu-id="4b0b8-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="4b0b8-112">Неуправляемый фрейм заглушки.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="4b0b8-113">Переход между доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="4b0b8-114">Вызов упрощенного метода.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="4b0b8-115">Начало вычисления функции.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="4b0b8-116">Внутренний вызов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="4b0b8-117">Начало инициализации класса.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="4b0b8-118">Порождается исключение.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="4b0b8-119">Кадр, используемый для управления доступом для кода.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="4b0b8-120">Среда выполнения — это JIT-компиляция метода.</span><span class="sxs-lookup"><span data-stu-id="4b0b8-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b0b8-121">Требования</span><span class="sxs-lookup"><span data-stu-id="4b0b8-121">Requirements</span></span>  
 <span data-ttu-id="4b0b8-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b0b8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b0b8-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b0b8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b0b8-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b0b8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b0b8-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b0b8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0b8-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b0b8-126">See also</span></span>

- [<span data-ttu-id="4b0b8-127">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="4b0b8-127">Debugging Enumerations</span></span>](debugging-enumerations.md)
