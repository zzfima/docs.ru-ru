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
ms.openlocfilehash: 0d62b9be1bef16014e2870c15a232bb46d4daf10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448756"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="3c2c6-102">Метод IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="3c2c6-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="3c2c6-103">Возвращает метаданные, связанные с членом, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c2c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c2c6-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3c2c6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c2c6-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="3c2c6-106">[in] Токен MemberRef для возврата связанные с ним метаданные.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="3c2c6-107">[out] Токен TypeDef или TypeRef или TypeSpec, представляющий класс, который объявляет член, или токен ModuleRef, представляющий класс модуля, который объявляет член или MethodDef, который представляет элемент.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="3c2c6-108">[out] Строковый буфер для имени элемента.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="3c2c6-109">[in] Запрошенный размер в расширенных символах с `szMember`.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="3c2c6-110">[out] Возвращаемый размер в расширенных символах с `szMember`.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="3c2c6-111">[out] Указатель на двоичную подпись метаданных для элемента.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="3c2c6-112">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="3c2c6-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c2c6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3c2c6-113">Requirements</span></span>  
 <span data-ttu-id="3c2c6-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c2c6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c2c6-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c2c6-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c2c6-116">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c2c6-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c2c6-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c2c6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2c6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3c2c6-118">See Also</span></span>  
 [<span data-ttu-id="3c2c6-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3c2c6-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3c2c6-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3c2c6-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
