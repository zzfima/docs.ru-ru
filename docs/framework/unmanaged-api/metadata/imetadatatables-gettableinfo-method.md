---
title: "Метод IMetaDataTables::GetTableInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f4ccd9bbd1c7caa9bbeb548176d834dc8844213
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="6f421-102">Метод IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="6f421-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="6f421-103">Возвращает имя, размер строки, количество строк, количество столбцов и ключевого столбца индекса указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="6f421-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f421-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f421-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="6f421-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f421-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="6f421-106">[in] Идентификатор таблицы, свойства которого следует вернуть.</span><span class="sxs-lookup"><span data-stu-id="6f421-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="6f421-107">[out] Указатель на размер в байтах, строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="6f421-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="6f421-108">[out] Указатель на число строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="6f421-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="6f421-109">[out] Указатель на число столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="6f421-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="6f421-110">[out] Указатель на индекс ключевого столбца или значение -1, если таблица не имеет ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="6f421-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="6f421-111">[out] Указатель на указатель на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="6f421-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f421-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6f421-112">Requirements</span></span>  
 <span data-ttu-id="6f421-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f421-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f421-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6f421-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f421-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f421-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6f421-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f421-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f421-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6f421-117">See Also</span></span>  
 [<span data-ttu-id="6f421-118">IMetaDataTables-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6f421-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="6f421-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="6f421-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
