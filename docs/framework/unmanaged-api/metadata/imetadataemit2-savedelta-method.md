---
title: Метод IMetaDataEmit2::SaveDelta
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d97f536d54ac1cb77c5d0413d2437508374ac7f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042917"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="9601a-102">Метод IMetaDataEmit2::SaveDelta</span><span class="sxs-lookup"><span data-stu-id="9601a-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="9601a-103">Сохраняет изменения в текущем сеансе, изменить и продолжить в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="9601a-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9601a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9601a-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9601a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9601a-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="9601a-106">[in] Имя файла, в котором нужно сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="9601a-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="9601a-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="9601a-107">[in] Reserved.</span></span> <span data-ttu-id="9601a-108">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="9601a-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9601a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9601a-109">Requirements</span></span>  
 <span data-ttu-id="9601a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9601a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9601a-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9601a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9601a-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9601a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9601a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9601a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9601a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9601a-114">See also</span></span>

- [<span data-ttu-id="9601a-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9601a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="9601a-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9601a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
