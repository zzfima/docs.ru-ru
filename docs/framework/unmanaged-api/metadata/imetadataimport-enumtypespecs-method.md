---
title: Метод IMetaDataImport::EnumTypeSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01151dc2fe6aa995285a34076527609816b2f3e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205164"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="11b05-102">Метод IMetaDataImport::EnumTypeSpecs</span><span class="sxs-lookup"><span data-stu-id="11b05-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="11b05-103">Перечисляет токены TypeSpec, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="11b05-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11b05-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11b05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11b05-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="11b05-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="11b05-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="11b05-107">Это значение должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="11b05-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="11b05-108">[out] Массив, используемый для хранения токенов TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="11b05-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="11b05-109">[in] Максимальный размер массива `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="11b05-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="11b05-110">[out] Количество токены TypeSpec, возвращаемых в `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="11b05-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11b05-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11b05-111">Return Value</span></span>  
  
|<span data-ttu-id="11b05-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11b05-112">HRESULT</span></span>|<span data-ttu-id="11b05-113">Описание</span><span class="sxs-lookup"><span data-stu-id="11b05-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeSpecs` <span data-ttu-id="11b05-114">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="11b05-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="11b05-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="11b05-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="11b05-116">В этом случае `pcTypeSpecs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="11b05-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11b05-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="11b05-117">Remarks</span></span>  
 <span data-ttu-id="11b05-118">Токены TypeSpec, создаваемые [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="11b05-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11b05-119">Требования</span><span class="sxs-lookup"><span data-stu-id="11b05-119">Requirements</span></span>  
 <span data-ttu-id="11b05-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11b05-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11b05-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11b05-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11b05-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11b05-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="11b05-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="11b05-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11b05-124">См. также</span><span class="sxs-lookup"><span data-stu-id="11b05-124">See also</span></span>

- [<span data-ttu-id="11b05-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="11b05-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="11b05-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="11b05-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
