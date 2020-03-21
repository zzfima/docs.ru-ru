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
ms.openlocfilehash: a61254ba751e47b0089a3f7528aca337a32e2db3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175373"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="89952-102">Метод IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="89952-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="89952-103">Возвращает метаданные, связанные с членом, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="89952-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89952-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89952-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="89952-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89952-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="89952-106">(в) Токен MemberRef для возврата связанных метаданных для.</span><span class="sxs-lookup"><span data-stu-id="89952-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="89952-107">(ваут) Токен TypeDef или TypeRef или TypeSpec, представляющий класс, декларифицируемый членом, или токен ModuleRef, представляющий класс модуля, декларизируемый членом, или MethodDef, представляющий участника.</span><span class="sxs-lookup"><span data-stu-id="89952-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="89952-108">(ваут) Строка буфера для имени участника.</span><span class="sxs-lookup"><span data-stu-id="89952-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="89952-109">(в) Запрошенный размер в широких `szMember`символах .</span><span class="sxs-lookup"><span data-stu-id="89952-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="89952-110">(ваут) Возвращенный размер в широких `szMember`символах .</span><span class="sxs-lookup"><span data-stu-id="89952-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="89952-111">(ваут) Указатель на двоичную подпись метаданных для участника.</span><span class="sxs-lookup"><span data-stu-id="89952-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="89952-112">(ваут) Размер байтов `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="89952-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89952-113">Требования</span><span class="sxs-lookup"><span data-stu-id="89952-113">Requirements</span></span>  
 <span data-ttu-id="89952-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89952-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89952-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89952-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89952-116">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89952-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89952-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89952-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89952-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89952-118">See also</span></span>

- [<span data-ttu-id="89952-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="89952-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="89952-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="89952-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
