---
title: Метод IMetaDataTables::GetRow
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a02719651d8169c1122f5a46b1b8df39b28612ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197286"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="8e265-102">Метод IMetaDataTables::GetRow</span><span class="sxs-lookup"><span data-stu-id="8e265-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="8e265-103">Возвращает строку по указанному индексу строки, в таблице с индексом указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="8e265-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e265-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e265-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e265-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e265-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="8e265-106">[in] Индекс таблицы, из которого извлекается строка.</span><span class="sxs-lookup"><span data-stu-id="8e265-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="8e265-107">[in] Индекс строки для получения.</span><span class="sxs-lookup"><span data-stu-id="8e265-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="8e265-108">[out] Указатель на указатель на строку.</span><span class="sxs-lookup"><span data-stu-id="8e265-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e265-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e265-109">Remarks</span></span>  
 <span data-ttu-id="8e265-110">Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="8e265-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="8e265-111">Сведения о таблице, см. в документации Common Language Infrastructure (CLI), особенно «раздел II: Определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="8e265-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="8e265-112">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="8e265-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e265-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8e265-113">Requirements</span></span>  
 <span data-ttu-id="8e265-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e265-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e265-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8e265-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e265-116">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e265-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e265-117">**Версии платформы .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e265-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e265-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8e265-118">See also</span></span>

- [<span data-ttu-id="8e265-119">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="8e265-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8e265-120">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="8e265-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
