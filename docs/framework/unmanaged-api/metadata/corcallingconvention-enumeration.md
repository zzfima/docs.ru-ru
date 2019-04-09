---
title: Перечисление CorCallingConvention
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44a4b5903cec2249eb1e176381fe3d8e600dd5e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145877"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="a5ad5-102">Перечисление CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="a5ad5-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="a5ad5-103">Содержит значения, описывающие типы соглашений о вызовах, выполняемых в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ad5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5ad5-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="a5ad5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a5ad5-105">Members</span></span>  
  
|<span data-ttu-id="a5ad5-106">Член</span><span class="sxs-lookup"><span data-stu-id="a5ad5-106">Member</span></span>|<span data-ttu-id="a5ad5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a5ad5-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="a5ad5-108">Указывает соглашение о вызовах по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="a5ad5-109">Указывает, что этот метод принимает переменное количество параметров.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="a5ad5-110">Указывает, что вызов к полю.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="a5ad5-111">Указывает, что вызов предназначен для локального метода.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="a5ad5-112">Указывает, что вызов к свойству.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="a5ad5-113">Указывает, что вызов является неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="a5ad5-114">Показывает создание экземпляра универсального метода.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="a5ad5-115">Указывает метод, который принимает переменное количество параметров вызова PInvoke 64-разрядной.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="a5ad5-116">Описывает недопустимое 4-разрядное значение.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="a5ad5-117">Указывает, что соглашение о вызове описывается четырьмя младшими битами.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="a5ad5-118">Указывает, что старшие биты описывают `this` параметра.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="a5ad5-119">Указывает, что `this` параметра явно описан в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="a5ad5-120">Указывает сигнатуру универсального метода с явной количество аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="a5ad5-121">Это предшествует обычное число параметров.</span><span class="sxs-lookup"><span data-stu-id="a5ad5-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5ad5-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a5ad5-122">Requirements</span></span>  
 <span data-ttu-id="a5ad5-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ad5-124">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a5ad5-124">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="a5ad5-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a5ad5-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5ad5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a5ad5-126">See also</span></span>

- [<span data-ttu-id="a5ad5-127">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="a5ad5-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
