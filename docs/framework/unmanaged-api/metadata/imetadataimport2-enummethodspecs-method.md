---
title: "Метод IMetaDataImport2::EnumMethodSpecs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e134d19eb6699f39e6d538f93f989b87ed8f37d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="f1d9f-102">Метод IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="f1d9f-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="f1d9f-103">Возвращает перечислитель для массива маркеров MethodSpec, связанных с указанным MethodDef или MemberRef токен.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1d9f-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1d9f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1d9f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f1d9f-106">[in, out] Указатель на перечислитель для `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="f1d9f-107">[in] Токен MemberRef или MethodDef, представляющий метод, маркеры которого MethodSpec для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="f1d9f-108">Если значение `tk` равно 0 (ноль), будут перечислены все маркеры MethodSpec в области.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="f1d9f-109">[out] Массив MethodSpec маркеры для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f1d9f-110">[in] Максимальное количество маркеров для размещения в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="f1d9f-111">[out] Возвращенное число маркеров помещаются в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1d9f-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1d9f-112">Return Value</span></span>  
  
|<span data-ttu-id="f1d9f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1d9f-113">HRESULT</span></span>|<span data-ttu-id="f1d9f-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="f1d9f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f1d9f-115">`EnumMethodSpecs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f1d9f-116">`phEnum`не имеет члена элементов.</span><span class="sxs-lookup"><span data-stu-id="f1d9f-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="f1d9f-117">В этом случае `pcMethodSpecs` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="f1d9f-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1d9f-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f1d9f-118">Requirements</span></span>  
 <span data-ttu-id="f1d9f-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d9f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d9f-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1d9f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1d9f-121">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1d9f-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1d9f-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d9f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d9f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f1d9f-123">See Also</span></span>  
 [<span data-ttu-id="f1d9f-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f1d9f-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="f1d9f-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f1d9f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
