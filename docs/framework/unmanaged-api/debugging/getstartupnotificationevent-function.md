---
title: "Функция GetStartupNotificationEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 809f34d265e0a1677d8b7fc78515b20df7353968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="8ed25-102">Функция GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="8ed25-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="8ed25-103">Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="8ed25-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ed25-104">Syntax</span></span>  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ed25-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ed25-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="8ed25-106">[in] Идентификатор целевого процесса, из которого следует получать уведомления при запуске среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8ed25-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="8ed25-107">[out] Указатель на дескриптор, который будет оповещаться средой CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="8ed25-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ed25-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8ed25-108">Return Value</span></span>  
 <span data-ttu-id="8ed25-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ed25-109">S_OK</span></span>  
 <span data-ttu-id="8ed25-110">Успешно получен дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="8ed25-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="8ed25-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8ed25-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="8ed25-112">`phStartupEvent` имеет значение null, или `debuggeePID` не ссылается на процесс, выполняющийся в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="8ed25-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="8ed25-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="8ed25-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8ed25-114">Не удалось получить дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="8ed25-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ed25-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ed25-115">Remarks</span></span>  
 <span data-ttu-id="8ed25-116">В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.</span><span class="sxs-lookup"><span data-stu-id="8ed25-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="8ed25-117">Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.</span><span class="sxs-lookup"><span data-stu-id="8ed25-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ed25-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8ed25-118">Requirements</span></span>  
 <span data-ttu-id="8ed25-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ed25-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ed25-120">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="8ed25-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="8ed25-121">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="8ed25-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="8ed25-122">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8ed25-122">**.NET Framework Versions:** 3.5 SP1</span></span>
