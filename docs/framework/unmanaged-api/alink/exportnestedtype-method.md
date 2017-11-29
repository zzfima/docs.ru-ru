---
title: "Метод ExportNestedType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedType
helpviewer_keywords: ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 378d1e8b21b8d3993377ac08ff7006c420117bfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="79f1c-102">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="79f1c-102">ExportNestedType Method</span></span>
<span data-ttu-id="79f1c-103">Задает вложенные типы как экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="79f1c-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="79f1c-104">[Метод ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) также можно экспортировать вложенные типы, но этот метод работает быстрее.</span><span class="sxs-lookup"><span data-stu-id="79f1c-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79f1c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79f1c-105">Syntax</span></span>  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="79f1c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="79f1c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="79f1c-107">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="79f1c-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="79f1c-108">Маркер файла или сборка файла, определяющая тип, который будет помечен в качестве экспортируемого.</span><span class="sxs-lookup"><span data-stu-id="79f1c-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="79f1c-109">Введите маркер типа будут сделаны может быть экспортирован.</span><span class="sxs-lookup"><span data-stu-id="79f1c-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="79f1c-110">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="79f1c-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="79f1c-111">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="79f1c-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="79f1c-112">`ComType`флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="79f1c-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="79f1c-113">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="79f1c-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="79f1c-114">Получает маркер для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="79f1c-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79f1c-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="79f1c-115">Return Value</span></span>  
 <span data-ttu-id="79f1c-116">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="79f1c-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79f1c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="79f1c-117">Requirements</span></span>  
 <span data-ttu-id="79f1c-118">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="79f1c-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f1c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="79f1c-119">See Also</span></span>  
 [<span data-ttu-id="79f1c-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="79f1c-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="79f1c-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="79f1c-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="79f1c-122">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="79f1c-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
