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
ms.openlocfilehash: b9ffd9ab9ddb95945744ecf210d0ae1d9d9812ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125831"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="80cb9-102">Метод IMetaDataTables::GetNumTables</span><span class="sxs-lookup"><span data-stu-id="80cb9-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="80cb9-103">Получает количество таблиц в области текущего `IMetaDataTables` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="80cb9-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cb9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80cb9-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80cb9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80cb9-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="80cb9-106">[out] Указатель на количество таблиц в области текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="80cb9-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80cb9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="80cb9-107">Requirements</span></span>  
 <span data-ttu-id="80cb9-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80cb9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80cb9-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80cb9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80cb9-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80cb9-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="80cb9-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="80cb9-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80cb9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="80cb9-112">See also</span></span>

- [<span data-ttu-id="80cb9-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="80cb9-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="80cb9-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="80cb9-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
