---
title: Метод IMetaDataImport::EnumTypeRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de0fe4a51fbb49e80377b6b434bf3b72ddb90f02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081627"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="a38f5-102">Метод IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="a38f5-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="a38f5-103">Перечисляет токены TypeRef, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a38f5-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a38f5-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a38f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a38f5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a38f5-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a38f5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a38f5-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="a38f5-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="a38f5-108">[out] Массив, используемый для хранения токенов TypeRef.</span><span class="sxs-lookup"><span data-stu-id="a38f5-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a38f5-109">[in] Максимальный размер массива `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="a38f5-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="a38f5-110">[out] Указатель на количество возвращаемых в токены TypeRef `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="a38f5-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a38f5-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a38f5-111">Return Value</span></span>  
  
|<span data-ttu-id="a38f5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a38f5-112">HRESULT</span></span>|<span data-ttu-id="a38f5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a38f5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a38f5-114">`EnumTypeRefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a38f5-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a38f5-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="a38f5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a38f5-116">В этом случае `pcTypeRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a38f5-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a38f5-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a38f5-117">Remarks</span></span>  
 <span data-ttu-id="a38f5-118">Лексема TypeRef представляет ссылку на тип.</span><span class="sxs-lookup"><span data-stu-id="a38f5-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38f5-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a38f5-119">Requirements</span></span>  
 <span data-ttu-id="a38f5-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a38f5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a38f5-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a38f5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a38f5-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a38f5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a38f5-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a38f5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38f5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a38f5-124">See also</span></span>

- [<span data-ttu-id="a38f5-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a38f5-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a38f5-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a38f5-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
