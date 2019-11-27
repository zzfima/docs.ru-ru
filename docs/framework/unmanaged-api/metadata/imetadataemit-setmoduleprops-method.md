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
ms.openlocfilehash: 2d3c820975488fa722e7af6070611ba7e9686ce8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445442"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="8c3c1-102">Метод IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="8c3c1-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="8c3c1-103">Обновляет ссылки на модуль, определенный в предыдущем вызове [IMetaDataEmit::D ефинемодулереф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="8c3c1-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c3c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c3c1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c3c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c3c1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8c3c1-106">окне Имя модуля в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="8c3c1-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="8c3c1-107">Это только имя файла, а не полный путь.</span><span class="sxs-lookup"><span data-stu-id="8c3c1-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c3c1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8c3c1-108">Requirements</span></span>  
 <span data-ttu-id="8c3c1-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c3c1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c3c1-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8c3c1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c3c1-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8c3c1-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c3c1-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c3c1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3c1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8c3c1-113">See also</span></span>

- [<span data-ttu-id="8c3c1-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8c3c1-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8c3c1-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8c3c1-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
