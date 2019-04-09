---
title: Метод ExportNestedType
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff159cf794d566be6478ef890c769a0ac72c9b25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176609"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="0cf2d-102">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="0cf2d-102">ExportNestedType Method</span></span>
<span data-ttu-id="0cf2d-103">Задает вложенные типы как экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="0cf2d-104">[Метод ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) также можно экспортировать вложенные типы, но этот метод работает быстрее.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf2d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cf2d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0cf2d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cf2d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0cf2d-107">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0cf2d-108">Маркер файла или сборки, определяющей тип, чтобы стать экспортируемый файл.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="0cf2d-109">Токен типа, чтобы стать экспортируемый типа.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="0cf2d-110">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="0cf2d-111">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="0cf2d-112">флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-112">flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="0cf2d-113">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="0cf2d-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="0cf2d-114">Получает маркер для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cf2d-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0cf2d-115">Return Value</span></span>  
 <span data-ttu-id="0cf2d-116">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0cf2d-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cf2d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0cf2d-117">Requirements</span></span>  
 <span data-ttu-id="0cf2d-118">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="0cf2d-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf2d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0cf2d-119">See also</span></span>

- [<span data-ttu-id="0cf2d-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="0cf2d-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0cf2d-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="0cf2d-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0cf2d-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="0cf2d-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
