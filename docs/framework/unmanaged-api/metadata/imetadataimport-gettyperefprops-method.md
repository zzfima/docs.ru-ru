---
title: Метод IMetaDataImport::GetTypeRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4d8829c9cb2818eafe98809c9a0d5fd8109d076
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778820"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="205c2-102">Метод IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="205c2-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="205c2-103">Возвращает метаданные, связанные с <xref:System.Type> ссылается указанный токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="205c2-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="205c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="205c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="205c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="205c2-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="205c2-106">[in] Токен TypeRef, который представляет метаданные для возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="205c2-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="205c2-107">[out] Указатель на область, в котором имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="205c2-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="205c2-108">Это значение является маркером AssemblyRef или ModuleRef, представляющий.</span><span class="sxs-lookup"><span data-stu-id="205c2-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="205c2-109">[out] Буфер, содержащий имя типа.</span><span class="sxs-lookup"><span data-stu-id="205c2-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="205c2-110">[in] Запрошенный размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="205c2-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="205c2-111">[out] Возвращаемый размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="205c2-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="205c2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="205c2-112">Requirements</span></span>  
 <span data-ttu-id="205c2-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="205c2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="205c2-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="205c2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="205c2-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="205c2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="205c2-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="205c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205c2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="205c2-117">See also</span></span>

- [<span data-ttu-id="205c2-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="205c2-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="205c2-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="205c2-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
