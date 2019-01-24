---
title: Метод IMetaDataImport::GetMemberProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611414"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="85f4f-102">Метод IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="85f4f-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="85f4f-103">Возвращает сведения о метаданных, в том числе имя, двоичную подпись и относительный виртуальный адрес <xref:System.Type> члена ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="85f4f-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85f4f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="85f4f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85f4f-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="85f4f-106">[in] Токен, который ссылается на связанные метаданные для члена.</span><span class="sxs-lookup"><span data-stu-id="85f4f-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="85f4f-107">[out] Указатель на токен метаданных, представляющий класс члена.</span><span class="sxs-lookup"><span data-stu-id="85f4f-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="85f4f-108">[out] Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="85f4f-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="85f4f-109">[in] Размер в расширенных символах `szMember` буфера.</span><span class="sxs-lookup"><span data-stu-id="85f4f-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="85f4f-110">[out] Размер в расширенных символах возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="85f4f-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="85f4f-111">[out] Любые значения флага, применения к элементу.</span><span class="sxs-lookup"><span data-stu-id="85f4f-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="85f4f-112">[out] Указатель на двоичную подпись метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="85f4f-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="85f4f-113">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="85f4f-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="85f4f-114">[out] Указатель на относительный виртуальный адрес элемента.</span><span class="sxs-lookup"><span data-stu-id="85f4f-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="85f4f-115">[out] Все флаги реализации метода, связанное с элементом.</span><span class="sxs-lookup"><span data-stu-id="85f4f-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="85f4f-116">[out] Флаг, который помечает <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="85f4f-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="85f4f-117">[out] Постоянное строковое значение, возвращаемое этим элементом.</span><span class="sxs-lookup"><span data-stu-id="85f4f-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="85f4f-118">[out] Размер в символах `ppValue`, или нуль, если `ppValue` не содержит строку.</span><span class="sxs-lookup"><span data-stu-id="85f4f-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f4f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="85f4f-119">Requirements</span></span>  
 <span data-ttu-id="85f4f-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f4f-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85f4f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85f4f-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85f4f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85f4f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f4f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="85f4f-124">See also</span></span>
- [<span data-ttu-id="85f4f-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="85f4f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="85f4f-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="85f4f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
