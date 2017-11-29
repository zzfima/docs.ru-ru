---
title: "Метод IMetaDataEmit::DefineModuleRef"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineModuleRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b3131e6cebf09b0767d1331656ff16b2b55d749
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="80d90-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="80d90-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="80d90-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="80d90-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80d90-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80d90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80d90-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="80d90-106">[in] Имя другой файл метаданных, обычно DLL.</span><span class="sxs-lookup"><span data-stu-id="80d90-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="80d90-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="80d90-107">This is the file name only.</span></span> <span data-ttu-id="80d90-108">Не используйте полный путь.</span><span class="sxs-lookup"><span data-stu-id="80d90-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="80d90-109">[out] Назначенные `mdModuleRef` токена.</span><span class="sxs-lookup"><span data-stu-id="80d90-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80d90-110">Требования</span><span class="sxs-lookup"><span data-stu-id="80d90-110">Requirements</span></span>  
 <span data-ttu-id="80d90-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80d90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80d90-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80d90-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80d90-113">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80d90-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80d90-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80d90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d90-115">См. также</span><span class="sxs-lookup"><span data-stu-id="80d90-115">See Also</span></span>  
 [<span data-ttu-id="80d90-116">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="80d90-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="80d90-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="80d90-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
