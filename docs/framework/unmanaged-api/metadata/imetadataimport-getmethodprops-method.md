---
title: Метод IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c61931f5f6a4bbbf66446d68b0d1b2d1df958a66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137927"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="936ea-102">Метод IMetaDataImport::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="936ea-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="936ea-103">Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="936ea-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="936ea-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="936ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="936ea-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="936ea-106">[in] Токен MethodDef, который представляет метод для возврата метаданных для.</span><span class="sxs-lookup"><span data-stu-id="936ea-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="936ea-107">[out] Указатель на токен TypeDef, представляющий тип, реализующий метод.</span><span class="sxs-lookup"><span data-stu-id="936ea-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="936ea-108">[out] Указатель на буфер, который имеет имя метода.</span><span class="sxs-lookup"><span data-stu-id="936ea-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="936ea-109">[in] Запрошенный размер `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="936ea-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="936ea-110">[out] Указатель на размер в расширенных символах `szMethod`, или в случае усечения фактическое число расширенных символов в имени метода.</span><span class="sxs-lookup"><span data-stu-id="936ea-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="936ea-111">[out] Указатель на любой флаги, связанные с методом.</span><span class="sxs-lookup"><span data-stu-id="936ea-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="936ea-112">[out] Указатель на двоичную подпись метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="936ea-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="936ea-113">[out] Указатель на размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="936ea-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="936ea-114">[out] Указатель на относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="936ea-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="936ea-115">[out] Указатель на любой флаги реализации метода.</span><span class="sxs-lookup"><span data-stu-id="936ea-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="936ea-116">Требования</span><span class="sxs-lookup"><span data-stu-id="936ea-116">Requirements</span></span>  
 <span data-ttu-id="936ea-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="936ea-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="936ea-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="936ea-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="936ea-119">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="936ea-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="936ea-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="936ea-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936ea-121">См. также</span><span class="sxs-lookup"><span data-stu-id="936ea-121">See also</span></span>

- [<span data-ttu-id="936ea-122">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="936ea-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="936ea-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="936ea-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
