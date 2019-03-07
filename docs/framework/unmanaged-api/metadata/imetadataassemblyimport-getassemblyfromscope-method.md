---
title: Метод IMetaDataAssemblyImport::GetAssemblyFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fc82ad87721c31337002dcfc5bbfdb9300afb31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479744"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="67bc0-102">Метод IMetaDataAssemblyImport::GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="67bc0-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="67bc0-103">Получает указатель на сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="67bc0-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67bc0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67bc0-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67bc0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67bc0-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="67bc0-106">[out] Указатель на извлеченного `mdAssembly` токен, идентифицирующий сборку.</span><span class="sxs-lookup"><span data-stu-id="67bc0-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67bc0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="67bc0-107">Requirements</span></span>  
 <span data-ttu-id="67bc0-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67bc0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67bc0-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67bc0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67bc0-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67bc0-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67bc0-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67bc0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67bc0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="67bc0-112">See also</span></span>
- [<span data-ttu-id="67bc0-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="67bc0-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
