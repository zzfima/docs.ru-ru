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
ms.openlocfilehash: 68fe41afa1999295a32b930b779991e2bbddb19a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117330"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="89197-102">Метод IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="89197-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="89197-103">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="89197-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89197-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89197-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89197-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89197-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="89197-106">[in] Значение HRESULT ошибки, возвращаемый вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="89197-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="89197-107">[in] Маркер метаданных объекта кода, который был их слияние, когда произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="89197-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89197-108">Требования</span><span class="sxs-lookup"><span data-stu-id="89197-108">Requirements</span></span>  
 <span data-ttu-id="89197-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89197-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89197-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89197-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89197-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89197-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="89197-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="89197-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="89197-113">См. также</span><span class="sxs-lookup"><span data-stu-id="89197-113">See also</span></span>

- [<span data-ttu-id="89197-114">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="89197-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
