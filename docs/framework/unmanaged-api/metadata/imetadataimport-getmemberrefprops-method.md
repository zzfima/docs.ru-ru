---
title: Метод IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2c431abb7a4a872454b9c2689ee195ed36ef236
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177018"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="d78b0-102">Метод IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="d78b0-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="d78b0-103">Возвращает метаданные, связанные с членом, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="d78b0-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d78b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d78b0-104">Syntax</span></span>  
  
```  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d78b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d78b0-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="d78b0-106">[in] Токен MemberRef для возврата связанные метаданные для.</span><span class="sxs-lookup"><span data-stu-id="d78b0-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="d78b0-107">[out] Токен TypeDef или TypeRef или TypeSpec, который представляет класс, который объявляет член, или токен ModuleRef, представляющий класс модуля, который объявляет член, или MethodDef, представляемого члена.</span><span class="sxs-lookup"><span data-stu-id="d78b0-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="d78b0-108">[out] Строковый буфер для имени члена.</span><span class="sxs-lookup"><span data-stu-id="d78b0-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="d78b0-109">[in] Запрошенный размер в расширенных символах `szMember`.</span><span class="sxs-lookup"><span data-stu-id="d78b0-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="d78b0-110">[out] Возвращаемый размер в расширенных символах `szMember`.</span><span class="sxs-lookup"><span data-stu-id="d78b0-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="d78b0-111">[out] Указатель на двоичную подпись метаданных для элемента.</span><span class="sxs-lookup"><span data-stu-id="d78b0-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="d78b0-112">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d78b0-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d78b0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d78b0-113">Requirements</span></span>  
 <span data-ttu-id="d78b0-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d78b0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d78b0-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d78b0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d78b0-116">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d78b0-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d78b0-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d78b0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78b0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d78b0-118">See also</span></span>

- [<span data-ttu-id="d78b0-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d78b0-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d78b0-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d78b0-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
