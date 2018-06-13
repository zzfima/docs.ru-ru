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
ms.openlocfilehash: 0afe4daa1c85f3e15addac55bdbe631d40e03f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407574"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="89431-102">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="89431-102">ExportNestedType Method</span></span>
<span data-ttu-id="89431-103">Задает вложенные типы как экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="89431-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="89431-104">[Метод ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) также можно экспортировать вложенные типы, но этот метод работает быстрее.</span><span class="sxs-lookup"><span data-stu-id="89431-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89431-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89431-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="89431-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="89431-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="89431-107">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="89431-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="89431-108">Маркер файла или сборка файла, определяющая тип, который будет помечен в качестве экспортируемого.</span><span class="sxs-lookup"><span data-stu-id="89431-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="89431-109">Введите маркер типа будут сделаны может быть экспортирован.</span><span class="sxs-lookup"><span data-stu-id="89431-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="89431-110">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="89431-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="89431-111">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="89431-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="89431-112">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="89431-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="89431-113">Это значение может быть передано в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="89431-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="89431-114">Получает маркер для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="89431-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89431-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89431-115">Return Value</span></span>  
 <span data-ttu-id="89431-116">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="89431-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89431-117">Требования</span><span class="sxs-lookup"><span data-stu-id="89431-117">Requirements</span></span>  
 <span data-ttu-id="89431-118">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="89431-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89431-119">См. также</span><span class="sxs-lookup"><span data-stu-id="89431-119">See Also</span></span>  
 [<span data-ttu-id="89431-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="89431-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="89431-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="89431-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="89431-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="89431-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
