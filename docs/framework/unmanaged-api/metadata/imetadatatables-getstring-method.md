---
title: Метод IMetaDataTables::GetString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fed98521c0609ebd8b5f65885d69c77814e9e85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042293"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="29c61-102">Метод IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="29c61-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="29c61-103">Получает строку по указанному индексу из столбца таблицы в текущей области ссылки.</span><span class="sxs-lookup"><span data-stu-id="29c61-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29c61-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29c61-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29c61-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="29c61-106">[in] Индекс, с которого начинается поиск следующего значения.</span><span class="sxs-lookup"><span data-stu-id="29c61-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="29c61-107">[out] Указатель на указатель на значение возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="29c61-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c61-108">Требования</span><span class="sxs-lookup"><span data-stu-id="29c61-108">Requirements</span></span>  
 <span data-ttu-id="29c61-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c61-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c61-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="29c61-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29c61-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29c61-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29c61-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c61-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c61-113">См. также</span><span class="sxs-lookup"><span data-stu-id="29c61-113">See also</span></span>

- [<span data-ttu-id="29c61-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="29c61-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="29c61-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="29c61-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
