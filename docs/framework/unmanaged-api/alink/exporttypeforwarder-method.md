---
title: Метод ExportTypeForwarder
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f97f46595f43c7576c499c6b9944f7e3509662fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742006"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="ac38d-102">Метод ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="ac38d-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="ac38d-103">Добавляет метод передачи типа с таблицей type данной сборки.</span><span class="sxs-lookup"><span data-stu-id="ac38d-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac38d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac38d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac38d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac38d-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="ac38d-106">Ссылка на сборку, к которому относится метод передачи типа.</span><span class="sxs-lookup"><span data-stu-id="ac38d-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ac38d-107">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="ac38d-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ac38d-108">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="ac38d-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ac38d-109">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="ac38d-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ac38d-110">Получает маркер экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="ac38d-110">Receives the token of the exported type.</span></span> <span data-ttu-id="ac38d-111">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="ac38d-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac38d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac38d-112">Return Value</span></span>  
 <span data-ttu-id="ac38d-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ac38d-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac38d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ac38d-114">Requirements</span></span>  
 <span data-ttu-id="ac38d-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="ac38d-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac38d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ac38d-116">See also</span></span>

- [<span data-ttu-id="ac38d-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ac38d-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ac38d-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ac38d-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ac38d-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="ac38d-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
