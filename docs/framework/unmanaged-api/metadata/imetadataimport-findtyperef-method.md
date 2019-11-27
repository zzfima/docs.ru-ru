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
ms.openlocfilehash: 21a69d120cc732ca6659f77abc9f8ea0c993271e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437789"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="01bbc-102">Метод IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="01bbc-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="01bbc-103">Возвращает указатель на маркер TypeRef для ссылки <xref:System.Type>, которая находится в указанной области и имеет указанное имя.</span><span class="sxs-lookup"><span data-stu-id="01bbc-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01bbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01bbc-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01bbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01bbc-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="01bbc-106">окне Токен ModuleRef, AssemblyRef или TypeRef, указывающий модуль, сборку или тип соответственно, в котором определена ссылка на тип.</span><span class="sxs-lookup"><span data-stu-id="01bbc-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="01bbc-107">окне Имя искомой ссылки на тип.</span><span class="sxs-lookup"><span data-stu-id="01bbc-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="01bbc-108">заполняет Указатель на соответствующий токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="01bbc-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01bbc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="01bbc-109">Requirements</span></span>  
 <span data-ttu-id="01bbc-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01bbc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01bbc-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="01bbc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01bbc-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01bbc-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01bbc-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01bbc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bbc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="01bbc-114">See also</span></span>

- [<span data-ttu-id="01bbc-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="01bbc-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="01bbc-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="01bbc-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
