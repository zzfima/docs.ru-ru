---
title: Метод IMetaDataTables::GetNextUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b9e729732175b7249e4d3be91996bc5e4050855
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450210"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="f65b1-102">Метод IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="f65b1-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="f65b1-103">Возвращает индекс строки, содержащей Далее жестко заданная строка в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="f65b1-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f65b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f65b1-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f65b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f65b1-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="f65b1-106">[in] Значение индекса из столбца текущей строки.</span><span class="sxs-lookup"><span data-stu-id="f65b1-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="f65b1-107">[out] Указатель на индекс строки, следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="f65b1-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f65b1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f65b1-108">Remarks</span></span>  
 <span data-ttu-id="f65b1-109">Не рекомендуется для использования этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="f65b1-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f65b1-110">Сведения о таблице см. в документации Common Language Infrastructure (CLI), особенно «раздел II: определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="f65b1-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f65b1-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="f65b1-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f65b1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f65b1-112">Requirements</span></span>  
 <span data-ttu-id="f65b1-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f65b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f65b1-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f65b1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f65b1-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f65b1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f65b1-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f65b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65b1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f65b1-117">See Also</span></span>  
 [<span data-ttu-id="f65b1-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f65b1-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f65b1-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f65b1-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
