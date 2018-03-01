---
title: "Метод ExportNestedTypeForwarder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eee41e9f71d600a74cc9f74b538ad9e215f0d905
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="3eb1f-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="3eb1f-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="3eb1f-103">Добавляет метод передачи типа для вложенного типа в таблицу типов заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eb1f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3eb1f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3eb1f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3eb1f-106">Идентификатор сборки для экспорта.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3eb1f-107">Маркер файла или сборки идентификатор файла, определяющего тип.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="3eb1f-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="3eb1f-109">Маркер родительского типа.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3eb1f-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3eb1f-111">`ComType`флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="3eb1f-112">Получает маркер экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-112">Receives token of export type.</span></span> <span data-ttu-id="3eb1f-113">Это необходимо только для выдачи вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eb1f-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3eb1f-114">Return Value</span></span>  
 <span data-ttu-id="3eb1f-115">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3eb1f-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb1f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3eb1f-116">Requirements</span></span>  
 <span data-ttu-id="3eb1f-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="3eb1f-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb1f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3eb1f-118">See Also</span></span>  
 [<span data-ttu-id="3eb1f-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3eb1f-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3eb1f-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3eb1f-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3eb1f-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="3eb1f-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
