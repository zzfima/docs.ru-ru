---
title: Метод IMetaDataEmit::SetFieldRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a38de994575bf0191ff2ab5ce1c7b047540289f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470592"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="bb7f2-102">Метод IMetaDataEmit::SetFieldRVA</span><span class="sxs-lookup"><span data-stu-id="bb7f2-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="bb7f2-103">Задает значение глобальной переменной для относительного виртуального адреса поля, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="bb7f2-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb7f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb7f2-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb7f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb7f2-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="bb7f2-106">[in] Маркер целевого поля.</span><span class="sxs-lookup"><span data-stu-id="bb7f2-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="bb7f2-107">[in] Адрес области кода или данных.</span><span class="sxs-lookup"><span data-stu-id="bb7f2-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb7f2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="bb7f2-108">Requirements</span></span>  
 <span data-ttu-id="bb7f2-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb7f2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb7f2-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb7f2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb7f2-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb7f2-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb7f2-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb7f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7f2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bb7f2-113">See also</span></span>
- [<span data-ttu-id="bb7f2-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bb7f2-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bb7f2-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bb7f2-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
