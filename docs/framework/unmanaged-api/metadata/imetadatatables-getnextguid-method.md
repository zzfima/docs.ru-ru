---
title: Метод IMetaDataTables::GetNextGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 872f5a9eaa17a777cfbb14fea34cc80e0b7c04ad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487490"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="93e57-102">Метод IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="93e57-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="93e57-103">Получает индекс следующего значения GUID в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="93e57-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93e57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93e57-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93e57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93e57-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="93e57-106">[in] Значение индекса из таблицы столбец GUID.</span><span class="sxs-lookup"><span data-stu-id="93e57-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="93e57-107">[out] Указатель на индекс следующего значения идентификатора GUID.</span><span class="sxs-lookup"><span data-stu-id="93e57-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93e57-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="93e57-108">Remarks</span></span>  
 <span data-ttu-id="93e57-109">Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="93e57-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="93e57-110">Сведения о таблице, см. в документации Common Language Infrastructure (CLI), особенно «раздел II: Определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="93e57-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="93e57-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="93e57-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93e57-112">Требования</span><span class="sxs-lookup"><span data-stu-id="93e57-112">Requirements</span></span>  
 <span data-ttu-id="93e57-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93e57-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93e57-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="93e57-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93e57-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93e57-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93e57-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93e57-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e57-117">См. также</span><span class="sxs-lookup"><span data-stu-id="93e57-117">See also</span></span>
- [<span data-ttu-id="93e57-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="93e57-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="93e57-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="93e57-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
