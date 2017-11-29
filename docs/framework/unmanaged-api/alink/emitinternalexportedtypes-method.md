---
title: "Метод EmitInternalExportedTypes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location: alink.dll
api_type: COM
f1_keywords: EmitInternalExportedTypes
helpviewer_keywords: EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f354058e0de944bbce9d128d3f4baa9b941fda08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="c30a8-102">Метод EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="c30a8-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="c30a8-103">Выдает типы, добавленные в сборку.</span><span class="sxs-lookup"><span data-stu-id="c30a8-103">Emits types added to the assembly.</span></span> <span data-ttu-id="c30a8-104">Этот метод Выяснив, что добавлены внутренние типы.</span><span class="sxs-lookup"><span data-stu-id="c30a8-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c30a8-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c30a8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c30a8-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c30a8-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="c30a8-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c30a8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c30a8-108">Return Value</span></span>  
 <span data-ttu-id="c30a8-109">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="c30a8-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c30a8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c30a8-110">Requirements</span></span>  
 <span data-ttu-id="c30a8-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="c30a8-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30a8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c30a8-112">See Also</span></span>  
 [<span data-ttu-id="c30a8-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c30a8-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c30a8-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c30a8-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c30a8-115">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="c30a8-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
