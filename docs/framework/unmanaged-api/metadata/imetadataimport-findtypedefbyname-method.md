---
title: Метод IMetaDataImport::FindTypeDefByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f182dad17e28cc5d19393bb4e13d747e34249fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782482"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="5c14b-102">Метод IMetaDataImport::FindTypeDefByName</span><span class="sxs-lookup"><span data-stu-id="5c14b-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="5c14b-103">Возвращает указатель на метаданных TypeDef токен для <xref:System.Type> с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="5c14b-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c14b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c14b-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c14b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c14b-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="5c14b-106">[in] Имя типа, для которого необходимо получить токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="5c14b-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="5c14b-107">[in] Определение типа или TypeRef токен, представляющий включающего класса.</span><span class="sxs-lookup"><span data-stu-id="5c14b-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="5c14b-108">Если искомый тип не является вложенным классом, это значение равно NULL.</span><span class="sxs-lookup"><span data-stu-id="5c14b-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="5c14b-109">[out] Указатель на соответствующий токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="5c14b-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c14b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5c14b-110">Requirements</span></span>  
 <span data-ttu-id="5c14b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c14b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c14b-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5c14b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c14b-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c14b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c14b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c14b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c14b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5c14b-115">See also</span></span>

- [<span data-ttu-id="5c14b-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5c14b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5c14b-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5c14b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
