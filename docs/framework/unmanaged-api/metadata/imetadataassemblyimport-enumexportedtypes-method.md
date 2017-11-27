---
title: "Метод IMetaDataAssemblyImport::EnumExportedTypes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumExportedTypes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76c73cc3d13089b4a38a47d523d8baa77f6eed12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="864c4-102">Метод IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="864c4-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="864c4-103">Перечисляет экспортированные типы, на которые ссылается манифест сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="864c4-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="864c4-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="864c4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="864c4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="864c4-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="864c4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="864c4-107">Это должен быть значением null значения при `EnumExportedTypes` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="864c4-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="864c4-108">[out] Перечисление `mdExportedType` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="864c4-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="864c4-109">[in] Максимальное число `mdExportedType` маркеры, которые могут быть помещены в `rExportedTypes` массива.</span><span class="sxs-lookup"><span data-stu-id="864c4-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="864c4-110">[out] Число `mdExportedType` токены непосредственно в `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="864c4-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="864c4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="864c4-111">Return Value</span></span>  
  
|<span data-ttu-id="864c4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="864c4-112">HRESULT</span></span>|<span data-ttu-id="864c4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="864c4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="864c4-114">`EnumExportedTypes`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="864c4-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="864c4-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="864c4-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="864c4-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="864c4-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="864c4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="864c4-117">Requirements</span></span>  
 <span data-ttu-id="864c4-118">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="864c4-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="864c4-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="864c4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="864c4-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="864c4-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="864c4-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="864c4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864c4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="864c4-122">See Also</span></span>  
 [<span data-ttu-id="864c4-123">Imetadataassemblyimport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="864c4-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
