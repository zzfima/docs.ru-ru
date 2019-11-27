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
ms.openlocfilehash: c736eccfd5d05ec9b65e6ed26187e7c7b4387c5d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431728"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="c2e75-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="c2e75-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="c2e75-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c2e75-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e75-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2e75-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2e75-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c2e75-106">окне Имя другого файла метаданных, обычно DLL.</span><span class="sxs-lookup"><span data-stu-id="c2e75-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="c2e75-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="c2e75-107">This is the file name only.</span></span> <span data-ttu-id="c2e75-108">Не используйте полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="c2e75-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="c2e75-109">заполняет Назначенный маркер `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="c2e75-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e75-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c2e75-110">Requirements</span></span>  
 <span data-ttu-id="c2e75-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2e75-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e75-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c2e75-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2e75-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c2e75-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2e75-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e75-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e75-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e75-115">See also</span></span>

- [<span data-ttu-id="c2e75-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c2e75-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c2e75-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c2e75-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
