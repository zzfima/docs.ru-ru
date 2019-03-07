---
title: Метод IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876f74d7fe7555f71db0bd77e68f657dfc80b179
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478964"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="311d0-102">Метод IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="311d0-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="311d0-103">Получает имя, размер строки, количество строк, число столбцов и ключевой столбец индекса указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="311d0-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="311d0-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="311d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="311d0-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="311d0-106">[in] Идентификатор таблицы, свойства которого следует вернуть.</span><span class="sxs-lookup"><span data-stu-id="311d0-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="311d0-107">[out] Указатель на размер в байтах, строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="311d0-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="311d0-108">[out] Указатель на число строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="311d0-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="311d0-109">[out] Указатель на число столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="311d0-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="311d0-110">[out] Указатель на индекс ключевого столбца или -1, если таблица не имеет ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="311d0-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="311d0-111">[out] Указатель на указатель на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="311d0-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="311d0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="311d0-112">Requirements</span></span>  
 <span data-ttu-id="311d0-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="311d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="311d0-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="311d0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="311d0-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="311d0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="311d0-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="311d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311d0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="311d0-117">See also</span></span>
- [<span data-ttu-id="311d0-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="311d0-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="311d0-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="311d0-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
