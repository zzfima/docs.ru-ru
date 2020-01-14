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
ms.openlocfilehash: 9ac6eba18ae23dc80a8dc90383aa67cfe41b39ff
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937404"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="b3e12-102">Метод IMetaDataTables::GetRow</span><span class="sxs-lookup"><span data-stu-id="b3e12-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="b3e12-103">Возвращает строку по указанному индексу строки в таблице по указанному индексу таблицы.</span><span class="sxs-lookup"><span data-stu-id="b3e12-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3e12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3e12-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3e12-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="b3e12-106">окне Индекс таблицы, из которой будет извлечена строка.</span><span class="sxs-lookup"><span data-stu-id="b3e12-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="b3e12-107">окне Индекс получаемой строки.</span><span class="sxs-lookup"><span data-stu-id="b3e12-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="b3e12-108">заполняет Указатель на указатель на строку.</span><span class="sxs-lookup"><span data-stu-id="b3e12-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3e12-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b3e12-109">Remarks</span></span>  

  <span data-ttu-id="b3e12-110">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="b3e12-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="b3e12-111">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="b3e12-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="b3e12-112">Документация доступна в Интернете; см. раздел [стандарты C# ECMA и Common Language INFRASTRUCTURE](../../../standard/components.md#applicable-standards) и [стандарт ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="b3e12-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3e12-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b3e12-113">Requirements</span></span>  
 <span data-ttu-id="b3e12-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3e12-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3e12-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b3e12-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3e12-116">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3e12-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3e12-117">**.NET Framework версии**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3e12-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e12-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3e12-118">See also</span></span>

- [<span data-ttu-id="b3e12-119">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b3e12-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b3e12-120">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b3e12-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
