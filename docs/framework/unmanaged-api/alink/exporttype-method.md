---
title: "Метод ExportType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportType
api_location: alink.dll
api_type: COM
f1_keywords: ExportType
helpviewer_keywords: ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9cc61d0bc32545b486f4472904b17ed0b59526e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="exporttype-method"></a><span data-ttu-id="809eb-102">Метод ExportType</span><span class="sxs-lookup"><span data-stu-id="809eb-102">ExportType Method</span></span>
<span data-ttu-id="809eb-103">Указывает, что тип может быть экспортирован.</span><span class="sxs-lookup"><span data-stu-id="809eb-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="809eb-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="809eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="809eb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="809eb-106">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="809eb-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="809eb-107">Маркер файла или сборки идентификатор файла, который определяет тип может быть экспортирован.</span><span class="sxs-lookup"><span data-stu-id="809eb-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="809eb-108">Маркер типа будут сделаны может быть экспортирован.</span><span class="sxs-lookup"><span data-stu-id="809eb-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="809eb-109">Полное имя типа будут сделаны может быть экспортирован.</span><span class="sxs-lookup"><span data-stu-id="809eb-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="809eb-110">`ComType`флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="809eb-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="809eb-111">Этот параметр может быть передан [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="809eb-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="809eb-112">Получает маркер для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="809eb-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="809eb-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="809eb-113">Return Value</span></span>  
 <span data-ttu-id="809eb-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="809eb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="809eb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="809eb-115">Requirements</span></span>  
 <span data-ttu-id="809eb-116">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="809eb-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809eb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="809eb-117">See Also</span></span>  
 [<span data-ttu-id="809eb-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="809eb-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="809eb-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="809eb-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="809eb-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="809eb-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
