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
ms.openlocfilehash: e1455ce7c3b07809d1dead8e98019c991475eb02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="5aa51-102">Указатель функции WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="5aa51-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="5aa51-103">Указывает на функцию, которая уведомляет основное приложение, время ожидания обработки (<xref:System.Threading.WaitHandle>) был сигнал или истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="5aa51-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="5aa51-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aa51-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa51-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5aa51-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5aa51-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5aa51-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="5aa51-107">[in] Указатель на объект, содержащий информацию, определенную средой размещения.</span><span class="sxs-lookup"><span data-stu-id="5aa51-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="5aa51-108">[in] `true` Если дескриптор ожидания истекло или `false` , если объект получил сигнал.</span><span class="sxs-lookup"><span data-stu-id="5aa51-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa51-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5aa51-109">Remarks</span></span>  
 <span data-ttu-id="5aa51-110">Функция, к которому `WAITORTIMERCALLBACK` точек — функция обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="5aa51-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aa51-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5aa51-111">Requirements</span></span>  
 <span data-ttu-id="5aa51-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aa51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aa51-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5aa51-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5aa51-114">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="5aa51-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="5aa51-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aa51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa51-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5aa51-116">See Also</span></span>  
 [<span data-ttu-id="5aa51-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5aa51-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
