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
ms.openlocfilehash: 4dfb31a2fad8a07b3821ac85bbb43b25693f11d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404112"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="d0b8c-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="d0b8c-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="d0b8c-103">Добавляет метод передачи типа для вложенного типа в таблицу типов заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b8c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0b8c-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="d0b8c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0b8c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d0b8c-106">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d0b8c-107">Маркер файла или сборки идентификатор файла, определяющего тип.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d0b8c-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="d0b8c-109">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d0b8c-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d0b8c-111">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="d0b8c-112">Получает маркер экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-112">Receives token of export type.</span></span> <span data-ttu-id="d0b8c-113">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0b8c-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d0b8c-114">Return Value</span></span>  
 <span data-ttu-id="d0b8c-115">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="d0b8c-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b8c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d0b8c-116">Requirements</span></span>  
 <span data-ttu-id="d0b8c-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="d0b8c-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b8c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d0b8c-118">See Also</span></span>  
 [<span data-ttu-id="d0b8c-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="d0b8c-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d0b8c-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="d0b8c-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d0b8c-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="d0b8c-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
