---
title: Метод IMetaDataAssemblyImport::EnumExportedTypes
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1beb76012d5f0351ee644c8dea89cabdbe2c8970
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555028"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="5444a-102">Метод IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="5444a-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="5444a-103">Перечисляет экспортированные типы, упоминаемые в манифесте сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="5444a-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5444a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5444a-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5444a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5444a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5444a-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="5444a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5444a-107">Это должно быть значение null значение, если `EnumExportedTypes` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="5444a-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="5444a-108">[out] Перечисление `mdExportedType` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="5444a-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5444a-109">[in] Максимальное число `mdExportedType` маркеры, которые могут быть помещены в `rExportedTypes` массива.</span><span class="sxs-lookup"><span data-stu-id="5444a-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5444a-110">[out] Число `mdExportedType` маркеры непосредственно в `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="5444a-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5444a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5444a-111">Return Value</span></span>  
  
|<span data-ttu-id="5444a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5444a-112">HRESULT</span></span>|<span data-ttu-id="5444a-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="5444a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5444a-114">`EnumExportedTypes` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5444a-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5444a-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="5444a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5444a-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="5444a-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5444a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5444a-117">Requirements</span></span>  
 <span data-ttu-id="5444a-118">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5444a-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5444a-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5444a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5444a-120">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5444a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5444a-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5444a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5444a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5444a-122">See also</span></span>
- [<span data-ttu-id="5444a-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="5444a-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
