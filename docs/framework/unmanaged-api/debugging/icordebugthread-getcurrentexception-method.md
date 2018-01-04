---
title: "Метод ICorDebugThread::GetCurrentException"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetCurrentException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c18e2dfa68d425e5ec23d4573428018bc971f8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="bff2a-102">Метод ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="bff2a-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="bff2a-103">Получает указатель на интерфейс ICorDebugValue объекта, который представляет исключение, которое в настоящее время возникшего исключения в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="bff2a-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bff2a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bff2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bff2a-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="bff2a-106">[out] Указатель на адрес `ICorDebugValue` объект, который представляет исключение, которое в настоящее время вызвано управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bff2a-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bff2a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bff2a-107">Remarks</span></span>  
 <span data-ttu-id="bff2a-108">Объект исключения будет существовать с момента исключения до конца `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="bff2a-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="bff2a-109">Вычисление функции, которая выполняется с помощью методов ICorDebugEval будет очистить объекта исключения при установке и восстановите ее завершения.</span><span class="sxs-lookup"><span data-stu-id="bff2a-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="bff2a-110">Исключения могут быть вложенными (например, если исключение создается в фильтре или при вычислении функции), поэтому может существовать несколько необработанных исключений в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="bff2a-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="bff2a-111">`GetCurrentException`Возвращает наиболее текущее исключение.</span><span class="sxs-lookup"><span data-stu-id="bff2a-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="bff2a-112">Объект и тип исключения могут меняться на протяжении жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="bff2a-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="bff2a-113">Например после типа x создается исключение, общеязыковой среды выполнения (CLR) может возникнуть нехватка памяти и повысить уровень до исключения нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="bff2a-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bff2a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bff2a-114">Requirements</span></span>  
 <span data-ttu-id="bff2a-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bff2a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bff2a-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bff2a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bff2a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bff2a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bff2a-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bff2a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
