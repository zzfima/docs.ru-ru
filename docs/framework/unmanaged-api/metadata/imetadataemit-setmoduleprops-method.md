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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042982"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="77178-102">Метод IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="77178-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="77178-103">Обновляет ссылки на модуль, определяются в первом вызове [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="77178-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77178-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77178-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77178-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77178-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="77178-106">[in] Имя модуля в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="77178-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="77178-107">Это только имя файла, а не полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="77178-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77178-108">Требования</span><span class="sxs-lookup"><span data-stu-id="77178-108">Requirements</span></span>  
 <span data-ttu-id="77178-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77178-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77178-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77178-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77178-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77178-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77178-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77178-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77178-113">См. также</span><span class="sxs-lookup"><span data-stu-id="77178-113">See also</span></span>

- [<span data-ttu-id="77178-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="77178-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="77178-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="77178-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
