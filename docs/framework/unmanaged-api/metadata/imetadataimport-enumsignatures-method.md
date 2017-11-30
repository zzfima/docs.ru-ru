---
title: "Метод IMetaDataImport::EnumSignatures"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumSignatures
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25fb32b0780dc91157d39ece37f93d7abd582cf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="4f756-102">Метод IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="4f756-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="4f756-103">Перечисляет токены Signature, представляющие отдельные подписи в текущей области.</span><span class="sxs-lookup"><span data-stu-id="4f756-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f756-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f756-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f756-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f756-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4f756-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="4f756-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4f756-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="4f756-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="4f756-108">[out] Массив, используемый для хранения подписи токенов.</span><span class="sxs-lookup"><span data-stu-id="4f756-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4f756-109">[in] Максимальный размер массива `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="4f756-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="4f756-110">[out] Число подписи маркеров, возвращаются в `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="4f756-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f756-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f756-111">Return Value</span></span>  
  
|<span data-ttu-id="4f756-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f756-112">HRESULT</span></span>|<span data-ttu-id="4f756-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4f756-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4f756-114">`EnumSignatures`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4f756-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4f756-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="4f756-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4f756-116">В этом случае `pcSignatures` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="4f756-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f756-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f756-117">Remarks</span></span>  
 <span data-ttu-id="4f756-118">Токены Signature созданные [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4f756-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f756-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4f756-119">Requirements</span></span>  
 <span data-ttu-id="4f756-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f756-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f756-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f756-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f756-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f756-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f756-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f756-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f756-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4f756-124">See Also</span></span>  
 [<span data-ttu-id="4f756-125">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f756-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4f756-126">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f756-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
