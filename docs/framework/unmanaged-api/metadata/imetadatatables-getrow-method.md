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
ms.openlocfilehash: 98fc95c618a7a06f5e6c219d7707af291770c06a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781415"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="ed350-102">Метод IMetaDataTables::GetRow</span><span class="sxs-lookup"><span data-stu-id="ed350-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="ed350-103">Возвращает строку по указанному индексу строки, в таблице с индексом указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="ed350-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed350-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed350-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed350-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed350-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="ed350-106">[in] Индекс таблицы, из которого извлекается строка.</span><span class="sxs-lookup"><span data-stu-id="ed350-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="ed350-107">[in] Индекс строки для получения.</span><span class="sxs-lookup"><span data-stu-id="ed350-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="ed350-108">[out] Указатель на указатель на строку.</span><span class="sxs-lookup"><span data-stu-id="ed350-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed350-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed350-109">Remarks</span></span>  
 <span data-ttu-id="ed350-110">Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="ed350-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ed350-111">Сведения о таблице, см. в документации Common Language Infrastructure (CLI), особенно «раздел II: Определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="ed350-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ed350-112">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="ed350-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed350-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ed350-113">Requirements</span></span>  
 <span data-ttu-id="ed350-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed350-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed350-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ed350-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed350-116">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed350-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed350-117">**Версии платформы .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed350-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed350-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ed350-118">See also</span></span>

- [<span data-ttu-id="ed350-119">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ed350-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ed350-120">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ed350-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
