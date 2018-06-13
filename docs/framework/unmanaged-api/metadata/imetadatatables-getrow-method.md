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
ms.openlocfilehash: 954b4df6b341e18c5a995b57541a72e236278c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449599"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="f8381-102">Метод IMetaDataTables::GetRow</span><span class="sxs-lookup"><span data-stu-id="f8381-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="f8381-103">Возвращает строку с указанной строки индекса, в таблице с заданным индексом таблицы.</span><span class="sxs-lookup"><span data-stu-id="f8381-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8381-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8381-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8381-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8381-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="f8381-106">[in] Индекс таблицы, из которого требуется извлечь строку.</span><span class="sxs-lookup"><span data-stu-id="f8381-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="f8381-107">[in] Индекс строки для получения.</span><span class="sxs-lookup"><span data-stu-id="f8381-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="f8381-108">[out] Указатель на указатель на строку.</span><span class="sxs-lookup"><span data-stu-id="f8381-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8381-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8381-109">Remarks</span></span>  
 <span data-ttu-id="f8381-110">Не рекомендуется для использования этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="f8381-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f8381-111">Сведения о таблице см. в документации Common Language Infrastructure (CLI), особенно «раздел II: определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="f8381-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f8381-112">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="f8381-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8381-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f8381-113">Requirements</span></span>  
 <span data-ttu-id="f8381-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8381-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8381-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8381-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8381-116">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8381-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8381-117">**Версии платформы .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8381-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8381-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f8381-118">See Also</span></span>  
 [<span data-ttu-id="f8381-119">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f8381-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f8381-120">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f8381-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
