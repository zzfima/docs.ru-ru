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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145877"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="40d04-102">Перечисление CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="40d04-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="40d04-103">Содержит значения, описывающие типы соглашений о вызовах, выполняемых в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="40d04-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40d04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40d04-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="40d04-105">Участники</span><span class="sxs-lookup"><span data-stu-id="40d04-105">Members</span></span>  
  
|<span data-ttu-id="40d04-106">Член</span><span class="sxs-lookup"><span data-stu-id="40d04-106">Member</span></span>|<span data-ttu-id="40d04-107">Описание</span><span class="sxs-lookup"><span data-stu-id="40d04-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="40d04-108">Указывает соглашение о вызовах по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40d04-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="40d04-109">Указывает, что этот метод принимает переменное количество параметров.</span><span class="sxs-lookup"><span data-stu-id="40d04-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="40d04-110">Указывает, что вызов к полю.</span><span class="sxs-lookup"><span data-stu-id="40d04-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="40d04-111">Указывает, что вызов предназначен для локального метода.</span><span class="sxs-lookup"><span data-stu-id="40d04-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="40d04-112">Указывает, что вызов к свойству.</span><span class="sxs-lookup"><span data-stu-id="40d04-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="40d04-113">Указывает, что вызов является неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="40d04-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="40d04-114">Показывает создание экземпляра универсального метода.</span><span class="sxs-lookup"><span data-stu-id="40d04-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="40d04-115">Указывает метод, который принимает переменное количество параметров вызова PInvoke 64-разрядной.</span><span class="sxs-lookup"><span data-stu-id="40d04-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="40d04-116">Описывает недопустимое 4-разрядное значение.</span><span class="sxs-lookup"><span data-stu-id="40d04-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="40d04-117">Указывает, что соглашение о вызове описывается четырьмя младшими битами.</span><span class="sxs-lookup"><span data-stu-id="40d04-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="40d04-118">Указывает, что старшие биты описывают `this` параметра.</span><span class="sxs-lookup"><span data-stu-id="40d04-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="40d04-119">Указывает, что `this` параметра явно описан в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="40d04-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="40d04-120">Указывает сигнатуру универсального метода с явной количество аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="40d04-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="40d04-121">Это предшествует обычное число параметров.</span><span class="sxs-lookup"><span data-stu-id="40d04-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40d04-122">Требования</span><span class="sxs-lookup"><span data-stu-id="40d04-122">Requirements</span></span>  
 <span data-ttu-id="40d04-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40d04-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40d04-124">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="40d04-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="40d04-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40d04-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d04-126">См. также</span><span class="sxs-lookup"><span data-stu-id="40d04-126">See also</span></span>

- [<span data-ttu-id="40d04-127">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="40d04-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
