---
title: "Метод IMetaDataError::OnError"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b6e136f3fd76b9eb2be1e49a48316dc65c481fc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="da2e9-102">Метод IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="da2e9-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="da2e9-103">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="da2e9-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da2e9-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da2e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da2e9-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="da2e9-106">[in] Значение HRESULT ошибки, возвращаемый вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="da2e9-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="da2e9-107">[in] Токен метаданных объекта кода объединенные возникшей ошибки.</span><span class="sxs-lookup"><span data-stu-id="da2e9-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2e9-108">Требования</span><span class="sxs-lookup"><span data-stu-id="da2e9-108">Requirements</span></span>  
 <span data-ttu-id="da2e9-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2e9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2e9-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="da2e9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da2e9-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da2e9-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da2e9-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2e9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2e9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="da2e9-113">See Also</span></span>  
 [<span data-ttu-id="da2e9-114">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="da2e9-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
