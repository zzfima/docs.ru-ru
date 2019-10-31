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
ms.openlocfilehash: b24f8ed4f5e2c6e0022f5599f2ab8c44a30a561a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129281"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="954f4-102">Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="954f4-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="954f4-103">Возвращает контейнер Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="954f4-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="954f4-104">*Контейнер* — это коллекция данных об ошибках, которая связана с тем же дефектом кода.</span><span class="sxs-lookup"><span data-stu-id="954f4-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="954f4-105">*Watson* относится к набору технологий для сбора и анализа данных, связанных с исключением.</span><span class="sxs-lookup"><span data-stu-id="954f4-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="954f4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="954f4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="954f4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="954f4-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="954f4-108">заполняет Указатель на структуру [буккетпараметерс](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) , содержащую данные об ошибке для исключения.</span><span class="sxs-lookup"><span data-stu-id="954f4-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="954f4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="954f4-109">Requirements</span></span>  
 <span data-ttu-id="954f4-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="954f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="954f4-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="954f4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="954f4-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="954f4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="954f4-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="954f4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954f4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="954f4-114">See also</span></span>

- [<span data-ttu-id="954f4-115">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="954f4-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
