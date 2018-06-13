---
title: Метод IMetaDataImport::CloseEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d81f9b0107fd927ddfda24cfd0ea3249e4c8651
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448821"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="a5622-102">Метод IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="a5622-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="a5622-103">Закрывает перечислитель, который определен указанным дескриптором.</span><span class="sxs-lookup"><span data-stu-id="a5622-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5622-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5622-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5622-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5622-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a5622-106">[in] Дескриптор для перечислителя для закрытия.</span><span class="sxs-lookup"><span data-stu-id="a5622-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5622-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5622-107">Remarks</span></span>  
 <span data-ttu-id="a5622-108">Дескриптор, указанный по `hEnum` получается из предыдущего `Enum` *имя* вызов (например, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="a5622-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5622-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a5622-109">Requirements</span></span>  
 <span data-ttu-id="a5622-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5622-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5622-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5622-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5622-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5622-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5622-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5622-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5622-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a5622-114">See Also</span></span>  
 [<span data-ttu-id="a5622-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a5622-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a5622-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a5622-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
