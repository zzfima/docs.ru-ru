---
title: "Указатель функции WAITORTIMERCALLBACK"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAITORTIMERCALLBACK
api_location: mscoree.dll
api_type: COM
f1_keywords: WAITORTIMERCALLBACK
helpviewer_keywords: WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f39c023c6911ca0bcc6b62a562785c069d846d15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="fa840-102">Указатель функции WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="fa840-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="fa840-103">Указывает на функцию, которая уведомляет основное приложение, время ожидания обработки (<xref:System.Threading.WaitHandle>) был сигнал или истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="fa840-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="fa840-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa840-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa840-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa840-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa840-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa840-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="fa840-107">[in] Указатель на объект, содержащий информацию, определенную средой размещения.</span><span class="sxs-lookup"><span data-stu-id="fa840-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="fa840-108">[in] `true` Если дескриптор ожидания истекло или `false` , если объект получил сигнал.</span><span class="sxs-lookup"><span data-stu-id="fa840-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa840-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa840-109">Remarks</span></span>  
 <span data-ttu-id="fa840-110">Функция, к которому `WAITORTIMERCALLBACK` точек — функция обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="fa840-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa840-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fa840-111">Requirements</span></span>  
 <span data-ttu-id="fa840-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa840-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa840-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fa840-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa840-114">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="fa840-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="fa840-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa840-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa840-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fa840-116">See Also</span></span>  
 [<span data-ttu-id="fa840-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="fa840-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
