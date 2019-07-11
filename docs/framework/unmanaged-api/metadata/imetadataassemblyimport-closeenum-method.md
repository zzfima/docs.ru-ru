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
ms.openlocfilehash: 2b46d1f5fb797b74726070ae3cd9814dc46c8f03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778335"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="11c16-102">Метод IMetaDataAssemblyImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="11c16-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="11c16-103">Освобождает ссылку на экземпляр указанного перечисления.</span><span class="sxs-lookup"><span data-stu-id="11c16-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11c16-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11c16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11c16-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="11c16-106">[in] Экземпляр перечисления, будет закрыта.</span><span class="sxs-lookup"><span data-stu-id="11c16-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c16-107">Требования</span><span class="sxs-lookup"><span data-stu-id="11c16-107">Requirements</span></span>  
 <span data-ttu-id="11c16-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11c16-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c16-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11c16-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11c16-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11c16-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11c16-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11c16-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c16-112">См. также</span><span class="sxs-lookup"><span data-stu-id="11c16-112">See also</span></span>

- [<span data-ttu-id="11c16-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="11c16-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
