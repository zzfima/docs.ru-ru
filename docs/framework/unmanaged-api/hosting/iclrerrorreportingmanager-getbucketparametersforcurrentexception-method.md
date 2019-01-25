---
title: Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec7e303e5145e16f4c17074d557410ffe4521c20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549841"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="e6311-102">Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="e6311-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="e6311-103">Возвращает сегмент Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="e6311-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="e6311-104">Объект *контейнеров* — это коллекция данные об ошибках, которая связана с дефектом кода.</span><span class="sxs-lookup"><span data-stu-id="e6311-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="e6311-105">*"Доктор Ватсон"* ссылается на набор технологий для сбора и анализа данных, связанный с исключением.</span><span class="sxs-lookup"><span data-stu-id="e6311-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6311-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6311-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6311-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6311-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="e6311-108">[out] Указатель на [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) структуру, которая содержит данные об ошибках для исключения.</span><span class="sxs-lookup"><span data-stu-id="e6311-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6311-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e6311-109">Requirements</span></span>  
 <span data-ttu-id="e6311-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6311-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6311-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6311-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6311-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6311-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6311-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6311-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6311-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e6311-114">See also</span></span>
- [<span data-ttu-id="e6311-115">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="e6311-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
