---
title: Указатель функции LPTHREAD_START_ROUTINE
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090883"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="fcb01-102">Указатель функции LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="fcb01-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="fcb01-103">Указывает на функцию, которая уведомляет узел о начале выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="fcb01-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="fcb01-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fcb01-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb01-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcb01-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcb01-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fcb01-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="fcb01-107">окне Указатель на код, который начал выполнять.</span><span class="sxs-lookup"><span data-stu-id="fcb01-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcb01-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="fcb01-108">Remarks</span></span>  
 <span data-ttu-id="fcb01-109">Функция, к которой `LPTHREAD_START_ROUTINE` Points, является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="fcb01-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcb01-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fcb01-110">Requirements</span></span>  
 <span data-ttu-id="fcb01-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcb01-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcb01-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fcb01-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcb01-113">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="fcb01-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="fcb01-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcb01-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb01-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fcb01-115">See also</span></span>

- [<span data-ttu-id="fcb01-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="fcb01-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
