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
ms.openlocfilehash: e02d7dd4b287d027b633ae9bf2e98e036062bdd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175412"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="84681-102">Метод IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="84681-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="84681-103">Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="84681-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84681-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84681-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84681-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84681-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="84681-106">(в) Токен TypeDef для класса с макетом для возврата.</span><span class="sxs-lookup"><span data-stu-id="84681-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="84681-107">(ваут) Одно из значений 1, 2, 4, 8 или 16, представляющее размер упаковки класса.</span><span class="sxs-lookup"><span data-stu-id="84681-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="84681-108">(ваут) Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) значений.</span><span class="sxs-lookup"><span data-stu-id="84681-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="84681-109">[in] Максимальный размер массива `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="84681-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="84681-110">(ваут) Количество элементов, `rFieldOffset`возвращенных в .</span><span class="sxs-lookup"><span data-stu-id="84681-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="84681-111">(ваут) Размер байтов класса, представленных `td`.</span><span class="sxs-lookup"><span data-stu-id="84681-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84681-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84681-112">Requirements</span></span>  
 <span data-ttu-id="84681-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84681-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84681-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84681-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84681-115">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84681-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84681-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84681-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84681-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84681-117">See also</span></span>

- [<span data-ttu-id="84681-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="84681-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="84681-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="84681-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
