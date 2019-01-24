---
title: Метод IMetaDataAssemblyImport::CloseEnum
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 156b2274aa442d9efb129d51ccf5939a09ac7408
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710135"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="eba5f-102">Метод IMetaDataAssemblyImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="eba5f-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="eba5f-103">Освобождает ссылку на экземпляр указанного перечисления.</span><span class="sxs-lookup"><span data-stu-id="eba5f-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eba5f-104">Syntax</span></span>  
  
```  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eba5f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eba5f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="eba5f-106">[in] Экземпляр перечисления, будет закрыта.</span><span class="sxs-lookup"><span data-stu-id="eba5f-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eba5f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="eba5f-107">Requirements</span></span>  
 <span data-ttu-id="eba5f-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eba5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eba5f-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eba5f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eba5f-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eba5f-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eba5f-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eba5f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba5f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="eba5f-112">See also</span></span>
- [<span data-ttu-id="eba5f-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="eba5f-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
