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
ms.openlocfilehash: 5025b75106b2cb0853047a09ca263f795d99633f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441183"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="95081-102">Указатель функции LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="95081-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="95081-103">Указывает на функцию, которая уведомляет основное приложение начала выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="95081-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="95081-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95081-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95081-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95081-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95081-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="95081-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="95081-107">[in] Указатель на код, в которой было начато.</span><span class="sxs-lookup"><span data-stu-id="95081-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95081-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="95081-108">Remarks</span></span>  
 <span data-ttu-id="95081-109">Функция, к которому `LPTHREAD_START_ROUTINE` точек — функция обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="95081-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95081-110">Требования</span><span class="sxs-lookup"><span data-stu-id="95081-110">Requirements</span></span>  
 <span data-ttu-id="95081-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95081-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95081-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95081-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95081-113">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="95081-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="95081-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95081-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95081-115">См. также</span><span class="sxs-lookup"><span data-stu-id="95081-115">See Also</span></span>  
 [<span data-ttu-id="95081-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="95081-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
