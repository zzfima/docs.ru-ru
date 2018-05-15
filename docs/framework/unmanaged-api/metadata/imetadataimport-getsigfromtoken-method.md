---
title: Метод IMetaDataImport::GetSigFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f40fb2e94eac13211cf8ccf179904071a23f59ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="614d9-102">Метод IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="614d9-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="614d9-103">Возвращает двоичную подпись метаданных, связанную с указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="614d9-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="614d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="614d9-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="614d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="614d9-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="614d9-106">[in] Маркер для возвращения двоичную подпись метаданных для.</span><span class="sxs-lookup"><span data-stu-id="614d9-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="614d9-107">[out] Указатель на подпись возвращенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="614d9-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="614d9-108">[out] Размер в байтах двоичную подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="614d9-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="614d9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="614d9-109">Requirements</span></span>  
 <span data-ttu-id="614d9-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="614d9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="614d9-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="614d9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="614d9-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="614d9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="614d9-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="614d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614d9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="614d9-114">See Also</span></span>  
 [<span data-ttu-id="614d9-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="614d9-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="614d9-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="614d9-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
