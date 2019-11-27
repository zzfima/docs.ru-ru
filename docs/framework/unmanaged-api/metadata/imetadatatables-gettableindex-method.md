---
title: Метод IMetaDataTables::GetTableIndex
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: 48c38288e960ff2e1fe21f30b6eceae8eeaac2da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434854"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="8edf5-102">Метод IMetaDataTables::GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="8edf5-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="8edf5-103">Возвращает индекс для таблицы, на которую ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="8edf5-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8edf5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8edf5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8edf5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8edf5-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="8edf5-106">окне Токен, ссылающийся на таблицу.</span><span class="sxs-lookup"><span data-stu-id="8edf5-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="8edf5-107">заполняет Указатель на возвращаемый индекс для упоминаемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8edf5-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8edf5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8edf5-108">Remarks</span></span>  
 <span data-ttu-id="8edf5-109">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="8edf5-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="8edf5-110">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="8edf5-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="8edf5-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="8edf5-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8edf5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8edf5-112">Requirements</span></span>  
 <span data-ttu-id="8edf5-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8edf5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8edf5-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8edf5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8edf5-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8edf5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8edf5-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8edf5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edf5-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="8edf5-117">See also</span></span>

- [<span data-ttu-id="8edf5-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="8edf5-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8edf5-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="8edf5-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
