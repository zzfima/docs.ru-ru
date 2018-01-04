---
title: "Метод IMetaDataTables::GetString"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2c0df58d1de7cc7c1eedfdea6c0e698cbd9cb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="a5771-102">Метод IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="a5771-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="a5771-103">Возвращает строку с указанным индексом из столбца таблицы в текущей области ссылки.</span><span class="sxs-lookup"><span data-stu-id="a5771-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5771-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5771-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5771-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5771-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="a5771-106">[in] Индекс, с которого начинается поиск следующего значения.</span><span class="sxs-lookup"><span data-stu-id="a5771-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="a5771-107">[out] Указатель на указатель на значение возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="a5771-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5771-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a5771-108">Requirements</span></span>  
 <span data-ttu-id="a5771-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5771-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5771-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5771-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5771-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5771-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5771-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5771-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5771-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a5771-113">See Also</span></span>  
 [<span data-ttu-id="a5771-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a5771-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a5771-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a5771-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
