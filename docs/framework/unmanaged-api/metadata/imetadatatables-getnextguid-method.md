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
ms.openlocfilehash: ca2c2b7c09f0b64fc8a2ffd6bd8455caa4c22215
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448528"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="2a4ce-102">Метод IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="2a4ce-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="2a4ce-103">Получает индекс следующего значения GUID в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a4ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a4ce-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a4ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a4ce-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="2a4ce-106">[in] Значение индекса из столбца таблицы GUID.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="2a4ce-107">[out] Указатель на индекс следующего значения идентификатора GUID.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a4ce-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a4ce-108">Remarks</span></span>  
 <span data-ttu-id="2a4ce-109">Не рекомендуется для использования этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="2a4ce-110">Сведения о таблице см. в документации Common Language Infrastructure (CLI), особенно «раздел II: определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="2a4ce-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="2a4ce-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a4ce-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2a4ce-112">Requirements</span></span>  
 <span data-ttu-id="2a4ce-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a4ce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a4ce-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a4ce-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a4ce-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a4ce-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a4ce-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a4ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a4ce-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2a4ce-117">See Also</span></span>  
 [<span data-ttu-id="2a4ce-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="2a4ce-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="2a4ce-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="2a4ce-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
