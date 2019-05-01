---
title: Метод IMetaDataEmit2::GetDeltaSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69897a7b646eb9f58e6b38588e302287b4241779
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043684"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="8fac0-102">Метод IMetaDataEmit2::GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="8fac0-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="8fac0-103">Получает значение, указывающее, любое изменение в размере метаданных, из текущего сеанса, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="8fac0-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fac0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fac0-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fac0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8fac0-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="8fac0-106">[in] Один из [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) значения, указывающие уровень точности требуемого.</span><span class="sxs-lookup"><span data-stu-id="8fac0-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="8fac0-107">Этот параметр учитывается для платформы .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="8fac0-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="8fac0-108">[out] Изменение размера метаданных.</span><span class="sxs-lookup"><span data-stu-id="8fac0-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fac0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8fac0-109">Requirements</span></span>  
 <span data-ttu-id="8fac0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fac0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fac0-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8fac0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8fac0-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fac0-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fac0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fac0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fac0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8fac0-114">See also</span></span>

- [<span data-ttu-id="8fac0-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8fac0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="8fac0-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8fac0-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
