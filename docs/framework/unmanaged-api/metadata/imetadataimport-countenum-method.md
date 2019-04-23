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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5015dc42497d269cdc2de944f14454558be6c07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142991"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="29e2a-102">Метод IMetaDataImport::CountEnum</span><span class="sxs-lookup"><span data-stu-id="29e2a-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="29e2a-103">Получает число элементов в перечислении, которое было получено с помощью указанного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="29e2a-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29e2a-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29e2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29e2a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="29e2a-106">[in] Дескриптор для перечислителя.</span><span class="sxs-lookup"><span data-stu-id="29e2a-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="29e2a-107">[out] Число элементов, перечисленных.</span><span class="sxs-lookup"><span data-stu-id="29e2a-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29e2a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="29e2a-108">Remarks</span></span>  
 <span data-ttu-id="29e2a-109">Дескриптор, указанный по `hEnum` получается из предыдущего `Enum` *имя* вызов (например, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="29e2a-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29e2a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="29e2a-110">Requirements</span></span>  
 <span data-ttu-id="29e2a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29e2a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29e2a-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="29e2a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29e2a-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29e2a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29e2a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29e2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e2a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="29e2a-115">See also</span></span>

- [<span data-ttu-id="29e2a-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="29e2a-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="29e2a-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="29e2a-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
