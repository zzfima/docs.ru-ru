---
title: Функция GetStartupNotificationEvent
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: fb158b35165fb229fc78169e2508679b6749752e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122955"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="528b9-102">Функция GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="528b9-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="528b9-103">Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="528b9-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="528b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="528b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="528b9-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="528b9-106">[in] Идентификатор целевого процесса, из которого следует получать уведомления при запуске среды CLR.</span><span class="sxs-lookup"><span data-stu-id="528b9-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="528b9-107">[out] Указатель на дескриптор, который будет оповещаться средой CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="528b9-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="528b9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="528b9-108">Return Value</span></span>  
 <span data-ttu-id="528b9-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="528b9-109">S_OK</span></span>  
 <span data-ttu-id="528b9-110">Успешно получен дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="528b9-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="528b9-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="528b9-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="528b9-112">`phStartupEvent` имеет значение null, или `debuggeePID` не ссылается на процесс, выполняющийся в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="528b9-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="528b9-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="528b9-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="528b9-114">Не удалось получить дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="528b9-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="528b9-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="528b9-115">Remarks</span></span>  
 <span data-ttu-id="528b9-116">В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.</span><span class="sxs-lookup"><span data-stu-id="528b9-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="528b9-117">Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.</span><span class="sxs-lookup"><span data-stu-id="528b9-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="528b9-118">Требования</span><span class="sxs-lookup"><span data-stu-id="528b9-118">Requirements</span></span>  
 <span data-ttu-id="528b9-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="528b9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="528b9-120">**Заголовок:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="528b9-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="528b9-121">**Библиотека:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="528b9-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="528b9-122">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="528b9-122">**.NET Framework Versions:** 3.5 SP1</span></span>
