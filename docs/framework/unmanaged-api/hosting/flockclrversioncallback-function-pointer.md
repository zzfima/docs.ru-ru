---
title: Указатель функции FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136519"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="a7c64-102">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="a7c64-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="a7c64-103">Указывает на функцию, которая вызывается средой CLR для указания того, что инициализация запущена или завершена.</span><span class="sxs-lookup"><span data-stu-id="a7c64-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="a7c64-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a7c64-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c64-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7c64-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a7c64-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="a7c64-106">Remarks</span></span>  
 <span data-ttu-id="a7c64-107">Эта функция реализуется узлом.</span><span class="sxs-lookup"><span data-stu-id="a7c64-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7c64-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a7c64-108">Requirements</span></span>  
 <span data-ttu-id="a7c64-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7c64-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7c64-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a7c64-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7c64-111">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="a7c64-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="a7c64-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7c64-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c64-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a7c64-113">See also</span></span>

- [<span data-ttu-id="a7c64-114">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="a7c64-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="a7c64-115">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="a7c64-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
