---
title: "Метод IMetaDataAssemblyImport::EnumManifestResources"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumManifestResources
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa31441d060744bb17fc26a61daa7e655aa378fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="b3c77-102">Метод IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="b3c77-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="b3c77-103">Получает указатель на перечислитель для ресурсов, на которые ссылается манифест текущей сборки.</span><span class="sxs-lookup"><span data-stu-id="b3c77-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3c77-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3c77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3c77-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b3c77-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="b3c77-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b3c77-107">Это должен быть значением null значения при `EnumManifestResources` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="b3c77-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="b3c77-108">[out] Массив, используемый для хранения `mdManifestResource` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="b3c77-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b3c77-109">[in] Максимальное число `mdManifestResource` маркеры, которые могут быть помещены в `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="b3c77-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b3c77-110">[out] Число `mdManifestResource` токены непосредственно в `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="b3c77-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3c77-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3c77-111">Return Value</span></span>  
  
|<span data-ttu-id="b3c77-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3c77-112">HRESULT</span></span>|<span data-ttu-id="b3c77-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="b3c77-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b3c77-114">`EnumManifestResources`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b3c77-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b3c77-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="b3c77-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b3c77-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="b3c77-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3c77-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b3c77-117">Requirements</span></span>  
 <span data-ttu-id="b3c77-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c77-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c77-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3c77-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3c77-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3c77-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3c77-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3c77-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c77-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b3c77-122">See Also</span></span>  
 [<span data-ttu-id="b3c77-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b3c77-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
