---
title: Метод ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64c212d064ad658678926690d1e680afe27c7c99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219243"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="12691-102">Метод ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="12691-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="12691-103">Пытается корректно завершить работу всех загруженных сред выполнения и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="12691-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="12691-104">Заменяет [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="12691-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12691-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12691-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12691-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="12691-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="12691-107">[in] Код выхода для процесса.</span><span class="sxs-lookup"><span data-stu-id="12691-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12691-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="12691-108">Return Value</span></span>  
 <span data-ttu-id="12691-109">Этот метод никогда не возвращает, поэтому его возвращаемое значение не определено.</span><span class="sxs-lookup"><span data-stu-id="12691-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12691-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="12691-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12691-111">Требования</span><span class="sxs-lookup"><span data-stu-id="12691-111">Requirements</span></span>  
 <span data-ttu-id="12691-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12691-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12691-113">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="12691-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="12691-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12691-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12691-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12691-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12691-116">См. также</span><span class="sxs-lookup"><span data-stu-id="12691-116">See also</span></span>

- [<span data-ttu-id="12691-117">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="12691-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="12691-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="12691-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
