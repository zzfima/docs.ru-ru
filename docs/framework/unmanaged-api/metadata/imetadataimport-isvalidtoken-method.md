---
title: "Метод IMetaDataImport::IsValidToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.IsValidToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61af4f5e68ebd5d5e4639cbc4c581d1c66358ff8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="6d2fb-102">Метод IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="6d2fb-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="6d2fb-103">Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.</span><span class="sxs-lookup"><span data-stu-id="6d2fb-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d2fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d2fb-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d2fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d2fb-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6d2fb-106">[in] Токен для проверки допустимости для ссылки.</span><span class="sxs-lookup"><span data-stu-id="6d2fb-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d2fb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d2fb-107">Return Value</span></span>  
 <span data-ttu-id="6d2fb-108">`true`Если `tk` токен правильность метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="6d2fb-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="6d2fb-109">В противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="6d2fb-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d2fb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6d2fb-110">Requirements</span></span>  
 <span data-ttu-id="6d2fb-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d2fb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d2fb-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d2fb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d2fb-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d2fb-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d2fb-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d2fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2fb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6d2fb-115">See Also</span></span>  
 [<span data-ttu-id="6d2fb-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6d2fb-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6d2fb-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6d2fb-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
