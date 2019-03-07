---
title: Метод IMetaDataTables::GetBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be7e375f2683ef7f37f2e1e141e1c8a3b00da09a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497045"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="ec5e5-102">Метод IMetaDataTables::GetBlob</span><span class="sxs-lookup"><span data-stu-id="ec5e5-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="ec5e5-103">Возвращает указатель на большой двоичный объект (BLOB) в индексе указанного столбца.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec5e5-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec5e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec5e5-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="ec5e5-106">[in] Адрес памяти, из которого необходимо получить `ppData`.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="ec5e5-107">[out] Указатель на размер в байтах из `ppData`.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ec5e5-108">[out] Получить указатель на указатель на двоичные данные.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5e5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ec5e5-109">Requirements</span></span>  
 <span data-ttu-id="ec5e5-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec5e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec5e5-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec5e5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec5e5-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec5e5-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec5e5-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5e5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ec5e5-114">See also</span></span>
- [<span data-ttu-id="ec5e5-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ec5e5-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ec5e5-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ec5e5-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
