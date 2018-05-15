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
ms.openlocfilehash: daf2c3dcaf16e949f8770121d8324cbfe6c7d05b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="a136f-102">Метод EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="a136f-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="a136f-103">Вызов для установки настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="a136f-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a136f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a136f-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="a136f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a136f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a136f-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="a136f-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a136f-107">Файл, понижающий уровень атрибута.</span><span class="sxs-lookup"><span data-stu-id="a136f-107">File that defiles the attribute.</span></span> <span data-ttu-id="a136f-108">Может иметь значение NULL, если `AssemblyID` не указывает на несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="a136f-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a136f-109">Тип настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="a136f-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="a136f-110">Пользовательские данные значения.</span><span class="sxs-lookup"><span data-stu-id="a136f-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="a136f-111">Длина пользовательских данных значения.</span><span class="sxs-lookup"><span data-stu-id="a136f-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="a136f-112">Значение TRUE, если пользовательский атрибут имеет отношение к подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="a136f-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="a136f-113">Значение TRUE, если несколько атрибутов, которые должны быть созданы.</span><span class="sxs-lookup"><span data-stu-id="a136f-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a136f-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a136f-114">Return Value</span></span>  
 <span data-ttu-id="a136f-115">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a136f-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a136f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a136f-116">Requirements</span></span>  
 <span data-ttu-id="a136f-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="a136f-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a136f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a136f-118">See Also</span></span>  
 [<span data-ttu-id="a136f-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a136f-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a136f-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a136f-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a136f-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="a136f-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
