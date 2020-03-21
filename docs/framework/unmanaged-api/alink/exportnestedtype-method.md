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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179416"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="03a2c-102">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="03a2c-102">ExportNestedType Method</span></span>
<span data-ttu-id="03a2c-103">Определяет вложенные типы как экспортируемые.</span><span class="sxs-lookup"><span data-stu-id="03a2c-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="03a2c-104">[Метод ExportType](exporttype-method.md) также может экспортировать вложенные типы, но этот метод быстрее.</span><span class="sxs-lookup"><span data-stu-id="03a2c-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a2c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03a2c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="03a2c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="03a2c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="03a2c-107">Идентификатор сборки для экспорта с.</span><span class="sxs-lookup"><span data-stu-id="03a2c-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="03a2c-108">Файл токен или сборка файла, определяющий тип, который будет экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="03a2c-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="03a2c-109">Введите токен типа, который будет экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="03a2c-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="03a2c-110">Токен родительского типа.</span><span class="sxs-lookup"><span data-stu-id="03a2c-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="03a2c-111">Полностью квалифицированное название типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="03a2c-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="03a2c-112">`ComType`флаги, `tdPublic` `tdNested`такие как или .</span><span class="sxs-lookup"><span data-stu-id="03a2c-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="03a2c-113">Это значение может быть передано [методу DefineExportedType.](../metadata/imetadataassemblyemit-defineexportedtype-method.md)</span><span class="sxs-lookup"><span data-stu-id="03a2c-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="03a2c-114">Получает токен для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="03a2c-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03a2c-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03a2c-115">Return Value</span></span>  
 <span data-ttu-id="03a2c-116">Возвращает S_OK, если метод успешно.</span><span class="sxs-lookup"><span data-stu-id="03a2c-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a2c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="03a2c-117">Requirements</span></span>  
 <span data-ttu-id="03a2c-118">Требуетa alink.h</span><span class="sxs-lookup"><span data-stu-id="03a2c-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a2c-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="03a2c-119">See also</span></span>

- [<span data-ttu-id="03a2c-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="03a2c-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="03a2c-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="03a2c-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="03a2c-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="03a2c-122">ALink API</span></span>](index.md)
