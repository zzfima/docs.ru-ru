---
title: Метод IMetaDataAssemblyImport::EnumManifestResources
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: 2748460826deb422a3851713db11343209fe449a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449551"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="95430-102">Метод IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="95430-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="95430-103">Возвращает указатель на перечислитель для ресурсов, указанных в текущем манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="95430-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95430-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95430-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="95430-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95430-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="95430-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="95430-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="95430-107">Это значение должно быть null, если метод `EnumManifestResources` вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="95430-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="95430-108">заполняет Массив, используемый для хранения маркеров метаданных `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="95430-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="95430-109">окне Максимальное число маркеров `mdManifestResource`, которые могут быть помещены в `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="95430-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="95430-110">заполняет Число маркеров `mdManifestResource`, фактически помещаемых в `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="95430-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95430-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95430-111">Return Value</span></span>  
  
|<span data-ttu-id="95430-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95430-112">HRESULT</span></span>|<span data-ttu-id="95430-113">Описание</span><span class="sxs-lookup"><span data-stu-id="95430-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="95430-114">`EnumManifestResources` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="95430-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="95430-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="95430-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="95430-116">В этом случае `pcTokens` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="95430-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95430-117">Требования</span><span class="sxs-lookup"><span data-stu-id="95430-117">Requirements</span></span>  
 <span data-ttu-id="95430-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95430-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95430-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="95430-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95430-120">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="95430-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95430-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95430-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95430-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="95430-122">See also</span></span>

- [<span data-ttu-id="95430-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="95430-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
