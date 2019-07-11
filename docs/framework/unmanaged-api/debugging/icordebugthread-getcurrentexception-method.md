---
title: Метод ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6d53ebfebb8c883065ce119c2338a2225f0472
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762480"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="ea4ce-102">Метод ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="ea4ce-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="ea4ce-103">Получает указатель на интерфейс ICorDebugValue объект, представляющий исключение, которое в настоящее время возникающего исключения в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea4ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea4ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea4ce-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="ea4ce-106">[out] Указатель на адрес `ICorDebugValue` , представляющий исключение, которое в настоящее время вызвано управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4ce-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea4ce-107">Remarks</span></span>  
 <span data-ttu-id="ea4ce-108">Объект исключения будет существовать с момента, возникает исключение, до конца `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="ea4ce-109">Вычисление функции, который выполняется с помощью методов ICorDebugEval будет очистить объекта исключения при установке и восстановите ее после завершения.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="ea4ce-110">Исключения могут быть вложенными, (например, если создается исключение в фильтре или при вычислении функции), поэтому может существовать несколько необработанных исключений в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="ea4ce-111">`GetCurrentException` Возвращает наиболее текущее исключение.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="ea4ce-112">Объект исключения и тип может изменяться в течение жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="ea4ce-113">Например после типа x создается исключение, общеязыковой среды выполнения (CLR) может возникнуть нехватка памяти и повысить его уровень до исключение out of memory.</span><span class="sxs-lookup"><span data-stu-id="ea4ce-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea4ce-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ea4ce-114">Requirements</span></span>  
 <span data-ttu-id="ea4ce-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea4ce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea4ce-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea4ce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea4ce-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea4ce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea4ce-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea4ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
