---
title: "Метод ICorDebugProcess::IsOSSuspended"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsOSSuspended
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="06fe4-102">Метод ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="06fe4-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="06fe4-103">Возвращает значение, указывающее, приостановлено ли заданный поток в результате остановки этого процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="06fe4-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06fe4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06fe4-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06fe4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06fe4-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="06fe4-106">[in] Идентификатор потока в вопросе.</span><span class="sxs-lookup"><span data-stu-id="06fe4-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="06fe4-107">[out] Указатель на значение типа Boolean, `true` если заданный поток был приостановлен; в противном случае значение *`pbSuspended` — `false`.</span><span class="sxs-lookup"><span data-stu-id="06fe4-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise *`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06fe4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="06fe4-108">Remarks</span></span>  
 <span data-ttu-id="06fe4-109">При приостановке указанного потока в результате остановки этого процесса отладчиком счетчика приостановок Win32 указанного потока увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="06fe4-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="06fe4-110">Пользовательский интерфейс (UI) отладчик может потребоваться учесть эти сведения учетной записи, если она отображает операционной системы (ОС) число приостановок работы потока для пользователя.</span><span class="sxs-lookup"><span data-stu-id="06fe4-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="06fe4-111">`IsOSSuspended` Метод имеет смысл только в контексте неуправляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="06fe4-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="06fe4-112">При отладке управляемого кода, потоки совместно приостановленном, а не приостановлен ОС.</span><span class="sxs-lookup"><span data-stu-id="06fe4-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06fe4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="06fe4-113">Requirements</span></span>  
 <span data-ttu-id="06fe4-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06fe4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06fe4-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06fe4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06fe4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06fe4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06fe4-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06fe4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
