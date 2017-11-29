---
title: "Метод IMetaDataTables2::GetMetaDataStreamInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStreamInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1631ae8398a8daa910931ff705440a2be0cf21b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="9b434-102">Метод IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="9b434-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="9b434-103">Возвращает имя, размер и содержимое потока метаданных по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="9b434-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b434-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b434-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b434-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b434-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="9b434-106">[in] Индекс потока запрошенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="9b434-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="9b434-107">[out] Указатель на имя потока.</span><span class="sxs-lookup"><span data-stu-id="9b434-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="9b434-108">[out] Указатель на поток метаданных.</span><span class="sxs-lookup"><span data-stu-id="9b434-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="9b434-109">[out] Размер в байтах для `ppv`.</span><span class="sxs-lookup"><span data-stu-id="9b434-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b434-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9b434-110">Requirements</span></span>  
 <span data-ttu-id="9b434-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b434-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b434-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b434-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b434-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b434-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b434-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b434-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b434-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9b434-115">See Also</span></span>  
 [<span data-ttu-id="9b434-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="9b434-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="9b434-117">IMetaDataTables-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9b434-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
