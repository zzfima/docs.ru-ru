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
ms.openlocfilehash: 193abe173b259ff2679642e229fce96151e37872
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179689"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="4d0e8-102">Метод IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="4d0e8-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="4d0e8-103">Перечисляет токены Signature, представляющие отдельные подписи в текущей области.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d0e8-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d0e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d0e8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4d0e8-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4d0e8-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="4d0e8-108">[out] Массив, используемый для хранения токенов подписи.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4d0e8-109">[in] Максимальный размер массива `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="4d0e8-110">[out] Количество подписи токенов, возвращаемых в `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d0e8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4d0e8-111">Return Value</span></span>  
  
|<span data-ttu-id="4d0e8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d0e8-112">HRESULT</span></span>|<span data-ttu-id="4d0e8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4d0e8-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures` <span data-ttu-id="4d0e8-114">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4d0e8-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4d0e8-116">В этом случае `pcSignatures` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d0e8-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d0e8-117">Remarks</span></span>  
 <span data-ttu-id="4d0e8-118">Маркеры подписи, создаваемые [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4d0e8-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0e8-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4d0e8-119">Requirements</span></span>  
 <span data-ttu-id="4d0e8-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d0e8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d0e8-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d0e8-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d0e8-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d0e8-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="4d0e8-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4d0e8-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d0e8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4d0e8-124">See also</span></span>

- [<span data-ttu-id="4d0e8-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4d0e8-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4d0e8-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4d0e8-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
