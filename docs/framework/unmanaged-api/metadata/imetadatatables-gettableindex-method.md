---
title: "Метод IMetaDataTables::GetTableIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d49e1258011d68a6278d1c40500386024a2cb0d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="7b965-102">Метод IMetaDataTables::GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="7b965-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="7b965-103">Возвращает индекс для таблицы, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="7b965-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b965-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b965-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b965-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b965-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="7b965-106">[in] Токен, который ссылается на таблицу.</span><span class="sxs-lookup"><span data-stu-id="7b965-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="7b965-107">[out] Указатель на возвращаемый индекс для ссылочной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b965-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b965-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b965-108">Remarks</span></span>  
 <span data-ttu-id="7b965-109">Не рекомендуется для использования этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="7b965-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="7b965-110">Сведения о таблице см. в документации Common Language Infrastructure (CLI), особенно «раздел II: определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="7b965-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="7b965-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="7b965-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b965-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7b965-112">Requirements</span></span>  
 <span data-ttu-id="7b965-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b965-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b965-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b965-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b965-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b965-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b965-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b965-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b965-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7b965-117">See Also</span></span>  
 [<span data-ttu-id="7b965-118">IMetaDataTables-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7b965-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="7b965-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="7b965-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
