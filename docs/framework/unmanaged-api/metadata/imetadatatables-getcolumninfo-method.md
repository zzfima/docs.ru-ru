---
title: Метод IMetaDataTables::GetColumnInfo
ms.date: 10/10/2019
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
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177121"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="8ec64-102">Метод IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="8ec64-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="8ec64-103">Получает данные об указанном столбце в указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="8ec64-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ec64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ec64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ec64-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="8ec64-106">(в) Индекс желаемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8ec64-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="8ec64-107">(в) Индекс желаемого столбца.</span><span class="sxs-lookup"><span data-stu-id="8ec64-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="8ec64-108">(ваут) Указатель на смещение столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="8ec64-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="8ec64-109">(ваут) Указатель на размер, в байтах, столбца.</span><span class="sxs-lookup"><span data-stu-id="8ec64-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="8ec64-110">(ваут) Указатель на тип значений в столбце.</span><span class="sxs-lookup"><span data-stu-id="8ec64-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="8ec64-111">(ваут) Указатель указателя на имя столбца.</span><span class="sxs-lookup"><span data-stu-id="8ec64-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="8ec64-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ec64-112">Remarks</span></span>

<span data-ttu-id="8ec64-113">Тип возвращенной колонки относится к диапазону значений:</span><span class="sxs-lookup"><span data-stu-id="8ec64-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="8ec64-114">pType</span><span class="sxs-lookup"><span data-stu-id="8ec64-114">pType</span></span>                    | <span data-ttu-id="8ec64-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8ec64-115">Description</span></span>   | <span data-ttu-id="8ec64-116">Функция помощника</span><span class="sxs-lookup"><span data-stu-id="8ec64-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="8ec64-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="8ec64-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="8ec64-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="8ec64-118">(0..63)</span></span>   | <span data-ttu-id="8ec64-119">Избавить</span><span class="sxs-lookup"><span data-stu-id="8ec64-119">Rid</span></span>           | <span data-ttu-id="8ec64-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-120">**IsRidType**</span></span><br><span data-ttu-id="8ec64-121">**Исидортокен**</span><span class="sxs-lookup"><span data-stu-id="8ec64-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="8ec64-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="8ec64-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="8ec64-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="8ec64-123">(64..95)</span></span> | <span data-ttu-id="8ec64-124">Закодированный токен</span><span class="sxs-lookup"><span data-stu-id="8ec64-124">Coded token</span></span> | <span data-ttu-id="8ec64-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="8ec64-126">**Исидортокен**</span><span class="sxs-lookup"><span data-stu-id="8ec64-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="8ec64-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="8ec64-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="8ec64-128">Int16</span><span class="sxs-lookup"><span data-stu-id="8ec64-128">Int16</span></span>         | <span data-ttu-id="8ec64-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="8ec64-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="8ec64-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="8ec64-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="8ec64-131">UInt16</span></span>        | <span data-ttu-id="8ec64-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="8ec64-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="8ec64-133">`iLONG` (98)</span></span>             | <span data-ttu-id="8ec64-134">Int32</span><span class="sxs-lookup"><span data-stu-id="8ec64-134">Int32</span></span>         | <span data-ttu-id="8ec64-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="8ec64-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="8ec64-136">`iULONG` (99)</span></span>            | <span data-ttu-id="8ec64-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="8ec64-137">UInt32</span></span>        | <span data-ttu-id="8ec64-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="8ec64-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="8ec64-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="8ec64-140">Byte</span><span class="sxs-lookup"><span data-stu-id="8ec64-140">Byte</span></span>          | <span data-ttu-id="8ec64-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="8ec64-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="8ec64-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="8ec64-143">Строка</span><span class="sxs-lookup"><span data-stu-id="8ec64-143">String</span></span>        | <span data-ttu-id="8ec64-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="8ec64-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="8ec64-145">`iGUID` (102)</span></span>            | <span data-ttu-id="8ec64-146">Guid</span><span class="sxs-lookup"><span data-stu-id="8ec64-146">Guid</span></span>          | <span data-ttu-id="8ec64-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="8ec64-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="8ec64-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="8ec64-149">BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="8ec64-149">Blob</span></span>          | <span data-ttu-id="8ec64-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="8ec64-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="8ec64-151">Значения, которые хранятся в *куче* `IsHeapType == true`(т.е.), можно прочитать с помощью:</span><span class="sxs-lookup"><span data-stu-id="8ec64-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="8ec64-152">`iSTRING`: **IMetadataTables.GetString**</span><span class="sxs-lookup"><span data-stu-id="8ec64-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="8ec64-153">`iGUID`: **IMetadataTables.GetGUID**</span><span class="sxs-lookup"><span data-stu-id="8ec64-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="8ec64-154">`iBLOB`: **IMetadataTables.GetBlob**</span><span class="sxs-lookup"><span data-stu-id="8ec64-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ec64-155">Чтобы использовать константы, определенные в `#define _DEFINE_META_DATA_META_CONSTANTS` таблице выше, включите директиву, предоставляемую файлом *заголовка cor.h.*</span><span class="sxs-lookup"><span data-stu-id="8ec64-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="8ec64-156">Требования</span><span class="sxs-lookup"><span data-stu-id="8ec64-156">Requirements</span></span>  
 <span data-ttu-id="8ec64-157">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ec64-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ec64-158">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ec64-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ec64-159">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ec64-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ec64-160">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ec64-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec64-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8ec64-161">See also</span></span>

- [<span data-ttu-id="8ec64-162">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="8ec64-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8ec64-163">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="8ec64-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
