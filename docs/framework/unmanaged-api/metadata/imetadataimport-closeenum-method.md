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
ms.openlocfilehash: 724660cd5703ee9b893493df5d583d97b5bdfb3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720526"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="ab436-102">Метод IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="ab436-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="ab436-103">Закрывает перечислитель, который определяется указанным дескриптором.</span><span class="sxs-lookup"><span data-stu-id="ab436-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab436-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab436-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab436-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab436-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ab436-106">[in] Дескриптор для перечислителя закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="ab436-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab436-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab436-107">Remarks</span></span>  
 <span data-ttu-id="ab436-108">Дескриптор, указанный по `hEnum` получается из предыдущего `Enum` *имя* вызов (например, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ab436-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab436-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ab436-109">Requirements</span></span>  
 <span data-ttu-id="ab436-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab436-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab436-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab436-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab436-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab436-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab436-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab436-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab436-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ab436-114">See also</span></span>
- [<span data-ttu-id="ab436-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ab436-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ab436-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ab436-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
