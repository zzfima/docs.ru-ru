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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c884d07fa35c053b1a3b65c04426ac0e3712621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429677"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="553b4-102">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="553b4-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="553b4-103">Указывает на функцию, общие вызовы языка среды выполнения (CLR) чтобы указать, что инициализация либо начала или завершения.</span><span class="sxs-lookup"><span data-stu-id="553b4-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="553b4-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="553b4-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553b4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="553b4-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="553b4-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="553b4-106">Remarks</span></span>  
 <span data-ttu-id="553b4-107">Эта функция реализуется узлом.</span><span class="sxs-lookup"><span data-stu-id="553b4-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="553b4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="553b4-108">Requirements</span></span>  
 <span data-ttu-id="553b4-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="553b4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="553b4-110">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="553b4-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="553b4-111">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="553b4-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="553b4-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="553b4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553b4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="553b4-113">See Also</span></span>  
 [<span data-ttu-id="553b4-114">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="553b4-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="553b4-115">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="553b4-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
