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
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177107"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="abe69-102">Метод IMetaDataTables::GetRow</span><span class="sxs-lookup"><span data-stu-id="abe69-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="abe69-103">Получает строку в указанном индексе строки, в таблице в указанном индексе таблицы.</span><span class="sxs-lookup"><span data-stu-id="abe69-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abe69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abe69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abe69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="abe69-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="abe69-106">(в) Индекс таблицы, из которой будет извлечен ряд.</span><span class="sxs-lookup"><span data-stu-id="abe69-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="abe69-107">(в) Индекс строки, чтобы получить.</span><span class="sxs-lookup"><span data-stu-id="abe69-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="abe69-108">(ваут) Указатель на указатель на строку.</span><span class="sxs-lookup"><span data-stu-id="abe69-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abe69-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="abe69-109">Remarks</span></span>  

  <span data-ttu-id="abe69-110">Мы не рекомендуем использовать этот метод, потому что он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="abe69-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="abe69-111">Для получения информации о таблице GUID см.</span><span class="sxs-lookup"><span data-stu-id="abe69-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="abe69-112">Документация доступна в Интернете; [см. ECMA C и общие стандарты языковой инфраструктуры](../../../standard/components.md#applicable-standards) и [стандартные ECMA-335 - Общая языковая инфраструктура (CLI).](http://www.ecma-international.org/publications/standards/Ecma-335.htm)</span><span class="sxs-lookup"><span data-stu-id="abe69-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abe69-113">Требования</span><span class="sxs-lookup"><span data-stu-id="abe69-113">Requirements</span></span>  
 <span data-ttu-id="abe69-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abe69-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abe69-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="abe69-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="abe69-116">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abe69-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="abe69-117">**Рамочные версии .NET**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abe69-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe69-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="abe69-118">See also</span></span>

- [<span data-ttu-id="abe69-119">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="abe69-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="abe69-120">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="abe69-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
