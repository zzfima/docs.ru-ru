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
ms.openlocfilehash: aa69eda974187748d7046c792fa16b7729e3deff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446886"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="4ac88-102">Метод IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="4ac88-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="4ac88-103">Возвращает сведения о метаданных для <xref:System.Type> представленного указанным токеном TypeDef.</span><span class="sxs-lookup"><span data-stu-id="4ac88-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ac88-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="4ac88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ac88-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4ac88-106">[in] Представляющий тип, для возврата метаданных для токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="4ac88-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="4ac88-107">[out] Буфер, содержащий имя типа.</span><span class="sxs-lookup"><span data-stu-id="4ac88-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="4ac88-108">[in] Размер в расширенных символах с `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="4ac88-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="4ac88-109">[out] Число расширенных символов, возвращаемых в `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="4ac88-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="4ac88-110">[out] Указатель на любой флаги, которые изменяют определения типа.</span><span class="sxs-lookup"><span data-stu-id="4ac88-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="4ac88-111">Это значение является битовой [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="4ac88-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="4ac88-112">[out] TypeDef или TypeRef токен метаданных, представляющий базовый тип запрошенного типа.</span><span class="sxs-lookup"><span data-stu-id="4ac88-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac88-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4ac88-113">Requirements</span></span>  
 <span data-ttu-id="4ac88-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ac88-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ac88-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ac88-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ac88-116">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ac88-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ac88-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ac88-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac88-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4ac88-118">See Also</span></span>  
 [<span data-ttu-id="4ac88-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4ac88-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4ac88-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4ac88-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
