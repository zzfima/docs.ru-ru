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
ms.openlocfilehash: 7dfaedad48291ac09f6959bc7b314ae0d9da76e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742043"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="65bf0-102">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="65bf0-102">ExportNestedType Method</span></span>
<span data-ttu-id="65bf0-103">Задает вложенные типы как экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="65bf0-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="65bf0-104">[Метод ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) также можно экспортировать вложенные типы, но этот метод работает быстрее.</span><span class="sxs-lookup"><span data-stu-id="65bf0-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65bf0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65bf0-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="65bf0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="65bf0-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="65bf0-107">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="65bf0-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="65bf0-108">Маркер файла или сборки, определяющей тип, чтобы стать экспортируемый файл.</span><span class="sxs-lookup"><span data-stu-id="65bf0-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="65bf0-109">Токен типа, чтобы стать экспортируемый типа.</span><span class="sxs-lookup"><span data-stu-id="65bf0-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="65bf0-110">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="65bf0-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="65bf0-111">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="65bf0-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="65bf0-112">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="65bf0-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="65bf0-113">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="65bf0-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="65bf0-114">Получает маркер для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="65bf0-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65bf0-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65bf0-115">Return Value</span></span>  
 <span data-ttu-id="65bf0-116">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="65bf0-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65bf0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="65bf0-117">Requirements</span></span>  
 <span data-ttu-id="65bf0-118">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="65bf0-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bf0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="65bf0-119">See also</span></span>

- [<span data-ttu-id="65bf0-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="65bf0-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="65bf0-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="65bf0-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="65bf0-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="65bf0-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
