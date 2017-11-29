---
title: "Метод IMetaDataImport::GetMemberProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b52d3130400310379c69eb0202217d1cd37ff18d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="500ba-102">Метод IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="500ba-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="500ba-103">Возвращает сведения о метаданных, в том числе имя, двоичную подпись и относительный виртуальный адрес из <xref:System.Type> члена ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="500ba-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="500ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="500ba-104">Syntax</span></span>  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="500ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="500ba-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="500ba-106">[in] Токен, который ссылается на связанные метаданные для члена.</span><span class="sxs-lookup"><span data-stu-id="500ba-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="500ba-107">[out] Указатель на токен метаданных, представляющий класс элемента.</span><span class="sxs-lookup"><span data-stu-id="500ba-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="500ba-108">[out] Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="500ba-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="500ba-109">[in] Размер в расширенных символах с `szMember` буфера.</span><span class="sxs-lookup"><span data-stu-id="500ba-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="500ba-110">[out] Размер в расширенных символах возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="500ba-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="500ba-111">[out] Любые значения флага, применении к элементу.</span><span class="sxs-lookup"><span data-stu-id="500ba-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="500ba-112">[out] Указатель на двоичную подпись метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="500ba-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="500ba-113">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="500ba-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="500ba-114">[out] Указатель на относительный виртуальный адрес элемента.</span><span class="sxs-lookup"><span data-stu-id="500ba-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="500ba-115">[out] Любые флаги реализации метода, связанное с элементом.</span><span class="sxs-lookup"><span data-stu-id="500ba-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="500ba-116">[out] Флаг, обозначающий <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="500ba-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="500ba-117">[out] Постоянное строковое значение, возвращенное этим членом.</span><span class="sxs-lookup"><span data-stu-id="500ba-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="500ba-118">[out] Размер в символах `ppValue`, или нуль, если `ppValue` не содержит строку.</span><span class="sxs-lookup"><span data-stu-id="500ba-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="500ba-119">Требования</span><span class="sxs-lookup"><span data-stu-id="500ba-119">Requirements</span></span>  
 <span data-ttu-id="500ba-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="500ba-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="500ba-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="500ba-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="500ba-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="500ba-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="500ba-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="500ba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="500ba-124">См. также</span><span class="sxs-lookup"><span data-stu-id="500ba-124">See Also</span></span>  
 [<span data-ttu-id="500ba-125">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="500ba-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="500ba-126">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="500ba-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
