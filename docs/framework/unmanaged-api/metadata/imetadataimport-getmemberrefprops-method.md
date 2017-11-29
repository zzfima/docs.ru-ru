---
title: "Метод IMetaDataImport::GetMemberRefProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0b4b0399c22890226ad49ca0f3a5c709fb251653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="35932-102">Метод IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="35932-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="35932-103">Возвращает метаданные, связанные с членом, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="35932-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35932-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35932-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="35932-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35932-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="35932-106">[in] Токен MemberRef для возврата связанные с ним метаданные.</span><span class="sxs-lookup"><span data-stu-id="35932-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="35932-107">[out] Токен TypeDef или TypeRef или TypeSpec, представляющий класс, который объявляет член, или токен ModuleRef, представляющий класс модуля, который объявляет член или MethodDef, который представляет элемент.</span><span class="sxs-lookup"><span data-stu-id="35932-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="35932-108">[out] Строковый буфер для имени элемента.</span><span class="sxs-lookup"><span data-stu-id="35932-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="35932-109">[in] Запрошенный размер в расширенных символах с `szMember`.</span><span class="sxs-lookup"><span data-stu-id="35932-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="35932-110">[out] Возвращаемый размер в расширенных символах с `szMember`.</span><span class="sxs-lookup"><span data-stu-id="35932-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="35932-111">[out] Указатель на двоичную подпись метаданных для элемента.</span><span class="sxs-lookup"><span data-stu-id="35932-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="35932-112">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="35932-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35932-113">Требования</span><span class="sxs-lookup"><span data-stu-id="35932-113">Requirements</span></span>  
 <span data-ttu-id="35932-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35932-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35932-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35932-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35932-116">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35932-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35932-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35932-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35932-118">См. также</span><span class="sxs-lookup"><span data-stu-id="35932-118">See Also</span></span>  
 [<span data-ttu-id="35932-119">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="35932-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="35932-120">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="35932-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
