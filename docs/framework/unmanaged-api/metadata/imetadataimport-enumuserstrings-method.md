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
ms.workload: dotnet
ms.openlocfilehash: 3d9c802318203db2ccd6043cded3c7730b18b0cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="08316-102">Метод IMetaDataImport::EnumUserStrings</span><span class="sxs-lookup"><span data-stu-id="08316-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="08316-103">Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="08316-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08316-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08316-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08316-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08316-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="08316-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="08316-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="08316-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="08316-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="08316-108">[out] Массив, используемый для хранения строки токенов.</span><span class="sxs-lookup"><span data-stu-id="08316-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="08316-109">[in] Максимальный размер массива `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="08316-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="08316-110">[out] Число маркеров строки возвращаются в `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="08316-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08316-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08316-111">Return Value</span></span>  
  
|<span data-ttu-id="08316-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08316-112">HRESULT</span></span>|<span data-ttu-id="08316-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="08316-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="08316-114">`EnumUserStrings`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="08316-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="08316-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="08316-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="08316-116">В этом случае `pcStrings` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="08316-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08316-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="08316-117">Remarks</span></span>  
 <span data-ttu-id="08316-118">Маркеры строки создаются путем [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="08316-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="08316-119">Этот метод предназначен для использования обозревателя метаданных, а не с помощью компилятора.</span><span class="sxs-lookup"><span data-stu-id="08316-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08316-120">Требования</span><span class="sxs-lookup"><span data-stu-id="08316-120">Requirements</span></span>  
 <span data-ttu-id="08316-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08316-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08316-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08316-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08316-123">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08316-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08316-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08316-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08316-125">См. также</span><span class="sxs-lookup"><span data-stu-id="08316-125">See Also</span></span>  
 [<span data-ttu-id="08316-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08316-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="08316-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08316-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
