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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7abcb7b69d0f0f2c53cd236c9b4092a94e0f421c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044700"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="7d08b-102">Метод IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="7d08b-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="7d08b-103">Получает указатель на перечислитель для ресурсов, на которые ссылается манифест текущей сборки.</span><span class="sxs-lookup"><span data-stu-id="7d08b-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d08b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d08b-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="7d08b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d08b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7d08b-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="7d08b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7d08b-107">Это должно быть значение null значение, если `EnumManifestResources` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="7d08b-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="7d08b-108">[out] Массив, используемый для хранения `mdManifestResource` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="7d08b-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7d08b-109">[in] Максимальное число `mdManifestResource` маркеры, которые могут быть помещены в `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="7d08b-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7d08b-110">[out] Число `mdManifestResource` маркеры непосредственно в `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="7d08b-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d08b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7d08b-111">Return Value</span></span>  
  
|<span data-ttu-id="7d08b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d08b-112">HRESULT</span></span>|<span data-ttu-id="7d08b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7d08b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7d08b-114">`EnumManifestResources` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7d08b-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7d08b-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="7d08b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7d08b-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="7d08b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d08b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="7d08b-117">Requirements</span></span>  
 <span data-ttu-id="7d08b-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d08b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d08b-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7d08b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d08b-120">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d08b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d08b-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d08b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d08b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7d08b-122">See also</span></span>

- [<span data-ttu-id="7d08b-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="7d08b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
