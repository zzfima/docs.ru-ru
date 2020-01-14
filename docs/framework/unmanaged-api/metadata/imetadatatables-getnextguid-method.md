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
ms.openlocfilehash: d4055975287267d08d2c2224ff6ddaa39fca548d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937798"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="1ad33-102">Метод IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="1ad33-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="1ad33-103">Возвращает индекс следующего значения GUID в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ad33-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ad33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ad33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ad33-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="1ad33-106">окне Значение индекса из столбца таблицы GUID.</span><span class="sxs-lookup"><span data-stu-id="1ad33-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="1ad33-107">заполняет Указатель на индекс следующего значения GUID.</span><span class="sxs-lookup"><span data-stu-id="1ad33-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ad33-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="1ad33-108">Remarks</span></span>  

  <span data-ttu-id="1ad33-109">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="1ad33-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="1ad33-110">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="1ad33-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="1ad33-111">Документация доступна в Интернете; см. раздел [стандарты C# ECMA и Common Language INFRASTRUCTURE](../../../standard/components.md#applicable-standards) и [стандарт ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="1ad33-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ad33-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1ad33-112">Requirements</span></span>  
 <span data-ttu-id="1ad33-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ad33-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad33-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1ad33-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ad33-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1ad33-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ad33-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad33-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad33-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ad33-117">See also</span></span>

- [<span data-ttu-id="1ad33-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="1ad33-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1ad33-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="1ad33-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
