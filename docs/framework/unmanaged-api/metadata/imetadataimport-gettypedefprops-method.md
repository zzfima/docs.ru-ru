---
title: Метод IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777511"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="d7165-102">Метод IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="d7165-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="d7165-103">Возвращает сведения о метаданных для <xref:System.Type> представленного указанным токеном TypeDef.</span><span class="sxs-lookup"><span data-stu-id="d7165-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7165-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7165-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7165-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7165-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d7165-106">[in] Токен TypeDef, который представляет метаданные для возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="d7165-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="d7165-107">[out] Буфер, содержащий имя типа.</span><span class="sxs-lookup"><span data-stu-id="d7165-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="d7165-108">[in] Размер в расширенных символах `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="d7165-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="d7165-109">[out] Число расширенных символов, возвращаемых в `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="d7165-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="d7165-110">[out] Указатель на всех флагов изменить определение типа.</span><span class="sxs-lookup"><span data-stu-id="d7165-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="d7165-111">Это значение является битовой [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="d7165-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="d7165-112">[out] Определение типа или TypeRef токен метаданных, представляющий базовый тип запрошенного типа.</span><span class="sxs-lookup"><span data-stu-id="d7165-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7165-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d7165-113">Requirements</span></span>  
 <span data-ttu-id="d7165-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7165-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7165-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7165-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7165-116">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7165-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7165-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7165-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7165-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d7165-118">See also</span></span>

- [<span data-ttu-id="d7165-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d7165-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d7165-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d7165-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
