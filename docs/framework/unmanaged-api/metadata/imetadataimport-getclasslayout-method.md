---
title: Метод IMetaDataImport::GetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52136426be9e8f220d8eb5fc93659f588f007498
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625123"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="94ff1-102">Метод IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="94ff1-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="94ff1-103">Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="94ff1-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ff1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94ff1-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="94ff1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94ff1-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="94ff1-106">[in] Токен TypeDef для класса с макетом для возврата.</span><span class="sxs-lookup"><span data-stu-id="94ff1-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="94ff1-107">[out] Одно из значений, 1, 2, 4, 8 или 16, представляющее размер пакета класса.</span><span class="sxs-lookup"><span data-stu-id="94ff1-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="94ff1-108">[out] Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) значения.</span><span class="sxs-lookup"><span data-stu-id="94ff1-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="94ff1-109">[in] Максимальный размер массива `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="94ff1-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="94ff1-110">[out] Число элементов, возвращаемых в `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="94ff1-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="94ff1-111">[out] Размер в байтах из класса, представленного параметром `td`.</span><span class="sxs-lookup"><span data-stu-id="94ff1-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94ff1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="94ff1-112">Requirements</span></span>  
 <span data-ttu-id="94ff1-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94ff1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94ff1-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94ff1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94ff1-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94ff1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94ff1-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94ff1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ff1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="94ff1-117">See also</span></span>
- [<span data-ttu-id="94ff1-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="94ff1-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="94ff1-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="94ff1-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
