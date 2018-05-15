---
title: Метод IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 756b0ff726c31bf096a1c1b70004c3ff82fe9979
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="dd827-102">Метод IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="dd827-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="dd827-103">Возвращает имя, размер и содержимое потока метаданных по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="dd827-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd827-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd827-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd827-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd827-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="dd827-106">[in] Индекс потока запрошенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="dd827-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="dd827-107">[out] Указатель на имя потока.</span><span class="sxs-lookup"><span data-stu-id="dd827-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="dd827-108">[out] Указатель на поток метаданных.</span><span class="sxs-lookup"><span data-stu-id="dd827-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="dd827-109">[out] Размер в байтах для `ppv`.</span><span class="sxs-lookup"><span data-stu-id="dd827-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd827-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dd827-110">Requirements</span></span>  
 <span data-ttu-id="dd827-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd827-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd827-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd827-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd827-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd827-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd827-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd827-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd827-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dd827-115">See Also</span></span>  
 [<span data-ttu-id="dd827-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="dd827-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="dd827-117">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="dd827-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
