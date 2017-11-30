---
title: "Метод IMetaDataImport::EnumUserStrings"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUserStrings
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 48ec44d993c5cdc2c545125bf8b4bcb80e413f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="03861-102">Метод IMetaDataImport::EnumUserStrings</span><span class="sxs-lookup"><span data-stu-id="03861-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="03861-103">Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="03861-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03861-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03861-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03861-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03861-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="03861-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="03861-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="03861-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="03861-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="03861-108">[out] Массив, используемый для хранения строки токенов.</span><span class="sxs-lookup"><span data-stu-id="03861-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="03861-109">[in] Максимальный размер массива `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="03861-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="03861-110">[out] Число маркеров строки возвращаются в `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="03861-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03861-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03861-111">Return Value</span></span>  
  
|<span data-ttu-id="03861-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03861-112">HRESULT</span></span>|<span data-ttu-id="03861-113">Описание</span><span class="sxs-lookup"><span data-stu-id="03861-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="03861-114">`EnumUserStrings`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="03861-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="03861-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="03861-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="03861-116">В этом случае `pcStrings` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="03861-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03861-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="03861-117">Remarks</span></span>  
 <span data-ttu-id="03861-118">Маркеры строки создаются путем [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="03861-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="03861-119">Этот метод предназначен для использования обозревателя метаданных, а не с помощью компилятора.</span><span class="sxs-lookup"><span data-stu-id="03861-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03861-120">Требования</span><span class="sxs-lookup"><span data-stu-id="03861-120">Requirements</span></span>  
 <span data-ttu-id="03861-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03861-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03861-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03861-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03861-123">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03861-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03861-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03861-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03861-125">См. также</span><span class="sxs-lookup"><span data-stu-id="03861-125">See Also</span></span>  
 [<span data-ttu-id="03861-126">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03861-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="03861-127">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03861-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
