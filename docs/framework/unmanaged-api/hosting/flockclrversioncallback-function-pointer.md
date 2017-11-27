---
title: "Указатель функции FLockClrVersionCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FLockClrVersionCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FLockClrVersionCallback
helpviewer_keywords: FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1b97c509ea8ed2c43c30cab278048aeb4170a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="5a70d-102">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="5a70d-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="5a70d-103">Указывает на функцию, общие вызовы языка среды выполнения (CLR) чтобы указать, что инициализация либо начала или завершения.</span><span class="sxs-lookup"><span data-stu-id="5a70d-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="5a70d-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a70d-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a70d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a70d-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a70d-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a70d-106">Remarks</span></span>  
 <span data-ttu-id="5a70d-107">Эта функция реализуется узлом.</span><span class="sxs-lookup"><span data-stu-id="5a70d-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a70d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5a70d-108">Requirements</span></span>  
 <span data-ttu-id="5a70d-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a70d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a70d-110">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a70d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a70d-111">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="5a70d-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="5a70d-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a70d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a70d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5a70d-113">See Also</span></span>  
 [<span data-ttu-id="5a70d-114">LockClrVersion-функция</span><span class="sxs-lookup"><span data-stu-id="5a70d-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="5a70d-115">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5a70d-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
