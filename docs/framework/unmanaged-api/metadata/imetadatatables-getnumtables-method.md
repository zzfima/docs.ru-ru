---
title: Метод IMetaDataTables::GetNumTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 913b452de54dcee95470dbbb039d5d7d5126a559
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453003"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="f6c5f-102">Метод IMetaDataTables::GetNumTables</span><span class="sxs-lookup"><span data-stu-id="f6c5f-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="f6c5f-103">Возвращает количество таблиц в области текущего `IMetaDataTables` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6c5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6c5f-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6c5f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6c5f-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="f6c5f-106">[out] Указатель на число таблиц в области текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6c5f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f6c5f-107">Requirements</span></span>  
 <span data-ttu-id="f6c5f-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6c5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6c5f-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6c5f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6c5f-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6c5f-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6c5f-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6c5f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c5f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f6c5f-112">See Also</span></span>  
 [<span data-ttu-id="f6c5f-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f6c5f-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f6c5f-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f6c5f-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
