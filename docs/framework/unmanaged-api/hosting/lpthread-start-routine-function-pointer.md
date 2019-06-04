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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a81e78c0a34f766e1598dd27506f62bd3132f348
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490156"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="83c8c-102">Указатель функции LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="83c8c-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="83c8c-103">Указывает на функцию, которая уведомляет основное приложение, который запущен поток для выполнения.</span><span class="sxs-lookup"><span data-stu-id="83c8c-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="83c8c-104">Этот указатель функции был объявлен устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="83c8c-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c8c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83c8c-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c8c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83c8c-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="83c8c-107">[in] Указатель на код, который начато выполнение.</span><span class="sxs-lookup"><span data-stu-id="83c8c-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83c8c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="83c8c-108">Remarks</span></span>  
 <span data-ttu-id="83c8c-109">Функция, которая `LPTHREAD_START_ROUTINE` точки — это функция обратного вызова и должны быть реализованы модулем записи ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="83c8c-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c8c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="83c8c-110">Requirements</span></span>  
 <span data-ttu-id="83c8c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c8c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c8c-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83c8c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83c8c-113">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="83c8c-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="83c8c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c8c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c8c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="83c8c-115">See also</span></span>

- [<span data-ttu-id="83c8c-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="83c8c-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
