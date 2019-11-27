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
ms.openlocfilehash: 662b628f3cc6d2d7138f56820beaccee9c5d9e81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426657"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="78f54-102">Метод IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="78f54-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="78f54-103">Возвращает имя, размер строки, число строк, число столбцов и индекс ключевого столбца указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="78f54-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78f54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78f54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78f54-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="78f54-106">окне Идентификатор таблицы, свойства которой должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="78f54-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="78f54-107">заполняет Указатель на размер строки таблицы в байтах.</span><span class="sxs-lookup"><span data-stu-id="78f54-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="78f54-108">заполняет Указатель на число строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="78f54-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="78f54-109">заполняет Указатель на число столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="78f54-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="78f54-110">заполняет Указатель на индекс ключевого столбца или значение-1, если у таблицы нет ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="78f54-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="78f54-111">заполняет Указатель на указатель на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="78f54-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f54-112">Требования</span><span class="sxs-lookup"><span data-stu-id="78f54-112">Requirements</span></span>  
 <span data-ttu-id="78f54-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78f54-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f54-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="78f54-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78f54-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78f54-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78f54-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f54-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f54-117">См. также</span><span class="sxs-lookup"><span data-stu-id="78f54-117">See also</span></span>

- [<span data-ttu-id="78f54-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="78f54-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="78f54-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="78f54-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
