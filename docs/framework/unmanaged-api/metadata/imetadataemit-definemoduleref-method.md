---
title: Метод IMetaDataEmit::DefineModuleRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f52f102102cb654035d49eea0f4b0a9061475a3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128821"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="6b250-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="6b250-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="6b250-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="6b250-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b250-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b250-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b250-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b250-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6b250-106">[in] Имя файла других метаданных, обычно библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="6b250-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="6b250-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="6b250-107">This is the file name only.</span></span> <span data-ttu-id="6b250-108">Не используйте полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="6b250-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="6b250-109">[out] Назначенные `mdModuleRef` токена.</span><span class="sxs-lookup"><span data-stu-id="6b250-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b250-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6b250-110">Requirements</span></span>  
 <span data-ttu-id="6b250-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b250-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b250-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b250-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b250-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b250-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6b250-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6b250-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b250-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6b250-115">See also</span></span>

- [<span data-ttu-id="6b250-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6b250-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6b250-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6b250-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
