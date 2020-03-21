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
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175438"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="9fb4f-102">Метод IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="9fb4f-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="9fb4f-103">Перечисляет токены TypeRef, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fb4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fb4f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fb4f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fb4f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9fb4f-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9fb4f-107">Это должно быть NULL для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="9fb4f-108">(ваут) Массив, используемый для хранения токенов TypeRef.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9fb4f-109">[in] Максимальный размер массива `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="9fb4f-110">(ваут) Указатель на количество возвращенных токенов TypeRef в `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fb4f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9fb4f-111">Return Value</span></span>  
  
|<span data-ttu-id="9fb4f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fb4f-112">HRESULT</span></span>|<span data-ttu-id="9fb4f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9fb4f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9fb4f-114">`EnumTypeRefs`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9fb4f-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="9fb4f-116">В этом `pcTypeRefs` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fb4f-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="9fb4f-117">Remarks</span></span>  
 <span data-ttu-id="9fb4f-118">Токен TypeRef представляет собой отсылку к типу.</span><span class="sxs-lookup"><span data-stu-id="9fb4f-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fb4f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9fb4f-119">Requirements</span></span>  
 <span data-ttu-id="9fb4f-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fb4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fb4f-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9fb4f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fb4f-122">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9fb4f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9fb4f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fb4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb4f-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9fb4f-124">See also</span></span>

- [<span data-ttu-id="9fb4f-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9fb4f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9fb4f-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9fb4f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
