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
ms.openlocfilehash: f67f3ef57b4996eb4a956c596b76fb94b1bdfd7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738885"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="066f3-102">Функция GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="066f3-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="066f3-103">Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="066f3-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="066f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="066f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="066f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="066f3-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="066f3-106">[in] Идентификатор целевого процесса, из которого следует получать уведомления при запуске среды CLR.</span><span class="sxs-lookup"><span data-stu-id="066f3-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="066f3-107">[out] Указатель на дескриптор, который будет оповещаться средой CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="066f3-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="066f3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="066f3-108">Return Value</span></span>  
 <span data-ttu-id="066f3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="066f3-109">S_OK</span></span>  
 <span data-ttu-id="066f3-110">Успешно получен дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="066f3-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="066f3-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="066f3-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="066f3-112">`phStartupEvent` имеет значение null, или `debuggeePID` не ссылается на процесс, выполняющийся в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="066f3-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="066f3-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="066f3-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="066f3-114">Не удалось получить дескриптор события уведомления при запуске.</span><span class="sxs-lookup"><span data-stu-id="066f3-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="066f3-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="066f3-115">Remarks</span></span>  
 <span data-ttu-id="066f3-116">В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.</span><span class="sxs-lookup"><span data-stu-id="066f3-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="066f3-117">Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.</span><span class="sxs-lookup"><span data-stu-id="066f3-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="066f3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="066f3-118">Requirements</span></span>  
 <span data-ttu-id="066f3-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="066f3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="066f3-120">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="066f3-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="066f3-121">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="066f3-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="066f3-122">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="066f3-122">**.NET Framework Versions:** 3.5 SP1</span></span>
