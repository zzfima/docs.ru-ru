---
title: Метод ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25b7a708bb2f16433d9de9b5fc1c178cb48874a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658472"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="089e4-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="089e4-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="089e4-103">Добавляет метод передачи типа для вложенного типа в таблицу типов данной сборки.</span><span class="sxs-lookup"><span data-stu-id="089e4-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="089e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="089e4-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="089e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="089e4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="089e4-106">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="089e4-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="089e4-107">Идентификатор маркера или сборки файла, который определяет тип файла.</span><span class="sxs-lookup"><span data-stu-id="089e4-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="089e4-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="089e4-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="089e4-109">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="089e4-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="089e4-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="089e4-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="089e4-111">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="089e4-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="089e4-112">Получает токен типа экспорта.</span><span class="sxs-lookup"><span data-stu-id="089e4-112">Receives token of export type.</span></span> <span data-ttu-id="089e4-113">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="089e4-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="089e4-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="089e4-114">Return Value</span></span>  
 <span data-ttu-id="089e4-115">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="089e4-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="089e4-116">Требования</span><span class="sxs-lookup"><span data-stu-id="089e4-116">Requirements</span></span>  
 <span data-ttu-id="089e4-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="089e4-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="089e4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="089e4-118">See also</span></span>
- [<span data-ttu-id="089e4-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="089e4-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="089e4-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="089e4-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="089e4-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="089e4-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
