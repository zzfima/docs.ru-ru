---
title: Метод IMetaDataTables::GetUserStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf6deb4d1420e7b58e1edc7741b683beb591ca5e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782099"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="3a637-102">Метод IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="3a637-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="3a637-103">Возвращает размер в байтах, кучи строк пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a637-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a637-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a637-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a637-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a637-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="3a637-106">[out] Указатель на размер в байтах кучи пользовательских строк.</span><span class="sxs-lookup"><span data-stu-id="3a637-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a637-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3a637-107">Requirements</span></span>  
 <span data-ttu-id="3a637-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a637-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a637-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a637-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a637-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a637-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a637-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a637-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a637-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3a637-112">See also</span></span>

- [<span data-ttu-id="3a637-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="3a637-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3a637-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="3a637-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
