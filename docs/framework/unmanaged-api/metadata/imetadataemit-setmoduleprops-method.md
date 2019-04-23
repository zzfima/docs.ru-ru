---
title: Метод IMetaDataEmit::SetModuleProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 651659a48ba9950cdd837889c4491c66fe40b507
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202967"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="6202f-102">Метод IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="6202f-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="6202f-103">Обновляет ссылки на модуль, определяются в первом вызове [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="6202f-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6202f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6202f-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6202f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6202f-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6202f-106">[in] Имя модуля в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="6202f-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="6202f-107">Это только имя файла, а не полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="6202f-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6202f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="6202f-108">Requirements</span></span>  
 <span data-ttu-id="6202f-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6202f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6202f-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6202f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6202f-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6202f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6202f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6202f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6202f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6202f-113">See also</span></span>

- [<span data-ttu-id="6202f-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6202f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6202f-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6202f-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
