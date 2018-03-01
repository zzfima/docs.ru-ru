---
title: "Метод ICLRMetaHost::ExitProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2407dd8fb4911bd7e6d46c973ebbab836da4f8fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="4263f-102">Метод ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="4263f-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="4263f-103">Пытается корректно завершить работу всех загруженных сред выполнения и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="4263f-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="4263f-104">Заменяет [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="4263f-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4263f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4263f-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4263f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4263f-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="4263f-107">[in] Код выхода для процесса.</span><span class="sxs-lookup"><span data-stu-id="4263f-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4263f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4263f-108">Return Value</span></span>  
 <span data-ttu-id="4263f-109">Этот метод никогда не возвращает, поэтому его возвращаемое значение не определено.</span><span class="sxs-lookup"><span data-stu-id="4263f-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4263f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4263f-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4263f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4263f-111">Requirements</span></span>  
 <span data-ttu-id="4263f-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4263f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4263f-113">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4263f-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4263f-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4263f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4263f-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4263f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4263f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4263f-116">See Also</span></span>  
 [<span data-ttu-id="4263f-117">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="4263f-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="4263f-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="4263f-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
