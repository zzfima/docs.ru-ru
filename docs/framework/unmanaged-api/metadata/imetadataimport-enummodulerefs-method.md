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
ms.openlocfilehash: 294156983507476b7ddfda3bc3cad16bb32f422b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445413"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="401ed-102">Метод IMetaDataImport::EnumModuleRefs</span><span class="sxs-lookup"><span data-stu-id="401ed-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="401ed-103">Перечисляет токены ModuleRef, представляющие импортируемые модули.</span><span class="sxs-lookup"><span data-stu-id="401ed-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="401ed-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="401ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="401ed-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="401ed-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="401ed-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="401ed-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="401ed-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="401ed-108">[out] Массив, используемый для хранения токены ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="401ed-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="401ed-109">[in] Максимальный размер массива `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="401ed-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="401ed-110">[out] Число токены ModuleRef, возвращаемых в `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="401ed-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="401ed-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="401ed-111">Return Value</span></span>  
  
|<span data-ttu-id="401ed-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="401ed-112">HRESULT</span></span>|<span data-ttu-id="401ed-113">Описание</span><span class="sxs-lookup"><span data-stu-id="401ed-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="401ed-114">`EnumModuleRefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="401ed-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="401ed-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="401ed-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="401ed-116">В этом случае `pcModuleRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="401ed-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="401ed-117">Требования</span><span class="sxs-lookup"><span data-stu-id="401ed-117">Requirements</span></span>  
 <span data-ttu-id="401ed-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="401ed-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401ed-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="401ed-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="401ed-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="401ed-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="401ed-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401ed-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401ed-122">См. также</span><span class="sxs-lookup"><span data-stu-id="401ed-122">See Also</span></span>  
 [<span data-ttu-id="401ed-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="401ed-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="401ed-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="401ed-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
