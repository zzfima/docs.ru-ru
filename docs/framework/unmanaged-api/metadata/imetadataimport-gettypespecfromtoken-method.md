---
title: "Метод IMetaDataImport::GetTypeSpecFromToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeSpecFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 37a8c2580dad3e198290b72b49b0aacaf1804c25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="b48f9-102">Метод IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="b48f9-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="b48f9-103">Возвращает двоичную подпись метаданных для спецификации типа, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="b48f9-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b48f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b48f9-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b48f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b48f9-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="b48f9-106">[in] Токен TypeSpec, связанного с подписью, запрошенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="b48f9-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="b48f9-107">[out] Указатель на двоичную подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="b48f9-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="b48f9-108">[out] Размер в байтах, подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="b48f9-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b48f9-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b48f9-109">Return Value</span></span>  
 <span data-ttu-id="b48f9-110">Значение HRESULT, указывающее успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="b48f9-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="b48f9-111">Сбои можно протестировать с помощью макроса FAILED.</span><span class="sxs-lookup"><span data-stu-id="b48f9-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b48f9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b48f9-112">Requirements</span></span>  
 <span data-ttu-id="b48f9-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b48f9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b48f9-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b48f9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b48f9-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b48f9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b48f9-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b48f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48f9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b48f9-117">See Also</span></span>  
 [<span data-ttu-id="b48f9-118">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b48f9-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b48f9-119">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b48f9-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
