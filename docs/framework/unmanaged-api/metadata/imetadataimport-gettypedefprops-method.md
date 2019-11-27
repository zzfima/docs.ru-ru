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
ms.openlocfilehash: c9ac624e17223def206e86fd92ee4fd2de7f6082
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436746"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="0a3f3-102">Метод IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="0a3f3-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="0a3f3-103">Возвращает сведения о метаданных для <xref:System.Type>, представленных указанным маркером TypeDef.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a3f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a3f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a3f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a3f3-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0a3f3-106">окне Токен TypeDef, представляющий тип, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="0a3f3-107">заполняет Буфер, содержащий имя типа.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="0a3f3-108">окне Размер в расширенных символах `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="0a3f3-109">заполняет Число расширенных символов, возвращаемых в `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="0a3f3-110">заполняет Указатель на любые флаги, изменяющие определение типа.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="0a3f3-111">Это значение является битовой маской из перечисления [кортипеаттр](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0a3f3-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="0a3f3-112">заполняет Токен метаданных TypeDef или TypeRef, представляющий базовый тип запрошенного типа.</span><span class="sxs-lookup"><span data-stu-id="0a3f3-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a3f3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0a3f3-113">Requirements</span></span>  
 <span data-ttu-id="0a3f3-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a3f3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a3f3-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="0a3f3-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a3f3-116">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0a3f3-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a3f3-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a3f3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3f3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0a3f3-118">See also</span></span>

- [<span data-ttu-id="0a3f3-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0a3f3-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0a3f3-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0a3f3-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
