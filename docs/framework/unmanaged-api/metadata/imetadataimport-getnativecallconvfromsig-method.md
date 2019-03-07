---
title: Метод IMetaDataImport::GetNativeCallConvFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1002aa9e01fedaacf80622952bbba82caa7081c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498020"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="c92cd-102">Метод IMetaDataImport::GetNativeCallConvFromSig</span><span class="sxs-lookup"><span data-stu-id="c92cd-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="c92cd-103">Возвращает собственное соглашение о вызовах для метода, представленного заданным указателем на подпись.</span><span class="sxs-lookup"><span data-stu-id="c92cd-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c92cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c92cd-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c92cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c92cd-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="c92cd-106">[in] Указатель на подпись метаданных для метода, возвращающего соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="c92cd-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="c92cd-107">[in] Размер в байтах `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="c92cd-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="c92cd-108">[out] Указатель на собственное соглашение о вызове.</span><span class="sxs-lookup"><span data-stu-id="c92cd-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c92cd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c92cd-109">Requirements</span></span>  
 <span data-ttu-id="c92cd-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c92cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c92cd-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c92cd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c92cd-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c92cd-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c92cd-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c92cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92cd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c92cd-114">See also</span></span>
- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="c92cd-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c92cd-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c92cd-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c92cd-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
