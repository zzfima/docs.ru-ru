---
title: Метод ExportType
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 455f71c5b576d1b57db591dab2a3e59f8a5eed67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777284"
---
# <a name="exporttype-method"></a><span data-ttu-id="af975-102">Метод ExportType</span><span class="sxs-lookup"><span data-stu-id="af975-102">ExportType Method</span></span>
<span data-ttu-id="af975-103">Указывает, что тип является экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="af975-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af975-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af975-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="af975-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af975-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="af975-106">Идентификатор сборки, из которой необходимо выполнить экспорт.</span><span class="sxs-lookup"><span data-stu-id="af975-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="af975-107">Маркер файла или идентификатор сборки файла, который определяет экспортируемый тип.</span><span class="sxs-lookup"><span data-stu-id="af975-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="af975-108">Токен типа, который должен быть сделан экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="af975-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="af975-109">Полное имя типа, которое необходимо сделать экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="af975-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="af975-110">`ComType`Флаги, `tdPublic` такие `tdNested`как или.</span><span class="sxs-lookup"><span data-stu-id="af975-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="af975-111">Этот параметр может быть передан [методу дефиникспортедтипе](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="af975-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="af975-112">Получает токен для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="af975-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af975-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="af975-113">Return Value</span></span>  
 <span data-ttu-id="af975-114">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="af975-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af975-115">Требования</span><span class="sxs-lookup"><span data-stu-id="af975-115">Requirements</span></span>  
 <span data-ttu-id="af975-116">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="af975-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af975-117">См. также</span><span class="sxs-lookup"><span data-stu-id="af975-117">See also</span></span>

- [<span data-ttu-id="af975-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="af975-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="af975-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="af975-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="af975-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="af975-120">ALink API</span></span>](index.md)
