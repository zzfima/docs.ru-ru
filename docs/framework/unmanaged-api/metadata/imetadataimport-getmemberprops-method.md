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
ms.openlocfilehash: fcf32c4b27324ccc54eabbb248e8c9906cf693b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782363"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="65af6-102">Метод IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="65af6-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="65af6-103">Получает сведения, хранящиеся в метаданных для определения указанного элемента, включая имя, двоичную подпись и относительный виртуальный адрес из <xref:System.Type> члена ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="65af6-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="65af6-104">Это простой вспомогательный метод: Если *МБ* является MethodDef, затем **GetMethodProps** вызывается; Если *МБ* будет FieldDef **GetFieldProps** вызывается.</span><span class="sxs-lookup"><span data-stu-id="65af6-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="65af6-105">См. в статье эти другие методы, Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="65af6-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="65af6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65af6-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="65af6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="65af6-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="65af6-108">[in] Токен, который ссылается на связанные метаданные для члена.</span><span class="sxs-lookup"><span data-stu-id="65af6-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="65af6-109">[out] Указатель на токен метаданных, представляющий класс члена.</span><span class="sxs-lookup"><span data-stu-id="65af6-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="65af6-110">[out] Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="65af6-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="65af6-111">[in] Размер в расширенных символах `szMember` буфера.</span><span class="sxs-lookup"><span data-stu-id="65af6-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="65af6-112">[out] Размер в расширенных символах возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="65af6-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="65af6-113">[out] Любые значения флага, применения к элементу.</span><span class="sxs-lookup"><span data-stu-id="65af6-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="65af6-114">[out] Указатель на двоичную подпись метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="65af6-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="65af6-115">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="65af6-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="65af6-116">[out] Указатель на относительный виртуальный адрес элемента.</span><span class="sxs-lookup"><span data-stu-id="65af6-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="65af6-117">[out] Все флаги реализации метода, связанное с элементом.</span><span class="sxs-lookup"><span data-stu-id="65af6-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="65af6-118">[out] Флаг, который помечает <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="65af6-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="65af6-119">Он является одним из `ELEMENT_TYPE_*` значения.</span><span class="sxs-lookup"><span data-stu-id="65af6-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="65af6-120">[out] Постоянное строковое значение, возвращаемое этим элементом.</span><span class="sxs-lookup"><span data-stu-id="65af6-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="65af6-121">[out] Размер в символах `ppValue`, или нуль, если `ppValue` не содержит строку.</span><span class="sxs-lookup"><span data-stu-id="65af6-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65af6-122">Требования</span><span class="sxs-lookup"><span data-stu-id="65af6-122">Requirements</span></span>  
 <span data-ttu-id="65af6-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65af6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65af6-124">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65af6-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65af6-125">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65af6-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65af6-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65af6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65af6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="65af6-127">See also</span></span>

- [<span data-ttu-id="65af6-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="65af6-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="65af6-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="65af6-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
