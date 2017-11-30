---
title: "Метод ICLRDebugManager::SetSymbolReadingPolicy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetSymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d116883c39b4400451ede07df83ac77893ce285c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="7682c-102">Метод ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="7682c-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="7682c-103">Задает политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="7682c-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="7682c-104">Политика определяет, включены ли сведения о номерах строк и файлах в стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="7682c-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7682c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7682c-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7682c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7682c-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="7682c-107">[in] Член [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="7682c-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7682c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7682c-108">Return Value</span></span>  
  
|<span data-ttu-id="7682c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7682c-109">HRESULT</span></span>|<span data-ttu-id="7682c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7682c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7682c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7682c-111">S_OK</span></span>|<span data-ttu-id="7682c-112">`SetSymbolReadingPolicy`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7682c-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="7682c-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7682c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7682c-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7682c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7682c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7682c-115">E_FAIL</span></span>|<span data-ttu-id="7682c-116">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7682c-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7682c-117">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7682c-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7682c-118">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7682c-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7682c-119">Требования</span><span class="sxs-lookup"><span data-stu-id="7682c-119">Requirements</span></span>  
 <span data-ttu-id="7682c-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7682c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7682c-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7682c-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7682c-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7682c-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7682c-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7682c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7682c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7682c-124">See Also</span></span>  
 [<span data-ttu-id="7682c-125">Iclrdebugmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7682c-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
