---
title: Метод IMetaDataTables::GetString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 216a1f7bd2ff5a596fa7abf7874b5e603d5a9f7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175243"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="2bed4-102">Метод IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="2bed4-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="2bed4-103">Получает строку в указанном индексе из столбца таблицы в текущей области отсчета.</span><span class="sxs-lookup"><span data-stu-id="2bed4-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bed4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bed4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bed4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2bed4-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="2bed4-106">(в) Индекс, на котором можно начать поиск следующего значения.</span><span class="sxs-lookup"><span data-stu-id="2bed4-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="2bed4-107">(ваут) Указатель указателя на указатель на возвращенное значение строки.</span><span class="sxs-lookup"><span data-stu-id="2bed4-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bed4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2bed4-108">Requirements</span></span>  
 <span data-ttu-id="2bed4-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bed4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bed4-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2bed4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bed4-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bed4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bed4-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bed4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bed4-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2bed4-113">See also</span></span>

- [<span data-ttu-id="2bed4-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="2bed4-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2bed4-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="2bed4-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
