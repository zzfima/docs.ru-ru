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
ms.openlocfilehash: 6522dbc8e49d612fc4c0d9597a9b5f12edb2cfe1
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937776"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="efb70-102">Метод IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="efb70-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="efb70-103">Возвращает индекс строки, содержащей следующую жестко заданную строку в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="efb70-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efb70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb70-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efb70-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="efb70-106">окне Значение индекса из текущего строкового столбца.</span><span class="sxs-lookup"><span data-stu-id="efb70-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="efb70-107">заполняет Указатель на индекс строки следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="efb70-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb70-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="efb70-108">Remarks</span></span>  
 <span data-ttu-id="efb70-109">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="efb70-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="efb70-110">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="efb70-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="efb70-111">Документация доступна в Интернете; см. раздел [стандарты C# ECMA и Common Language INFRASTRUCTURE](../../../standard/components.md#applicable-standards) и [стандарт ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="efb70-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb70-112">Требования</span><span class="sxs-lookup"><span data-stu-id="efb70-112">Requirements</span></span>  
 <span data-ttu-id="efb70-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb70-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb70-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="efb70-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efb70-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="efb70-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efb70-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb70-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb70-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="efb70-117">See also</span></span>

- [<span data-ttu-id="efb70-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="efb70-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="efb70-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="efb70-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
