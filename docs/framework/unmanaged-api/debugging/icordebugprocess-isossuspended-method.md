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
ms.openlocfilehash: 2b65a621541f2b4a800f6b3708a6b257374c5866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419823"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="0f308-102">Метод ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="0f308-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="0f308-103">Возвращает значение, указывающее, приостановлено ли заданный поток в результате остановки этого процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="0f308-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f308-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f308-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f308-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f308-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0f308-106">[in] Идентификатор потока в вопросе.</span><span class="sxs-lookup"><span data-stu-id="0f308-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="0f308-107">[out] Указатель на значение типа Boolean, `true` если заданный поток был приостановлен; в противном случае значение \*`pbSuspended` — `false`.</span><span class="sxs-lookup"><span data-stu-id="0f308-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f308-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f308-108">Remarks</span></span>  
 <span data-ttu-id="0f308-109">При приостановке указанного потока в результате остановки этого процесса отладчиком счетчика приостановок Win32 указанного потока увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="0f308-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="0f308-110">Пользовательский интерфейс (UI) отладчик может потребоваться учесть эти сведения учетной записи, если она отображает операционной системы (ОС) число приостановок работы потока для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0f308-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="0f308-111">`IsOSSuspended` Метод имеет смысл только в контексте неуправляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="0f308-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="0f308-112">При отладке управляемого кода, потоки совместно приостановленном, а не приостановлен ОС.</span><span class="sxs-lookup"><span data-stu-id="0f308-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f308-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0f308-113">Requirements</span></span>  
 <span data-ttu-id="0f308-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f308-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f308-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f308-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f308-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f308-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f308-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f308-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
