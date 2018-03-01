---
title: "Метод ExportTypeForwarder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3fe418b1f8a5d5a6d3c2d36184ca76d5ef9989bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="8bcb3-102">Метод ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="8bcb3-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="8bcb3-103">Добавляет метод передачи типа в таблицу типов заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bcb3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bcb3-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bcb3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bcb3-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="8bcb3-106">Ссылка на сборку, на которую ссылается сервер пересылки типов.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="8bcb3-107">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8bcb3-108">`ComType`флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="8bcb3-109">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="8bcb3-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="8bcb3-110">Получает маркер экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-110">Receives the token of the exported type.</span></span> <span data-ttu-id="8bcb3-111">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bcb3-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8bcb3-112">Return Value</span></span>  
 <span data-ttu-id="8bcb3-113">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="8bcb3-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bcb3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8bcb3-114">Requirements</span></span>  
 <span data-ttu-id="8bcb3-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="8bcb3-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bcb3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8bcb3-116">See Also</span></span>  
 [<span data-ttu-id="8bcb3-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="8bcb3-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8bcb3-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="8bcb3-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8bcb3-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="8bcb3-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
