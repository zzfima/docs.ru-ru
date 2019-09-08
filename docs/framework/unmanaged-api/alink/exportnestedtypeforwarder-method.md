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
ms.openlocfilehash: eb8112d6d2b5c2cbb257db2f20ff4be5a84e827b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787471"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="548de-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="548de-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="548de-103">Добавляет сервер пересылки типа для вложенного типа в таблицу типов данной сборки.</span><span class="sxs-lookup"><span data-stu-id="548de-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="548de-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="548de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="548de-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="548de-106">Идентификатор сборки, из которой необходимо выполнить экспорт.</span><span class="sxs-lookup"><span data-stu-id="548de-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="548de-107">Маркер файла или идентификатор сборки файла, который определяет тип.</span><span class="sxs-lookup"><span data-stu-id="548de-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="548de-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="548de-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="548de-109">Токен родительского типа.</span><span class="sxs-lookup"><span data-stu-id="548de-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="548de-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="548de-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="548de-111">`ComType`Флаги, `tdPublic` такие `tdNested`как или.</span><span class="sxs-lookup"><span data-stu-id="548de-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="548de-112">Получает маркер типа экспорта.</span><span class="sxs-lookup"><span data-stu-id="548de-112">Receives token of export type.</span></span> <span data-ttu-id="548de-113">Это необходимо только для выпуска вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="548de-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="548de-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="548de-114">Return Value</span></span>  
 <span data-ttu-id="548de-115">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="548de-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548de-116">Требования</span><span class="sxs-lookup"><span data-stu-id="548de-116">Requirements</span></span>  
 <span data-ttu-id="548de-117">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="548de-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548de-118">См. также</span><span class="sxs-lookup"><span data-stu-id="548de-118">See also</span></span>

- [<span data-ttu-id="548de-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="548de-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="548de-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="548de-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="548de-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="548de-121">ALink API</span></span>](index.md)
