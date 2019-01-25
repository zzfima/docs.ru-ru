---
title: Метод IMetaDataError::OnError
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ebb7fdbcf8c17991928df2dc621ec651b9cd4f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678724"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="8dc77-102">Метод IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="8dc77-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="8dc77-103">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="8dc77-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dc77-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8dc77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dc77-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="8dc77-106">[in] Значение HRESULT ошибки, возвращаемый вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="8dc77-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="8dc77-107">[in] Маркер метаданных объекта кода, который был их слияние, когда произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="8dc77-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc77-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8dc77-108">Requirements</span></span>  
 <span data-ttu-id="8dc77-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dc77-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc77-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8dc77-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8dc77-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8dc77-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8dc77-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc77-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc77-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8dc77-113">See also</span></span>
- [<span data-ttu-id="8dc77-114">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="8dc77-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
