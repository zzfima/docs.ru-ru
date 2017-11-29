---
title: "Метод GetScope 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3ebcb90142cc70a2d246d2e9ea6c42babe83b18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="731f8-102">Метод GetScope 1</span><span class="sxs-lookup"><span data-stu-id="731f8-102">GetScope Method1</span></span>
<span data-ttu-id="731f8-103">Возвращает область импортирования.</span><span class="sxs-lookup"><span data-stu-id="731f8-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="731f8-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="731f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="731f8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="731f8-106">Уникальный идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="731f8-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="731f8-107">Уникальный идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="731f8-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="731f8-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="731f8-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="731f8-109">Получает [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс для области.</span><span class="sxs-lookup"><span data-stu-id="731f8-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="731f8-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="731f8-110">Return Value</span></span>  
 <span data-ttu-id="731f8-111">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="731f8-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="731f8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="731f8-112">Requirements</span></span>  
 <span data-ttu-id="731f8-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="731f8-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731f8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="731f8-114">See Also</span></span>  
 [<span data-ttu-id="731f8-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="731f8-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="731f8-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="731f8-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="731f8-117">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="731f8-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
