---
title: Метод IMetaDataImport::FindTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8159b5245598993a2075fb402b280f9ab4cb2cfa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782464"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="3488d-102">Метод IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="3488d-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="3488d-103">Возвращает указатель на TypeRef токен для <xref:System.Type> ссылки, который находится в указанной области и с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="3488d-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3488d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3488d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3488d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3488d-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="3488d-106">[in] Токен ModuleRef, AssemblyRef или TypeRef, который указывает модуль, сборки или типа, соответственно, в котором ссылаться на тип определен.</span><span class="sxs-lookup"><span data-stu-id="3488d-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="3488d-107">[in] Имя ссылки на тип для поиска.</span><span class="sxs-lookup"><span data-stu-id="3488d-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="3488d-108">[out] Указатель на соответствующий токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="3488d-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3488d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3488d-109">Requirements</span></span>  
 <span data-ttu-id="3488d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3488d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3488d-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3488d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3488d-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3488d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3488d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3488d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3488d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3488d-114">See also</span></span>

- [<span data-ttu-id="3488d-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3488d-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3488d-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3488d-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
