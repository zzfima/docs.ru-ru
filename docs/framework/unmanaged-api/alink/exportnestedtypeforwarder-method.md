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
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438414"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="dcb50-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="dcb50-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="dcb50-103">Добавляет сервер пересылки типа для вложенного типа в таблицу типов данной сборки.</span><span class="sxs-lookup"><span data-stu-id="dcb50-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcb50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcb50-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dcb50-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dcb50-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="dcb50-106">Идентификатор сборки, из которой необходимо выполнить экспорт.</span><span class="sxs-lookup"><span data-stu-id="dcb50-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="dcb50-107">Маркер файла или идентификатор сборки файла, который определяет тип.</span><span class="sxs-lookup"><span data-stu-id="dcb50-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="dcb50-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="dcb50-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="dcb50-109">Токен родительского типа.</span><span class="sxs-lookup"><span data-stu-id="dcb50-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="dcb50-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="dcb50-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dcb50-111">`ComType` флаги, такие как `tdPublic` или `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="dcb50-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="dcb50-112">Получает маркер типа экспорта.</span><span class="sxs-lookup"><span data-stu-id="dcb50-112">Receives token of export type.</span></span> <span data-ttu-id="dcb50-113">Это необходимо только для выпуска вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="dcb50-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcb50-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dcb50-114">Return Value</span></span>  
 <span data-ttu-id="dcb50-115">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="dcb50-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb50-116">Требования</span><span class="sxs-lookup"><span data-stu-id="dcb50-116">Requirements</span></span>  
 <span data-ttu-id="dcb50-117">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="dcb50-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb50-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dcb50-118">See also</span></span>

- [<span data-ttu-id="dcb50-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="dcb50-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="dcb50-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="dcb50-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="dcb50-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="dcb50-121">ALink API</span></span>](index.md)
