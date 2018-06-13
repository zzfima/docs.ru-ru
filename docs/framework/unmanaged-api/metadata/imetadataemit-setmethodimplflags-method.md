---
title: Метод IMetaDataEmit::SetMethodImplFlags
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71881fe8c4b883bb91468033a3c17c8d77c35f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445426"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="8d09c-102">Метод IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="8d09c-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="8d09c-103">Задает или обновляет подпись метаданных реализации унаследованного метода, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="8d09c-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d09c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d09c-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d09c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d09c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8d09c-106">[in] Токен, метод должен быть изменен.</span><span class="sxs-lookup"><span data-stu-id="8d09c-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="8d09c-107">[in] Сочетание значений [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) перечисления, которое указывает возможности реализации метода.</span><span class="sxs-lookup"><span data-stu-id="8d09c-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d09c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8d09c-108">Requirements</span></span>  
 <span data-ttu-id="8d09c-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d09c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d09c-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d09c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d09c-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d09c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d09c-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d09c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d09c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8d09c-113">See Also</span></span>  
 [<span data-ttu-id="8d09c-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8d09c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8d09c-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8d09c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
