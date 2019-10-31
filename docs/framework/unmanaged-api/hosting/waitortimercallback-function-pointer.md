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
ms.openlocfilehash: db6a20dee21b6c8bbd55fa9b52a159a00fe310d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092037"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="c0ffb-102">Указатель функции WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="c0ffb-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="c0ffb-103">Указывает на функцию, которая уведомляет основное приложение о том, что дескриптор ожидания (<xref:System.Threading.WaitHandle>) имеет либо сигнал, либо время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c0ffb-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="c0ffb-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c0ffb-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ffb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0ffb-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0ffb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0ffb-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="c0ffb-107">окне Указатель на объект, содержащий сведения, определенные узлом.</span><span class="sxs-lookup"><span data-stu-id="c0ffb-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="c0ffb-108">[in] `true`, если истекло время ожидания дескриптора ожидания, или `false`, если он был сигнальным.</span><span class="sxs-lookup"><span data-stu-id="c0ffb-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0ffb-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0ffb-109">Remarks</span></span>  
 <span data-ttu-id="c0ffb-110">Функция, к которой `WAITORTIMERCALLBACK` Points, является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="c0ffb-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ffb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c0ffb-111">Requirements</span></span>  
 <span data-ttu-id="c0ffb-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ffb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ffb-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c0ffb-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0ffb-114">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="c0ffb-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="c0ffb-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ffb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ffb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c0ffb-116">See also</span></span>

- [<span data-ttu-id="c0ffb-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c0ffb-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
