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
ms.openlocfilehash: 5bdf9fb50fe06141df6f3818c784588b9e2138af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212028"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="0a754-102">Метод ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="0a754-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="0a754-103">Добавляет метод передачи типа с таблицей type данной сборки.</span><span class="sxs-lookup"><span data-stu-id="0a754-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a754-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a754-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a754-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a754-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="0a754-106">Ссылка на сборку, к которому относится метод передачи типа.</span><span class="sxs-lookup"><span data-stu-id="0a754-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="0a754-107">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="0a754-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0a754-108">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="0a754-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="0a754-109">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="0a754-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="0a754-110">Получает маркер экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="0a754-110">Receives the token of the exported type.</span></span> <span data-ttu-id="0a754-111">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="0a754-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a754-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a754-112">Return Value</span></span>  
 <span data-ttu-id="0a754-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0a754-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a754-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0a754-114">Requirements</span></span>  
 <span data-ttu-id="0a754-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="0a754-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a754-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0a754-116">See also</span></span>

- [<span data-ttu-id="0a754-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="0a754-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0a754-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="0a754-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0a754-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="0a754-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
