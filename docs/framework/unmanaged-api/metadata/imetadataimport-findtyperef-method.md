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
ms.openlocfilehash: 375dbaf03384b4d05a7815a11612814d8b427170
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444447"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="2b160-102">Метод IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="2b160-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="2b160-103">Получает указатель на маркер TypeRef <xref:System.Type> ссылка в заданной области и с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="2b160-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b160-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b160-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b160-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b160-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="2b160-106">[in] Токен ModuleRef, AssemblyRef или TypeRef, который указывает модулю, сборки или типа, соответственно, в котором ссылаться на тип определен.</span><span class="sxs-lookup"><span data-stu-id="2b160-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="2b160-107">[in] Имя типа ссылки для поиска.</span><span class="sxs-lookup"><span data-stu-id="2b160-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="2b160-108">[out] Указатель на соответствующий маркер TypeRef.</span><span class="sxs-lookup"><span data-stu-id="2b160-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b160-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2b160-109">Requirements</span></span>  
 <span data-ttu-id="2b160-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b160-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b160-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b160-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b160-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b160-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b160-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b160-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b160-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2b160-114">See Also</span></span>  
 [<span data-ttu-id="2b160-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2b160-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2b160-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2b160-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
