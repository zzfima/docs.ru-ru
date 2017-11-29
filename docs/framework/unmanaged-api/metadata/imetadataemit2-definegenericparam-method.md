---
title: "Метод IMetaDataEmit2::DefineGenericParam"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineGenericParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 737e57b86e74cc7e4668589d16c2e2cb351162bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="f7fc0-102">Метод IMetaDataEmit2::DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="f7fc0-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="f7fc0-103">Создает определение для параметра универсального типа и возвращает маркер для этого параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7fc0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7fc0-104">Syntax</span></span>  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7fc0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7fc0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f7fc0-106">[in] `mdTypeDef` Или `mdMethodDef` токен, представляющий метод или конструктор, для которого необходимо определить универсальный параметр.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="f7fc0-107">[in] Индекс универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="f7fc0-108">[in] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее тип универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="f7fc0-109">[in] Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="f7fc0-110">[in] Этот параметр зарезервирован для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="f7fc0-111">[in] Нулем массив ограничения типа.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="f7fc0-112">Элементы массива должны быть `mdTypeDef`, `mdTypeRef`, или `mdTypeSpec` токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="f7fc0-113">[out] Токен, представляющий универсальный параметр.</span><span class="sxs-lookup"><span data-stu-id="f7fc0-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7fc0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f7fc0-114">Requirements</span></span>  
 <span data-ttu-id="f7fc0-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7fc0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7fc0-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f7fc0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7fc0-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7fc0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7fc0-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7fc0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fc0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f7fc0-119">See Also</span></span>  
 [<span data-ttu-id="f7fc0-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f7fc0-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="f7fc0-121">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f7fc0-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
