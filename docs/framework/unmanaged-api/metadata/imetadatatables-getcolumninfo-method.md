---
title: Метод IMetaDataTables::GetColumnInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6156499368fb743b69c03f38b40ad3c5bcabce6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992411"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="8edd0-102">Метод IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="8edd0-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="8edd0-103">Получает данные о заданном столбце в указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="8edd0-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8edd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8edd0-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8edd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8edd0-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="8edd0-106">[in] Индекс нужную таблицу.</span><span class="sxs-lookup"><span data-stu-id="8edd0-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="8edd0-107">[in] Индекс требуемый столбец.</span><span class="sxs-lookup"><span data-stu-id="8edd0-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="8edd0-108">[out] Указатель на смещение столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="8edd0-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="8edd0-109">[out] Указатель на размер в байтах, столбца.</span><span class="sxs-lookup"><span data-stu-id="8edd0-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="8edd0-110">[out] Указатель на тип значения в столбце.</span><span class="sxs-lookup"><span data-stu-id="8edd0-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="8edd0-111">[out] Указатель на указатель на имя столбца.</span><span class="sxs-lookup"><span data-stu-id="8edd0-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8edd0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8edd0-112">Requirements</span></span>  
 <span data-ttu-id="8edd0-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8edd0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8edd0-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8edd0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8edd0-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8edd0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8edd0-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8edd0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edd0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8edd0-117">See also</span></span>

- [<span data-ttu-id="8edd0-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="8edd0-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8edd0-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="8edd0-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
