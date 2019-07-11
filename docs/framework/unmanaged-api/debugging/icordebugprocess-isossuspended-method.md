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
ms.openlocfilehash: 275f62c8211f71f067d310dd4b3af2ddb11e93d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755460"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="9f371-102">Метод ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="9f371-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="9f371-103">Получает значение, указывающее, приостановлено ли указанный поток в результате остановки этого процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="9f371-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f371-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f371-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f371-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f371-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="9f371-106">[in] Идентификатор потока в вопросе.</span><span class="sxs-lookup"><span data-stu-id="9f371-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="9f371-107">[out] Указатель на логическое значение, которое является `true` значение, если указанный поток приостановленной; в противном случае \*`pbSuspended` является `false`.</span><span class="sxs-lookup"><span data-stu-id="9f371-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f371-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f371-108">Remarks</span></span>  
 <span data-ttu-id="9f371-109">Если указанного потока приостановлено из-за остановки этого процесса отладчиком, счетчик приостановок Win32 указанного потока увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="9f371-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="9f371-110">Пользовательский интерфейс отладчика (UI) может потребоваться учесть эти сведения учетной записи, если она отображает операционной системы (ОС) приостановка счетчика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f371-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="9f371-111">`IsOSSuspended` Метод имеет смысл только в контексте отладка неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9f371-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="9f371-112">При отладке управляемого кода, потоки, совместно приостановленной вместо ОС.</span><span class="sxs-lookup"><span data-stu-id="9f371-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f371-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9f371-113">Requirements</span></span>  
 <span data-ttu-id="9f371-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f371-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f371-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f371-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f371-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f371-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f371-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f371-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
