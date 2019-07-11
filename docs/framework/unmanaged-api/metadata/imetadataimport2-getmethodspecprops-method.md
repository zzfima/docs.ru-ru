---
title: Метод IMetaDataImport2::GetMethodSpecProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7700236efe7b031866867f5ed859ba71683a8a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782296"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="d1017-102">Метод IMetaDataImport2::GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="d1017-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="d1017-103">Получает токен метода, который ссылается указанный MethodSpec подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="d1017-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1017-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1017-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="d1017-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1017-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="d1017-106">[in] MethodSpec токен, представляющий экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="d1017-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="d1017-107">[out] Указатель на токен MethodDef или MethodRef, представляющий определение метода.</span><span class="sxs-lookup"><span data-stu-id="d1017-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="d1017-108">[out] Указатель на двоичную подпись метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="d1017-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="d1017-109">[out] Размер в байтах из `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d1017-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1017-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d1017-110">Requirements</span></span>  
 <span data-ttu-id="d1017-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1017-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1017-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d1017-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1017-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1017-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1017-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1017-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1017-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d1017-115">See also</span></span>

- [<span data-ttu-id="d1017-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d1017-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="d1017-117">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d1017-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
