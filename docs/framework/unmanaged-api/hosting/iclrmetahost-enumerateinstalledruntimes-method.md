---
title: Метод ICLRMetaHost::EnumerateInstalledRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ed4c09d910db6fa2e61d44e4ac777f9b6095a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434285"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="bc2d8-102">Метод ICLRMetaHost::EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="bc2d8-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="bc2d8-103">Возвращает перечисление, содержащее допустимое [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейса для каждой версии среды common language runtime (CLR), установленного на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc2d8-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc2d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc2d8-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc2d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc2d8-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="bc2d8-106">[out] Перечисление [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейсов для каждой версии среды CLR, которая установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc2d8-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc2d8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc2d8-107">Return Value</span></span>  
 <span data-ttu-id="bc2d8-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="bc2d8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bc2d8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc2d8-109">HRESULT</span></span>|<span data-ttu-id="bc2d8-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bc2d8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc2d8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc2d8-111">S_OK</span></span>|<span data-ttu-id="bc2d8-112">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="bc2d8-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="bc2d8-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="bc2d8-113">E_POINTER</span></span>|<span data-ttu-id="bc2d8-114">Параметр `ppEnumerator` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="bc2d8-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc2d8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="bc2d8-115">Requirements</span></span>  
 <span data-ttu-id="bc2d8-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc2d8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc2d8-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bc2d8-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bc2d8-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc2d8-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc2d8-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc2d8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2d8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bc2d8-120">See Also</span></span>  
 [<span data-ttu-id="bc2d8-121">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="bc2d8-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="bc2d8-122">Размещение</span><span class="sxs-lookup"><span data-stu-id="bc2d8-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
