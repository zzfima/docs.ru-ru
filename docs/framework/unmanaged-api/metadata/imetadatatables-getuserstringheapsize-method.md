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
ms.openlocfilehash: a217a835e258052ace5b59a70cbc0fa31691d78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452850"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="f4122-102">Метод IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="f4122-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="f4122-103">Возвращает размер в байтах, кучи пользовательских строк.</span><span class="sxs-lookup"><span data-stu-id="f4122-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4122-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4122-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4122-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4122-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="f4122-106">[out] Указатель на размер в байтах кучи пользовательских строк.</span><span class="sxs-lookup"><span data-stu-id="f4122-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4122-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f4122-107">Requirements</span></span>  
 <span data-ttu-id="f4122-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4122-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4122-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f4122-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4122-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4122-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4122-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4122-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4122-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f4122-112">See Also</span></span>  
 [<span data-ttu-id="f4122-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f4122-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f4122-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f4122-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
