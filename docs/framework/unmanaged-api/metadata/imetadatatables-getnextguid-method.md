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
ms.openlocfilehash: b23e1d26d62012efe338eeb179db0e7ee17cd658
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110473"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="1c47f-102">Метод IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="1c47f-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="1c47f-103">Получает индекс следующего значения GUID в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="1c47f-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c47f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c47f-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c47f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c47f-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="1c47f-106">[in] Значение индекса из таблицы столбец GUID.</span><span class="sxs-lookup"><span data-stu-id="1c47f-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="1c47f-107">[out] Указатель на индекс следующего значения идентификатора GUID.</span><span class="sxs-lookup"><span data-stu-id="1c47f-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c47f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c47f-108">Remarks</span></span>  
 <span data-ttu-id="1c47f-109">Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="1c47f-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="1c47f-110">Сведения о таблице, см. в документации Common Language Infrastructure (CLI), особенно «раздел II: Определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="1c47f-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="1c47f-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="1c47f-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c47f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1c47f-112">Requirements</span></span>  
 <span data-ttu-id="1c47f-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c47f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c47f-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1c47f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c47f-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c47f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c47f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c47f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c47f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1c47f-117">See also</span></span>

- [<span data-ttu-id="1c47f-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="1c47f-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1c47f-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="1c47f-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
