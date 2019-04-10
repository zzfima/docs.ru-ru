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
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220088"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="3458a-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="3458a-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="3458a-103">Добавляет метод передачи типа для вложенного типа в таблицу типов данной сборки.</span><span class="sxs-lookup"><span data-stu-id="3458a-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3458a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3458a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3458a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3458a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3458a-106">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="3458a-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3458a-107">Идентификатор маркера или сборки файла, который определяет тип файла.</span><span class="sxs-lookup"><span data-stu-id="3458a-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="3458a-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="3458a-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="3458a-109">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="3458a-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3458a-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="3458a-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="3458a-111">флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="3458a-111">flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="3458a-112">Получает токен типа экспорта.</span><span class="sxs-lookup"><span data-stu-id="3458a-112">Receives token of export type.</span></span> <span data-ttu-id="3458a-113">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="3458a-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3458a-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3458a-114">Return Value</span></span>  
 <span data-ttu-id="3458a-115">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3458a-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3458a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3458a-116">Requirements</span></span>  
 <span data-ttu-id="3458a-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="3458a-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3458a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3458a-118">See also</span></span>

- [<span data-ttu-id="3458a-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3458a-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3458a-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3458a-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3458a-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="3458a-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
