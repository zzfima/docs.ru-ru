---
title: Интерфейс IMetaDataTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b2298e2d67e8a50e11d53d864f0e78f3b549e45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131421"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="b6335-102">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b6335-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="b6335-103">Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.</span><span class="sxs-lookup"><span data-stu-id="b6335-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6335-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b6335-104">Methods</span></span>  
  
|<span data-ttu-id="b6335-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b6335-105">Method</span></span>|<span data-ttu-id="b6335-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6335-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6335-107">Метод GetBlob</span><span class="sxs-lookup"><span data-stu-id="b6335-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="b6335-108">Возвращает указатель на большой двоичный объект (BLOB) в индексе указанного столбца.</span><span class="sxs-lookup"><span data-stu-id="b6335-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="b6335-109">Метод GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="b6335-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="b6335-110">Возвращает размер в байтах, кучи больших двоичных ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="b6335-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="b6335-111">Метод GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="b6335-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="b6335-112">Получает указатель на массив токенов, связанных с заданного индекса строки.</span><span class="sxs-lookup"><span data-stu-id="b6335-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="b6335-113">Метод GetColumn</span><span class="sxs-lookup"><span data-stu-id="b6335-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="b6335-114">Возвращает указатель на значения, содержащиеся в столбце в индексе указанного столбца в таблице с индексом указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6335-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b6335-115">Метод GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="b6335-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="b6335-116">Получает данные о заданном столбце в указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="b6335-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="b6335-117">Метод GetGuid</span><span class="sxs-lookup"><span data-stu-id="b6335-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="b6335-118">Возвращает идентификатор GUID из строки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="b6335-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="b6335-119">Метод GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="b6335-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="b6335-120">Возвращает размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="b6335-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="b6335-121">Метод GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="b6335-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="b6335-122">Получает индекс следующий большой двоичный объект в таблице.</span><span class="sxs-lookup"><span data-stu-id="b6335-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="b6335-123">Метод GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="b6335-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="b6335-124">Получает индекс следующего значения GUID в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6335-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="b6335-125">Метод GetNextString</span><span class="sxs-lookup"><span data-stu-id="b6335-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="b6335-126">Получает индекс следующей строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6335-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="b6335-127">Метод GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="b6335-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="b6335-128">Получает индекс строки, содержащей Далее жестко запрограммированные строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6335-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="b6335-129">Метод GetNumTables</span><span class="sxs-lookup"><span data-stu-id="b6335-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="b6335-130">Получает количество таблиц в области текущего `IMetaDataTables` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b6335-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="b6335-131">Метод GetRow</span><span class="sxs-lookup"><span data-stu-id="b6335-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="b6335-132">Возвращает строку по указанному индексу строки, в таблице с индексом указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6335-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b6335-133">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="b6335-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="b6335-134">Получает строку по указанному индексу из столбца таблицы в текущей области ссылки.</span><span class="sxs-lookup"><span data-stu-id="b6335-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="b6335-135">Метод GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="b6335-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="b6335-136">Возвращает размер в байтах, кучи строк.</span><span class="sxs-lookup"><span data-stu-id="b6335-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="b6335-137">Метод GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="b6335-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="b6335-138">Получает индекс для таблицы, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="b6335-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="b6335-139">Метод GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="b6335-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="b6335-140">Получает имя, размер строки, количество строк, число столбцов и ключевой столбец индекса таблицы по индексу указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6335-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b6335-141">Метод GetUserString</span><span class="sxs-lookup"><span data-stu-id="b6335-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="b6335-142">Получает жестко заданную строку по указанному индексу в строковый столбец в текущей области.</span><span class="sxs-lookup"><span data-stu-id="b6335-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="b6335-143">Метод GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="b6335-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="b6335-144">Возвращает размер в байтах, кучи строк пользователя.</span><span class="sxs-lookup"><span data-stu-id="b6335-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6335-145">Требования</span><span class="sxs-lookup"><span data-stu-id="b6335-145">Requirements</span></span>  
 <span data-ttu-id="b6335-146">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6335-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6335-147">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b6335-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6335-148">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6335-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b6335-149">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b6335-149">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6335-150">См. также</span><span class="sxs-lookup"><span data-stu-id="b6335-150">See also</span></span>

- [<span data-ttu-id="b6335-151">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="b6335-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b6335-152">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b6335-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
