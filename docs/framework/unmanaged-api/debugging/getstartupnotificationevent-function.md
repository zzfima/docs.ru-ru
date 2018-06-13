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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3692471e0652a1a812b1d0cbed9e38cc32112ef4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404314"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="9a33b-102">Функция GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="9a33b-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="9a33b-103">Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="9a33b-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a33b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a33b-104">Syntax</span></span>  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a33b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a33b-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="9a33b-106">[in] Идентификатор целевого процесса, из которого следует получать уведомления при запуске среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9a33b-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="9a33b-107">[out] Указатель на дескриптор, который будет оповещаться средой CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="9a33b-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a33b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a33b-108">Return Value</span></span>  
 <span data-ttu-id="9a33b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a33b-109">S_OK</span></span>  
 <span data-ttu-id="9a33b-110">Успешно получен дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="9a33b-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="9a33b-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9a33b-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="9a33b-112">`phStartupEvent` имеет значение null, или `debuggeePID` не ссылается на процесс, выполняющийся в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="9a33b-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="9a33b-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="9a33b-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9a33b-114">Не удалось получить дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="9a33b-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a33b-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a33b-115">Remarks</span></span>  
 <span data-ttu-id="9a33b-116">В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.</span><span class="sxs-lookup"><span data-stu-id="9a33b-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="9a33b-117">Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.</span><span class="sxs-lookup"><span data-stu-id="9a33b-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a33b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9a33b-118">Requirements</span></span>  
 <span data-ttu-id="9a33b-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a33b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a33b-120">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="9a33b-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9a33b-121">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="9a33b-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9a33b-122">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9a33b-122">**.NET Framework Versions:** 3.5 SP1</span></span>
