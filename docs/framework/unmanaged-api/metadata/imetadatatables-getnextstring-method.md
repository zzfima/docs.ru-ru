---
title: Метод IMetaDataTables::GetNextString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: a1cd932051a9ed90a29ff5eeaa818a67104192bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175256"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="55019-102">Метод IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="55019-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="55019-103">Получает индекс следующей строки в текущей таблице столбца.</span><span class="sxs-lookup"><span data-stu-id="55019-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55019-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55019-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55019-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55019-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="55019-106">(в) Значение индекса из столбца строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="55019-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="55019-107">(ваут) Указатель на индекс следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="55019-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55019-108">Требования</span><span class="sxs-lookup"><span data-stu-id="55019-108">Requirements</span></span>  
 <span data-ttu-id="55019-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55019-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55019-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="55019-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55019-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55019-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55019-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55019-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55019-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55019-113">See also</span></span>

- [<span data-ttu-id="55019-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="55019-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="55019-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="55019-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
