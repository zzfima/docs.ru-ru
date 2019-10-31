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
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133487"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="1f969-102">Метод ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="1f969-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="1f969-103">Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="1f969-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f969-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f969-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f969-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f969-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="1f969-106">заполняет Указатель на адрес объекта `ICorDebugValue`, представляющий исключение, которое в данный момент вызывается управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="1f969-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f969-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="1f969-107">Remarks</span></span>  
 <span data-ttu-id="1f969-108">Объект исключения будет существовать с момента возникновения исключения до конца блока `catch`.</span><span class="sxs-lookup"><span data-stu-id="1f969-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="1f969-109">Вычисление функции, выполняемое методами ICorDebugEval, очистит объект исключения при установке и восстановит его по завершении.</span><span class="sxs-lookup"><span data-stu-id="1f969-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="1f969-110">Исключения могут быть вложенными (например, если исключение создается в фильтре или в вычислении функции), поэтому в одном потоке может быть несколько необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="1f969-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="1f969-111">`GetCurrentException` возвращает последнее исключение.</span><span class="sxs-lookup"><span data-stu-id="1f969-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="1f969-112">Объект и тип исключения могут меняться в течение всего времени существования исключения.</span><span class="sxs-lookup"><span data-stu-id="1f969-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="1f969-113">Например, после возникновения исключения типа x среда CLR может закончится нехваткой памяти и повысить ее до исключения нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="1f969-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f969-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f969-114">Requirements</span></span>  
 <span data-ttu-id="1f969-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f969-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f969-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f969-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f969-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f969-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f969-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f969-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
