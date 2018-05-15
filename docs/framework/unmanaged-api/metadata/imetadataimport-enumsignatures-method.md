---
title: Метод IMetaDataImport::EnumSignatures
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d36270047c8af0580a1cc3b44aa303e5907f33fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="5f6e0-102">Метод IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="5f6e0-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="5f6e0-103">Перечисляет токены Signature, представляющие отдельные подписи в текущей области.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f6e0-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f6e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f6e0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5f6e0-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5f6e0-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="5f6e0-108">[out] Массив, используемый для хранения подписи токенов.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5f6e0-109">[in] Максимальный размер массива `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="5f6e0-110">[out] Число подписи маркеров, возвращаются в `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f6e0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5f6e0-111">Return Value</span></span>  
  
|<span data-ttu-id="5f6e0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f6e0-112">HRESULT</span></span>|<span data-ttu-id="5f6e0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5f6e0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5f6e0-114">`EnumSignatures` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5f6e0-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5f6e0-116">В этом случае `pcSignatures` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f6e0-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f6e0-117">Remarks</span></span>  
 <span data-ttu-id="5f6e0-118">Токены Signature созданные [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6e0-119">Требования</span><span class="sxs-lookup"><span data-stu-id="5f6e0-119">Requirements</span></span>  
 <span data-ttu-id="5f6e0-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6e0-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f6e0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f6e0-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f6e0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f6e0-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6e0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6e0-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5f6e0-124">See Also</span></span>  
 [<span data-ttu-id="5f6e0-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5f6e0-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5f6e0-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5f6e0-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
