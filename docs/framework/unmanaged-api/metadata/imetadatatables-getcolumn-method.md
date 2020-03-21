---
title: Метод IMetaDataTables::GetColumn
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177140"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="1c0e3-102">Метод IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="1c0e3-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="1c0e3-103">Получает указатель на значение, содержащееся в ячейке указанного столбца и строку в данной таблице.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c0e3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c0e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c0e3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c0e3-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="1c0e3-106">(в) Индекс таблицы.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="1c0e3-107">(в) Индекс столбца в таблице.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="1c0e3-108">(в) Индекс строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="1c0e3-109">(ваут) Указатель на значение в ячейке.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="1c0e3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c0e3-110">Remarks</span></span>

<span data-ttu-id="1c0e3-111">Интерпретация возвращенного значения `pVal` зависит от типа столбца.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="1c0e3-112">Тип столбца можно определить, позвонив по [iMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="1c0e3-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="1c0e3-113">Метод **GetColumn** автоматически преобразует столбцы типа **Rid** или **CodedToken** `mdToken` в полные 32-битные значения.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="1c0e3-114">Он также автоматически преобразует 8-битные или 16-битные значения в полные 32-битные значения.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="1c0e3-115">Для столбцов *типа кучи* возвращенный *pVal* будет индексом в соответствующую кучу.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="1c0e3-116">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="1c0e3-116">Column type</span></span>              | <span data-ttu-id="1c0e3-117">pVal содержит</span><span class="sxs-lookup"><span data-stu-id="1c0e3-117">pVal contains</span></span> | <span data-ttu-id="1c0e3-118">Комментарий</span><span class="sxs-lookup"><span data-stu-id="1c0e3-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="1c0e3-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="1c0e3-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="1c0e3-120">(0..63)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-120">(0..63)</span></span>  | <span data-ttu-id="1c0e3-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="1c0e3-121">mdToken</span></span>     | <span data-ttu-id="1c0e3-122">*pVal* будет содержать полный токен.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="1c0e3-123">Функция автоматически преобразует Rid в полный маркер.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="1c0e3-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="1c0e3-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="1c0e3-125">(64..95)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-125">(64..95)</span></span> | <span data-ttu-id="1c0e3-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="1c0e3-126">mdToken</span></span> | <span data-ttu-id="1c0e3-127">По возвращении *pVal* будет содержать полный токен.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="1c0e3-128">Функция автоматически распаковывает CodedToken в полный маркер.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="1c0e3-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="1c0e3-130">Int16</span><span class="sxs-lookup"><span data-stu-id="1c0e3-130">Int16</span></span>         | <span data-ttu-id="1c0e3-131">Автоматически знак-расширенный до 32-битного.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="1c0e3-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="1c0e3-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="1c0e3-133">UInt16</span></span>        | <span data-ttu-id="1c0e3-134">Автоматически знак-расширенный до 32-битного.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="1c0e3-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-135">`iLONG` (98)</span></span>             | <span data-ttu-id="1c0e3-136">Int32</span><span class="sxs-lookup"><span data-stu-id="1c0e3-136">Int32</span></span>         |                                        |
| <span data-ttu-id="1c0e3-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-137">`iULONG` (99)</span></span>            | <span data-ttu-id="1c0e3-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="1c0e3-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="1c0e3-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="1c0e3-140">Byte</span><span class="sxs-lookup"><span data-stu-id="1c0e3-140">Byte</span></span>          | <span data-ttu-id="1c0e3-141">Автоматически знак-расширенный до 32-битного.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="1c0e3-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="1c0e3-143">Индекс струнной кучи</span><span class="sxs-lookup"><span data-stu-id="1c0e3-143">String heap index</span></span> | <span data-ttu-id="1c0e3-144">*pVal* — это индекс в струнную кучу.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="1c0e3-145">Используйте [IMetadataTables::GetString,](imetadatatables-getstring-method.md) чтобы получить фактическое значение строки столбца.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="1c0e3-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-146">`iGUID` (102)</span></span>            | <span data-ttu-id="1c0e3-147">Индекс кучи Guid</span><span class="sxs-lookup"><span data-stu-id="1c0e3-147">Guid heap index</span></span> | <span data-ttu-id="1c0e3-148">*pVal* — это индекс в кучу Guid.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="1c0e3-149">Используйте [IMetadataTables::GetGuid,](imetadatatables-getguid-method.md) чтобы получить фактическое значение guid столбца.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="1c0e3-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="1c0e3-151">Индекс кучи blob</span><span class="sxs-lookup"><span data-stu-id="1c0e3-151">Blob heap index</span></span> | <span data-ttu-id="1c0e3-152">*pVal* является индексом в кучу Blob.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="1c0e3-153">Используйте [IMetadataTables::GetBlob,](imetadatatables-getblob-method.md) чтобы получить фактическое значение blob столбца.</span><span class="sxs-lookup"><span data-stu-id="1c0e3-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="1c0e3-154">Требования</span><span class="sxs-lookup"><span data-stu-id="1c0e3-154">Requirements</span></span>  
 <span data-ttu-id="1c0e3-155">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c0e3-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c0e3-156">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1c0e3-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c0e3-157">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c0e3-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c0e3-158">**Рамочные версии .NET**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c0e3-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0e3-159">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c0e3-159">See also</span></span>

- [<span data-ttu-id="1c0e3-160">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="1c0e3-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1c0e3-161">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="1c0e3-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
