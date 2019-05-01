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
ms.openlocfilehash: 4ebde1d506a120a99e1c637c660b45d698994f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992476"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="eb0f1-102">Метод IMetaDataEmit::SetFieldRVA</span><span class="sxs-lookup"><span data-stu-id="eb0f1-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="eb0f1-103">Задает значение глобальной переменной для относительного виртуального адреса поля, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="eb0f1-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb0f1-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb0f1-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="eb0f1-106">[in] Маркер целевого поля.</span><span class="sxs-lookup"><span data-stu-id="eb0f1-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="eb0f1-107">[in] Адрес области кода или данных.</span><span class="sxs-lookup"><span data-stu-id="eb0f1-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb0f1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="eb0f1-108">Requirements</span></span>  
 <span data-ttu-id="eb0f1-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb0f1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb0f1-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb0f1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb0f1-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb0f1-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb0f1-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb0f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eb0f1-113">See also</span></span>

- [<span data-ttu-id="eb0f1-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="eb0f1-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="eb0f1-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="eb0f1-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
