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
ms.openlocfilehash: 376b9ff09ad38ca43d57fcf064458e0331da8aad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442001"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="c5aa4-102">Метод IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="c5aa4-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="c5aa4-103">Возвращает указатель на значение, содержащееся в ячейке указанного столбца и строки в заданной таблице.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5aa4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5aa4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5aa4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5aa4-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="c5aa4-106">окне Индекс таблицы.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="c5aa4-107">окне Индекс столбца в таблице.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="c5aa4-108">окне Индекс строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="c5aa4-109">заполняет Указатель на значение в ячейке.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-109">[out] A pointer to the value in the cell.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="c5aa4-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5aa4-110">Remarks</span></span>

<span data-ttu-id="c5aa4-111">Интерпретация значения, возвращаемого с помощью `pVal`, зависит от типа столбца.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="c5aa4-112">Тип столбца можно определить с помощью метода [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="c5aa4-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="c5aa4-113">Метод **DataColumn** автоматически преобразует столбцы типа **RID** или **кодедтокен** в полные 32-разрядные значения `mdToken`.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="c5aa4-114">Он также автоматически преобразует 8-битные или 16-битные значения в полные 32-разрядные значения.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span> 
- <span data-ttu-id="c5aa4-115">Для столбцов типа *кучи* возвращенный *Pval* будет индексом в соответствующей куче.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="c5aa4-116">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="c5aa4-116">Column type</span></span>              | <span data-ttu-id="c5aa4-117">pVal содержит</span><span class="sxs-lookup"><span data-stu-id="c5aa4-117">pVal contains</span></span> | <span data-ttu-id="c5aa4-118">Комментарий</span><span class="sxs-lookup"><span data-stu-id="c5aa4-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="c5aa4-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="c5aa4-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="c5aa4-120">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-120">(0..63)</span></span>  | <span data-ttu-id="c5aa4-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="c5aa4-121">mdToken</span></span>     | <span data-ttu-id="c5aa4-122">*Pval* будет содержать полный маркер.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="c5aa4-123">Функция автоматически преобразует RID в полный маркер.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="c5aa4-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="c5aa4-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="c5aa4-125">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-125">(64..95)</span></span> | <span data-ttu-id="c5aa4-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="c5aa4-126">mdToken</span></span> | <span data-ttu-id="c5aa4-127">После возврата *Pval* будет содержать полный маркер.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="c5aa4-128">Функция автоматически распаковывает Кодедтокен в полную лексему.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="c5aa4-129">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="c5aa4-130">Int16</span><span class="sxs-lookup"><span data-stu-id="c5aa4-130">Int16</span></span>         | <span data-ttu-id="c5aa4-131">Автоматический вход в 32-разрядный.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="c5aa4-132">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="c5aa4-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="c5aa4-133">UInt16</span></span>        | <span data-ttu-id="c5aa4-134">Автоматический вход в 32-разрядный.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="c5aa4-135">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-135">`iLONG` (98)</span></span>             | <span data-ttu-id="c5aa4-136">Int32</span><span class="sxs-lookup"><span data-stu-id="c5aa4-136">Int32</span></span>         |                                        | 
| <span data-ttu-id="c5aa4-137">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-137">`iULONG` (99)</span></span>            | <span data-ttu-id="c5aa4-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="c5aa4-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="c5aa4-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="c5aa4-140">Байт</span><span class="sxs-lookup"><span data-stu-id="c5aa4-140">Byte</span></span>          | <span data-ttu-id="c5aa4-141">Автоматический вход в 32-разрядный.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="c5aa4-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="c5aa4-143">Индекс строковой кучи</span><span class="sxs-lookup"><span data-stu-id="c5aa4-143">String heap index</span></span> | <span data-ttu-id="c5aa4-144">*Pval* — это индекс в куче строк.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="c5aa4-145">Используйте [IMetadataTables:: GetString](imetadatatables-getstring-method.md) , чтобы получить фактическое строковое значение столбца.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="c5aa4-146">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-146">`iGUID` (102)</span></span>            | <span data-ttu-id="c5aa4-147">Индекс кучи GUID</span><span class="sxs-lookup"><span data-stu-id="c5aa4-147">Guid heap index</span></span> | <span data-ttu-id="c5aa4-148">*Pval* — это индекс в куче GUID.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="c5aa4-149">Чтобы получить действительное значение GUID столбца, используйте [IMetadataTables::](imetadatatables-getguid-method.md) DataColumn.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="c5aa4-150">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="c5aa4-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="c5aa4-151">Индекс кучи больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="c5aa4-151">Blob heap index</span></span> | <span data-ttu-id="c5aa4-152">*Pval* — это индекс в куче больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="c5aa4-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="c5aa4-153">Для получения действительного значения большого двоичного объекта столбца используйте [IMetadataTables::-BLOB](imetadatatables-getblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c5aa4-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="c5aa4-154">Требования</span><span class="sxs-lookup"><span data-stu-id="c5aa4-154">Requirements</span></span>  
 <span data-ttu-id="c5aa4-155">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5aa4-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5aa4-156">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c5aa4-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5aa4-157">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5aa4-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5aa4-158">**.NET Framework версии** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5aa4-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5aa4-159">См. также</span><span class="sxs-lookup"><span data-stu-id="c5aa4-159">See also</span></span>

- [<span data-ttu-id="c5aa4-160">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c5aa4-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c5aa4-161">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c5aa4-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
