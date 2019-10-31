---
title: Метод ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 21da69d4bff0f17eb607dda45fb7dbafea8c59f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128774"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="24ebc-102">Метод ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="24ebc-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="24ebc-103">Возвращает значение, указывающее, был ли заданный поток приостановлен в результате остановки этого процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="24ebc-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ebc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24ebc-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ebc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24ebc-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="24ebc-106">окне Идентификатор рассматриваемого потока.</span><span class="sxs-lookup"><span data-stu-id="24ebc-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="24ebc-107">заполняет Указатель на логическое значение, которое `true`, если указанный поток был приостановлен; в противном случае \*`pbSuspended` `false`.</span><span class="sxs-lookup"><span data-stu-id="24ebc-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24ebc-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="24ebc-108">Remarks</span></span>  
 <span data-ttu-id="24ebc-109">Если указанный поток был приостановлен в результате остановки этого процесса отладчиком, счетчик приостановки Win32 указанного потока увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="24ebc-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="24ebc-110">Пользовательский интерфейс отладчика может захотеть использовать эту информацию при отображении счетчика приостановки операционной системы (ОС) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="24ebc-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="24ebc-111">Метод `IsOSSuspended` имеет смысл только в контексте неуправляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="24ebc-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="24ebc-112">Во время управляемой отладки потоки приостанавливаются совместно, а не с приостановленной ОС.</span><span class="sxs-lookup"><span data-stu-id="24ebc-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ebc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="24ebc-113">Requirements</span></span>  
 <span data-ttu-id="24ebc-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ebc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ebc-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24ebc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24ebc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ebc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ebc-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ebc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
