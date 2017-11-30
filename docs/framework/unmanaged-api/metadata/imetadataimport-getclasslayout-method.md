---
title: "Метод IMetaDataImport::GetClassLayout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cece37a6321fc68cbff2957f9753af5f2f916f5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="ecabc-102">Метод IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="ecabc-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="ecabc-103">Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="ecabc-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecabc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecabc-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecabc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecabc-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ecabc-106">[in] Токен TypeDef для класса с макетом для возврата.</span><span class="sxs-lookup"><span data-stu-id="ecabc-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="ecabc-107">[out] Одно из значений, 1, 2, 4, 8 или 16, представляющее размер пакета класса.</span><span class="sxs-lookup"><span data-stu-id="ecabc-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="ecabc-108">[out] Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) значения.</span><span class="sxs-lookup"><span data-stu-id="ecabc-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ecabc-109">[in] Максимальный размер массива `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="ecabc-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="ecabc-110">[out] Число элементов, возвращаемых в `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="ecabc-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="ecabc-111">[out] Размер в байтах класса, представленный `td`.</span><span class="sxs-lookup"><span data-stu-id="ecabc-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecabc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ecabc-112">Requirements</span></span>  
 <span data-ttu-id="ecabc-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecabc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecabc-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ecabc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ecabc-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecabc-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ecabc-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecabc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecabc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ecabc-117">See Also</span></span>  
 [<span data-ttu-id="ecabc-118">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ecabc-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ecabc-119">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ecabc-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
