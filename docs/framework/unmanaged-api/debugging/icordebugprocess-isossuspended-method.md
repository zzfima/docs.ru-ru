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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775574"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="94cda-102">Метод ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="94cda-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="94cda-103">Получает значение, указывающее, приостановлено ли указанный поток в результате остановки этого процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="94cda-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94cda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94cda-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94cda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94cda-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="94cda-106">[in] Идентификатор потока в вопросе.</span><span class="sxs-lookup"><span data-stu-id="94cda-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="94cda-107">[out] Указатель на логическое значение, которое является `true` значение, если указанный поток приостановленной; в противном случае \*`pbSuspended` является `false`.</span><span class="sxs-lookup"><span data-stu-id="94cda-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94cda-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="94cda-108">Remarks</span></span>  
 <span data-ttu-id="94cda-109">Если указанного потока приостановлено из-за остановки этого процесса отладчиком, счетчик приостановок Win32 указанного потока увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="94cda-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="94cda-110">Пользовательский интерфейс отладчика (UI) может потребоваться учесть эти сведения учетной записи, если она отображает операционной системы (ОС) приостановка счетчика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="94cda-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="94cda-111">`IsOSSuspended` Метод имеет смысл только в контексте отладка неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="94cda-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="94cda-112">При отладке управляемого кода, потоки, совместно приостановленной вместо ОС.</span><span class="sxs-lookup"><span data-stu-id="94cda-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94cda-113">Требования</span><span class="sxs-lookup"><span data-stu-id="94cda-113">Requirements</span></span>  
 <span data-ttu-id="94cda-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94cda-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94cda-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94cda-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94cda-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94cda-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94cda-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94cda-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
