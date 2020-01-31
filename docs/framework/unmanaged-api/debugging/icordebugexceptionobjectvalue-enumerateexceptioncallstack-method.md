---
title: Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 57eb284bfe39ce92b2d6c03a2aeb4ae84d6aba91
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788666"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="69bcd-102">Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="69bcd-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="69bcd-103">Возвращает перечислитель для стека вызовов, внедренного в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="69bcd-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69bcd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69bcd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69bcd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69bcd-105">Parameters</span></span>  
 <span data-ttu-id="69bcd-106">ппкаллстаккенум</span><span class="sxs-lookup"><span data-stu-id="69bcd-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="69bcd-107">заполняет Указатель на адрес объекта интерфейса [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) , который является перечислителем трассировки стека для управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="69bcd-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69bcd-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="69bcd-108">Remarks</span></span>  
 <span data-ttu-id="69bcd-109">Если сведения о стеке вызовов недоступны, метод возвращает `S_OK`, а [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) — допустимый перечислитель с длиной 0.</span><span class="sxs-lookup"><span data-stu-id="69bcd-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="69bcd-110">Если методу не удается получить сведения о трассировке стека, возвращается значение `E_FAIL` и перечислитель не возвращается.</span><span class="sxs-lookup"><span data-stu-id="69bcd-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="69bcd-111">Объект [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) отвечает за декодирование данных трассировки стека из поля `_stackTrace` объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="69bcd-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69bcd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="69bcd-112">Requirements</span></span>  
 <span data-ttu-id="69bcd-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69bcd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69bcd-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69bcd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69bcd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69bcd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69bcd-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69bcd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69bcd-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="69bcd-117">See also</span></span>

- [<span data-ttu-id="69bcd-118">Интерфейс ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="69bcd-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="69bcd-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="69bcd-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
