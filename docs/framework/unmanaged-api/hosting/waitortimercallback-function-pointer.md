---
title: Указатель функции WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24a2c3baec0d958302101c295966f945ae98fa78
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490714"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="30224-102">Указатель функции WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="30224-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="30224-103">Указывает на функцию, которая уведомляет основное приложение, дескриптор ожидания (<xref:System.Threading.WaitHandle>) был сигнал или истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="30224-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="30224-104">Этот указатель функции был объявлен устаревшим в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30224-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30224-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30224-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30224-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="30224-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="30224-107">[in] Указатель на объект, содержащий сведения, определенные средой размещения.</span><span class="sxs-lookup"><span data-stu-id="30224-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="30224-108">[in] `true` Если дескриптор ожидания истекло, или `false` Если объект получил сигнал.</span><span class="sxs-lookup"><span data-stu-id="30224-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30224-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="30224-109">Remarks</span></span>  
 <span data-ttu-id="30224-110">Функция, которая `WAITORTIMERCALLBACK` точки — это функция обратного вызова и должны быть реализованы модулем записи ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="30224-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30224-111">Требования</span><span class="sxs-lookup"><span data-stu-id="30224-111">Requirements</span></span>  
 <span data-ttu-id="30224-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30224-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30224-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30224-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30224-114">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="30224-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="30224-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30224-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30224-116">См. также</span><span class="sxs-lookup"><span data-stu-id="30224-116">See also</span></span>
- [<span data-ttu-id="30224-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="30224-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
