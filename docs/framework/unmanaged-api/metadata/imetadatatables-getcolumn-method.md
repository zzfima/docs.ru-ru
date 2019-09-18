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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 853f137d91e1b3eb4f3f65a06522618f8441dcb3
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053679"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="11f2e-102">Метод IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="11f2e-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="11f2e-103">Возвращает указатель на значение, содержащееся в ячейке указанного столбца и строки в заданной таблице.</span><span class="sxs-lookup"><span data-stu-id="11f2e-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11f2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11f2e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11f2e-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="11f2e-106">окне Индекс таблицы.</span><span class="sxs-lookup"><span data-stu-id="11f2e-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="11f2e-107">окне Индекс столбца в таблице.</span><span class="sxs-lookup"><span data-stu-id="11f2e-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="11f2e-108">окне Индекс строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="11f2e-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="11f2e-109">заполняет Указатель на значение в ячейке.</span><span class="sxs-lookup"><span data-stu-id="11f2e-109">[out] A pointer to the value in the cell.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="11f2e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="11f2e-110">Remarks</span></span>

<span data-ttu-id="11f2e-111">Интерпретация значения, возвращаемого с помощью `pVal` , зависит от типа столбца.</span><span class="sxs-lookup"><span data-stu-id="11f2e-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="11f2e-112">Тип столбца можно определить с помощью метода [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="11f2e-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="11f2e-113">Метод **DataColumn** автоматически преобразует столбцы типа **RID** или **кодедтокен** в полные 32-разрядные `mdToken` значения.</span><span class="sxs-lookup"><span data-stu-id="11f2e-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="11f2e-114">Он также автоматически преобразует 8-битные или 16-битные значения в полные 32-разрядные значения.</span><span class="sxs-lookup"><span data-stu-id="11f2e-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span> 
- <span data-ttu-id="11f2e-115">Для столбцов типа *кучи* возвращенный *Pval* будет индексом в соответствующей куче.</span><span class="sxs-lookup"><span data-stu-id="11f2e-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="11f2e-116">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="11f2e-116">Column type</span></span>              | <span data-ttu-id="11f2e-117">pVal содержит</span><span class="sxs-lookup"><span data-stu-id="11f2e-117">pVal contains</span></span> | <span data-ttu-id="11f2e-118">Комментарий</span><span class="sxs-lookup"><span data-stu-id="11f2e-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="11f2e-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="11f2e-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="11f2e-120">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="11f2e-120">(0..63)</span></span>  | <span data-ttu-id="11f2e-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="11f2e-121">mdToken</span></span>     | <span data-ttu-id="11f2e-122">*Pval* будет содержать полный маркер.</span><span class="sxs-lookup"><span data-stu-id="11f2e-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="11f2e-123">Функция автоматически преобразует RID в полный маркер.</span><span class="sxs-lookup"><span data-stu-id="11f2e-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="11f2e-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="11f2e-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="11f2e-125">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="11f2e-125">(64..95)</span></span> | <span data-ttu-id="11f2e-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="11f2e-126">mdToken</span></span> | <span data-ttu-id="11f2e-127">После возврата *Pval* будет содержать полный маркер.</span><span class="sxs-lookup"><span data-stu-id="11f2e-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="11f2e-128">Функция автоматически распаковывает Кодедтокен в полную лексему.</span><span class="sxs-lookup"><span data-stu-id="11f2e-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="11f2e-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="11f2e-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="11f2e-130">Int16</span><span class="sxs-lookup"><span data-stu-id="11f2e-130">Int16</span></span>         | <span data-ttu-id="11f2e-131">Автоматический вход в 32-разрядный.</span><span class="sxs-lookup"><span data-stu-id="11f2e-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="11f2e-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="11f2e-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="11f2e-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="11f2e-133">UInt16</span></span>        | <span data-ttu-id="11f2e-134">Автоматический вход в 32-разрядный.</span><span class="sxs-lookup"><span data-stu-id="11f2e-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="11f2e-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="11f2e-135">`iLONG` (98)</span></span>             | <span data-ttu-id="11f2e-136">Int32</span><span class="sxs-lookup"><span data-stu-id="11f2e-136">Int32</span></span>         |                                        | 
| <span data-ttu-id="11f2e-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="11f2e-137">`iULONG` (99)</span></span>            | <span data-ttu-id="11f2e-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="11f2e-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="11f2e-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="11f2e-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="11f2e-140">Byte</span><span class="sxs-lookup"><span data-stu-id="11f2e-140">Byte</span></span>          | <span data-ttu-id="11f2e-141">Автоматический вход в 32-разрядный.</span><span class="sxs-lookup"><span data-stu-id="11f2e-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="11f2e-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="11f2e-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="11f2e-143">Индекс строковой кучи</span><span class="sxs-lookup"><span data-stu-id="11f2e-143">String heap index</span></span> | <span data-ttu-id="11f2e-144">*Pval* — это индекс в куче строк.</span><span class="sxs-lookup"><span data-stu-id="11f2e-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="11f2e-145">Используйте [IMetadataTables:: GetString](imetadatatables-getstring-method.md) , чтобы получить фактическое строковое значение столбца.</span><span class="sxs-lookup"><span data-stu-id="11f2e-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="11f2e-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="11f2e-146">`iGUID` (102)</span></span>            | <span data-ttu-id="11f2e-147">Индекс кучи GUID</span><span class="sxs-lookup"><span data-stu-id="11f2e-147">Guid heap index</span></span> | <span data-ttu-id="11f2e-148">*Pval* — это индекс в куче GUID.</span><span class="sxs-lookup"><span data-stu-id="11f2e-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="11f2e-149">Чтобы получить действительное значение GUID столбца, используйте [IMetadataTables::](imetadatatables-getguid-method.md) DataColumn.</span><span class="sxs-lookup"><span data-stu-id="11f2e-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="11f2e-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="11f2e-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="11f2e-151">Индекс кучи больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="11f2e-151">Blob heap index</span></span> | <span data-ttu-id="11f2e-152">*Pval* — это индекс в куче больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="11f2e-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="11f2e-153">Для получения действительного значения большого двоичного объекта столбца используйте [IMetadataTables::-BLOB](imetadatatables-getblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11f2e-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="11f2e-154">Требования</span><span class="sxs-lookup"><span data-stu-id="11f2e-154">Requirements</span></span>  
 <span data-ttu-id="11f2e-155">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11f2e-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11f2e-156">**Заголовок.** COR. h</span><span class="sxs-lookup"><span data-stu-id="11f2e-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11f2e-157">**Библиотечная** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="11f2e-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11f2e-158">**Версии .NET Framework**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11f2e-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f2e-159">См. также</span><span class="sxs-lookup"><span data-stu-id="11f2e-159">See also</span></span>

- [<span data-ttu-id="11f2e-160">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="11f2e-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="11f2e-161">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="11f2e-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
