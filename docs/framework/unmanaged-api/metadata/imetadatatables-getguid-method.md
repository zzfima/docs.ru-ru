---
title: Метод IMetaDataTables::GetGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175282"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="c1ecb-102">Метод IMetaDataTables::GetGuid</span><span class="sxs-lookup"><span data-stu-id="c1ecb-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="c1ecb-103">Получает GUID из строки в указанном индексе.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ecb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1ecb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ecb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1ecb-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="c1ecb-106">(в) Индекс строки, из которого можно получить GUID.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="c1ecb-107">(ваут) Указатель на указатель на GUID.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1ecb-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1ecb-108">Remarks</span></span>  

  <span data-ttu-id="c1ecb-109">Мы не рекомендуем использовать этот метод, потому что он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="c1ecb-110">Для получения информации о таблице GUID см.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="c1ecb-111">Документация доступна в Интернете; [см. ECMA C и общие стандарты языковой инфраструктуры](../../../standard/components.md#applicable-standards) и [стандартные ECMA-335 - Общая языковая инфраструктура (CLI).](http://www.ecma-international.org/publications/standards/Ecma-335.htm)</span><span class="sxs-lookup"><span data-stu-id="c1ecb-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ecb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c1ecb-112">Requirements</span></span>  
 <span data-ttu-id="c1ecb-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ecb-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1ecb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1ecb-115">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1ecb-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ecb-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ecb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ecb-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c1ecb-117">See also</span></span>

- [<span data-ttu-id="c1ecb-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c1ecb-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c1ecb-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c1ecb-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
