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
ms.openlocfilehash: 3ce6cfd6a331c9d9695f65eb3a670305de38d010
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779851"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="0e252-102">Метод IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="0e252-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="0e252-103">Получает индекс строки, содержащей Далее жестко запрограммированные строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="0e252-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e252-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e252-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e252-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e252-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="0e252-106">[in] Значение индекса, текущий столбец строки.</span><span class="sxs-lookup"><span data-stu-id="0e252-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="0e252-107">[out] Указатель на индекс строки, следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="0e252-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e252-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e252-108">Remarks</span></span>  
 <span data-ttu-id="0e252-109">Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты.</span><span class="sxs-lookup"><span data-stu-id="0e252-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="0e252-110">Сведения о таблице, см. в документации Common Language Infrastructure (CLI), особенно «раздел II: Определение метаданных и семантика».</span><span class="sxs-lookup"><span data-stu-id="0e252-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="0e252-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="0e252-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e252-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0e252-112">Requirements</span></span>  
 <span data-ttu-id="0e252-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e252-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e252-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0e252-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e252-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e252-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e252-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e252-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e252-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0e252-117">See also</span></span>

- [<span data-ttu-id="0e252-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="0e252-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0e252-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="0e252-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
