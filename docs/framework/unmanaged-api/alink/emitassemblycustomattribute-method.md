---
title: Метод EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfcc2db3f1f0d8646f903fedb1eb06b39928d00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742122"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="3b726-102">Метод EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="3b726-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="3b726-103">Вызов для установки настраиваемых атрибутов уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="3b726-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b726-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b726-104">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b726-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b726-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3b726-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="3b726-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3b726-107">Файл, который определяет атрибут.</span><span class="sxs-lookup"><span data-stu-id="3b726-107">File that defiles the attribute.</span></span> <span data-ttu-id="3b726-108">Может иметь значение NULL, если `AssemblyID` не обеспечивает несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="3b726-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="3b726-109">Тип настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="3b726-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="3b726-110">Пользовательское значение данных.</span><span class="sxs-lookup"><span data-stu-id="3b726-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="3b726-111">Длина данных пользовательское значение.</span><span class="sxs-lookup"><span data-stu-id="3b726-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="3b726-112">Значение TRUE, если пользовательский атрибут имеет отношение к подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="3b726-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="3b726-113">Значение TRUE, если несколько атрибутов для добавления.</span><span class="sxs-lookup"><span data-stu-id="3b726-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b726-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b726-114">Return Value</span></span>  
 <span data-ttu-id="3b726-115">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3b726-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b726-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3b726-116">Requirements</span></span>  
 <span data-ttu-id="3b726-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="3b726-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b726-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3b726-118">See also</span></span>

- [<span data-ttu-id="3b726-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3b726-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3b726-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3b726-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3b726-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="3b726-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
