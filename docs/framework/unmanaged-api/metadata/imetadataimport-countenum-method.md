---
title: Метод IMetaDataImport::CountEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: b780ca513d8a0b4f88e66594e86e9ff8290f6523
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177362"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="c0147-102">Метод IMetaDataImport::CountEnum</span><span class="sxs-lookup"><span data-stu-id="c0147-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="c0147-103">Получает количество элементов в перечислении, которое было извлечено указанным регистратором.</span><span class="sxs-lookup"><span data-stu-id="c0147-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0147-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0147-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0147-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0147-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c0147-106">(в) Ручка для регистратора.</span><span class="sxs-lookup"><span data-stu-id="c0147-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="c0147-107">(ваут) Количество перечисленных элементов.</span><span class="sxs-lookup"><span data-stu-id="c0147-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0147-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0147-108">Remarks</span></span>  
 <span data-ttu-id="c0147-109">Ручка, `hEnum` указанная, получена `Enum`из предыдущего вызова *Name* (например, [IMetaDataImport::EnumTypeDefs).](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)</span><span class="sxs-lookup"><span data-stu-id="c0147-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0147-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c0147-110">Requirements</span></span>  
 <span data-ttu-id="c0147-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0147-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0147-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0147-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0147-113">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0147-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0147-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0147-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0147-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0147-115">See also</span></span>

- [<span data-ttu-id="c0147-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c0147-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c0147-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c0147-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
