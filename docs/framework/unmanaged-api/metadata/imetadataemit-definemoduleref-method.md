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
ms.openlocfilehash: 4503c3c745fde148c77ff30c9ece008dd9d54829
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="100b5-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="100b5-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="100b5-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="100b5-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="100b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="100b5-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="100b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="100b5-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="100b5-106">[in] Имя другой файл метаданных, обычно DLL.</span><span class="sxs-lookup"><span data-stu-id="100b5-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="100b5-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="100b5-107">This is the file name only.</span></span> <span data-ttu-id="100b5-108">Не используйте полный путь.</span><span class="sxs-lookup"><span data-stu-id="100b5-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="100b5-109">[out] Назначенные `mdModuleRef` токена.</span><span class="sxs-lookup"><span data-stu-id="100b5-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="100b5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="100b5-110">Requirements</span></span>  
 <span data-ttu-id="100b5-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="100b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="100b5-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="100b5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="100b5-113">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="100b5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="100b5-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="100b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="100b5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="100b5-115">See Also</span></span>  
 [<span data-ttu-id="100b5-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="100b5-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="100b5-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="100b5-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
