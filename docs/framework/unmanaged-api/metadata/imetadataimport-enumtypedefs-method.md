---
title: "Метод IMetaDataImport::EnumTypeDefs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aeb0e3c2eab4cde219b050bcf0e50202fe2be3f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="ad309-102">Метод IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="ad309-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="ad309-103">Перечисляет токены TypeDef, представляющие все типы в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ad309-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad309-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad309-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad309-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad309-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ad309-106">[out] Указатель на новый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="ad309-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="ad309-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="ad309-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="ad309-108">[in] Массив, используемый для хранения токенов TypeDef.</span><span class="sxs-lookup"><span data-stu-id="ad309-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ad309-109">[in] Максимальный размер массива `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="ad309-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="ad309-110">[out] Число токены TypeDef, возвращаемых в `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="ad309-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad309-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ad309-111">Return Value</span></span>  
  
|<span data-ttu-id="ad309-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad309-112">HRESULT</span></span>|<span data-ttu-id="ad309-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="ad309-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ad309-114">`EnumTypeDefs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ad309-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ad309-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ad309-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ad309-116">В этом случае `pcTypeDefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ad309-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad309-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad309-117">Remarks</span></span>  
 <span data-ttu-id="ad309-118">Маркер TypeDef представляет тип, например класс или интерфейс, а также любой тип, добавленный посредством механизма расширяемости.</span><span class="sxs-lookup"><span data-stu-id="ad309-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad309-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ad309-119">Requirements</span></span>  
 <span data-ttu-id="ad309-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad309-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad309-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ad309-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad309-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad309-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad309-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad309-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad309-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ad309-124">See Also</span></span>  
 [<span data-ttu-id="ad309-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ad309-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ad309-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ad309-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
