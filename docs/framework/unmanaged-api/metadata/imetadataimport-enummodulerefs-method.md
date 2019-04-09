---
title: Метод IMetaDataImport::EnumModuleRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d66d24da05bc3b8f0c3d0a828456d7c61613d219
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188315"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="fb70d-102">Метод IMetaDataImport::EnumModuleRefs</span><span class="sxs-lookup"><span data-stu-id="fb70d-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="fb70d-103">Перечисляет токены ModuleRef, представляющие импортируемые модули.</span><span class="sxs-lookup"><span data-stu-id="fb70d-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb70d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb70d-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb70d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb70d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fb70d-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="fb70d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fb70d-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="fb70d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="fb70d-108">[out] Массив, используемый для хранения токены ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="fb70d-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fb70d-109">[in] Максимальный размер массива `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="fb70d-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="fb70d-110">[out] Количество токены ModuleRef, возвращаемых в `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="fb70d-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb70d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb70d-111">Return Value</span></span>  
  
|<span data-ttu-id="fb70d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb70d-112">HRESULT</span></span>|<span data-ttu-id="fb70d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fb70d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumModuleRefs` <span data-ttu-id="fb70d-114">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fb70d-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fb70d-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="fb70d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fb70d-116">В этом случае `pcModuleRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="fb70d-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb70d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="fb70d-117">Requirements</span></span>  
 <span data-ttu-id="fb70d-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb70d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb70d-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb70d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb70d-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb70d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="fb70d-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fb70d-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb70d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="fb70d-122">See also</span></span>

- [<span data-ttu-id="fb70d-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="fb70d-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fb70d-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="fb70d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
