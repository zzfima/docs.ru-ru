---
title: "Метод IMetaDataImport::CountEnum"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26e826417e6fb48eb261278988bc7c351ee663aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="a97c8-102">Метод IMetaDataImport::CountEnum</span><span class="sxs-lookup"><span data-stu-id="a97c8-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="a97c8-103">Возвращает число элементов в перечислении, которые были получены с помощью указанного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a97c8-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a97c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a97c8-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a97c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a97c8-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a97c8-106">[in] Дескриптор для перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a97c8-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="a97c8-107">[out] Число элементов, перечисленных.</span><span class="sxs-lookup"><span data-stu-id="a97c8-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a97c8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a97c8-108">Remarks</span></span>  
 <span data-ttu-id="a97c8-109">Дескриптор, указанный по `hEnum` получается из предыдущего `Enum` *имя* вызов (например, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="a97c8-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a97c8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a97c8-110">Requirements</span></span>  
 <span data-ttu-id="a97c8-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a97c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a97c8-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a97c8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a97c8-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a97c8-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a97c8-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a97c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97c8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a97c8-115">See Also</span></span>  
 [<span data-ttu-id="a97c8-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a97c8-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a97c8-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a97c8-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
