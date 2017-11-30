---
title: "Метод IMetaDataImport2::GetMethodSpecProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetMethodSpecProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b07e79f3990782e18ffdc57e9bd75a0b62765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="e85a7-102">Метод IMetaDataImport2::GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="e85a7-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="e85a7-103">Возвращает подпись метаданных для метода, который ссылается указанный MethodSpec токен.</span><span class="sxs-lookup"><span data-stu-id="e85a7-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e85a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e85a7-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e85a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e85a7-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="e85a7-106">[in] MethodSpec токен, представляющий экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="e85a7-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="e85a7-107">[out] Указатель на токен MethodDef или MethodRef, представляющий определение метода.</span><span class="sxs-lookup"><span data-stu-id="e85a7-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="e85a7-108">[out] Указатель на двоичную подпись метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="e85a7-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="e85a7-109">[out] Размер в байтах для `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="e85a7-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e85a7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e85a7-110">Requirements</span></span>  
 <span data-ttu-id="e85a7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e85a7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e85a7-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e85a7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e85a7-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e85a7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e85a7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e85a7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85a7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e85a7-115">See Also</span></span>  
 [<span data-ttu-id="e85a7-116">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e85a7-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="e85a7-117">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e85a7-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
