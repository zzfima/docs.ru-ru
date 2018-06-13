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
ms.openlocfilehash: ea617668a72413f3387a35fe009b37fa15d03354
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449612"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="a5ae6-102">Метод IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="a5ae6-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="a5ae6-103">Возвращает имя, размер строки, количество строк, количество столбцов и ключевого столбца индекса указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ae6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5ae6-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="a5ae6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5ae6-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="a5ae6-106">[in] Идентификатор таблицы, свойства которого следует вернуть.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="a5ae6-107">[out] Указатель на размер в байтах, строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="a5ae6-108">[out] Указатель на число строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="a5ae6-109">[out] Указатель на число столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="a5ae6-110">[out] Указатель на индекс ключевого столбца или значение -1, если таблица не имеет ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="a5ae6-111">[out] Указатель на указатель на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5ae6-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ae6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a5ae6-112">Requirements</span></span>  
 <span data-ttu-id="a5ae6-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5ae6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ae6-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5ae6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5ae6-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5ae6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5ae6-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5ae6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ae6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a5ae6-117">See Also</span></span>  
 [<span data-ttu-id="a5ae6-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a5ae6-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a5ae6-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a5ae6-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
