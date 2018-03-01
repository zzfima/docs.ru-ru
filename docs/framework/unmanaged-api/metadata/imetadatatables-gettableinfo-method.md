---
title: "Метод IMetaDataTables::GetTableInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ce9e3beb15724c7d7ddf02cbe7f83795d474139
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="b282d-102">Метод IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="b282d-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="b282d-103">Возвращает имя, размер строки, количество строк, количество столбцов и ключевого столбца индекса указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b282d-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b282d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b282d-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="b282d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b282d-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="b282d-106">[in] Идентификатор таблицы, свойства которого следует вернуть.</span><span class="sxs-lookup"><span data-stu-id="b282d-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="b282d-107">[out] Указатель на размер в байтах, строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="b282d-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="b282d-108">[out] Указатель на число строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="b282d-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="b282d-109">[out] Указатель на число столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="b282d-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="b282d-110">[out] Указатель на индекс ключевого столбца или значение -1, если таблица не имеет ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="b282d-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="b282d-111">[out] Указатель на указатель на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="b282d-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b282d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b282d-112">Requirements</span></span>  
 <span data-ttu-id="b282d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b282d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b282d-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b282d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b282d-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b282d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b282d-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b282d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b282d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b282d-117">See Also</span></span>  
 [<span data-ttu-id="b282d-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b282d-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="b282d-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b282d-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
