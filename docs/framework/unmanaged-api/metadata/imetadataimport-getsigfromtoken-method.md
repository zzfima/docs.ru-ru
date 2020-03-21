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
ms.openlocfilehash: 5af59e158a34b06d304a98db1dfaa46585b22eb6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177196"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="e79bb-102">Метод IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="e79bb-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="e79bb-103">Возвращает двоичную подпись метаданных, связанную с указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="e79bb-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e79bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e79bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e79bb-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="e79bb-106">(в) Токен для возврата двоичной подписи метаданных для.</span><span class="sxs-lookup"><span data-stu-id="e79bb-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="e79bb-107">(ваут) Указатель на возвращенную подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="e79bb-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="e79bb-108">(ваут) Размер байтов двоичной подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="e79bb-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e79bb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e79bb-109">Requirements</span></span>  
 <span data-ttu-id="e79bb-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e79bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e79bb-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e79bb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e79bb-112">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e79bb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e79bb-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e79bb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79bb-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e79bb-114">See also</span></span>

- [<span data-ttu-id="e79bb-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e79bb-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e79bb-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e79bb-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
