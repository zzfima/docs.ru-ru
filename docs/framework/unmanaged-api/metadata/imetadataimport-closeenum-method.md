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
ms.openlocfilehash: 7f27955467436d562c6a9acc9d7f666427e4c85b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770710"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="3b566-102">Метод IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="3b566-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="3b566-103">Закрывает перечислитель, который определяется указанным дескриптором.</span><span class="sxs-lookup"><span data-stu-id="3b566-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b566-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b566-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b566-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b566-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="3b566-106">[in] Дескриптор для перечислителя закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="3b566-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b566-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b566-107">Remarks</span></span>  
 <span data-ttu-id="3b566-108">Дескриптор, указанный по `hEnum` получается из предыдущего `Enum` *имя* вызов (например, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="3b566-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b566-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3b566-109">Requirements</span></span>  
 <span data-ttu-id="3b566-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b566-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b566-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b566-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b566-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b566-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b566-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b566-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b566-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3b566-114">See also</span></span>

- [<span data-ttu-id="3b566-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3b566-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3b566-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3b566-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
