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
ms.openlocfilehash: 276a69deecccc91b3c511403c2bd0d5c0baabd9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772799"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="3c76c-102">Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="3c76c-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="3c76c-103">Возвращает сегмент Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="3c76c-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="3c76c-104">Объект *контейнеров* — это коллекция данные об ошибках, которая связана с дефектом кода.</span><span class="sxs-lookup"><span data-stu-id="3c76c-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="3c76c-105">*"Доктор Ватсон"* ссылается на набор технологий для сбора и анализа данных, связанный с исключением.</span><span class="sxs-lookup"><span data-stu-id="3c76c-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c76c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c76c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c76c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c76c-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="3c76c-108">[out] Указатель на [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) структуру, которая содержит данные об ошибках для исключения.</span><span class="sxs-lookup"><span data-stu-id="3c76c-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c76c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3c76c-109">Requirements</span></span>  
 <span data-ttu-id="3c76c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c76c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c76c-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c76c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c76c-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c76c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c76c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c76c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c76c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3c76c-114">See also</span></span>

- [<span data-ttu-id="3c76c-115">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="3c76c-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
