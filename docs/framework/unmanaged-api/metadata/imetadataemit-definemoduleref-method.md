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
ms.openlocfilehash: 94261b7796166cf482a7de990551890e4722dd3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177741"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="a5446-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="a5446-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="a5446-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="a5446-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5446-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5446-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5446-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5446-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a5446-106">(в) Имя другого файла метаданных, как правило, DLL.</span><span class="sxs-lookup"><span data-stu-id="a5446-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="a5446-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="a5446-107">This is the file name only.</span></span> <span data-ttu-id="a5446-108">Не используйте имя полного пути.</span><span class="sxs-lookup"><span data-stu-id="a5446-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="a5446-109">(ваут) Назначенный `mdModuleRef` токен.</span><span class="sxs-lookup"><span data-stu-id="a5446-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5446-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a5446-110">Requirements</span></span>  
 <span data-ttu-id="a5446-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5446-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5446-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5446-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5446-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5446-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5446-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5446-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5446-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a5446-115">See also</span></span>

- [<span data-ttu-id="a5446-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a5446-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a5446-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a5446-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
