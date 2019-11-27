---
title: Метод IMetaDataTables::GetGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 1f0c52efd4b55d19cbd7b2407c4b2d7c893b1009
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436088"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="ab17f-102">Метод IMetaDataTables::GetGuid</span><span class="sxs-lookup"><span data-stu-id="ab17f-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="ab17f-103">Возвращает идентификатор GUID из строки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="ab17f-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab17f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab17f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab17f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab17f-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="ab17f-106">окне Индекс строки, из которой необходимо получить идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="ab17f-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="ab17f-107">заполняет Указатель на указатель на идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="ab17f-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab17f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab17f-108">Remarks</span></span>  
 <span data-ttu-id="ab17f-109">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="ab17f-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ab17f-110">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="ab17f-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ab17f-111">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="ab17f-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab17f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ab17f-112">Requirements</span></span>  
 <span data-ttu-id="ab17f-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab17f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab17f-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ab17f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab17f-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ab17f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab17f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab17f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab17f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ab17f-117">See also</span></span>

- [<span data-ttu-id="ab17f-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ab17f-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ab17f-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ab17f-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
