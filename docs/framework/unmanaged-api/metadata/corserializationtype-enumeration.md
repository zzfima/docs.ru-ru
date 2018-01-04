---
title: "Перечисление CorSerializationType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSerializationType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSerializationType
helpviewer_keywords: CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e43151b1611f5b9b8218d30ba46a9143f463c193
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="7da9a-102">Перечисление CorSerializationType</span><span class="sxs-lookup"><span data-stu-id="7da9a-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="7da9a-103">Задает способ сериализации объекта средой CLR.</span><span class="sxs-lookup"><span data-stu-id="7da9a-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7da9a-104">Syntax</span></span>  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="7da9a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7da9a-105">Members</span></span>  
  
|<span data-ttu-id="7da9a-106">Член</span><span class="sxs-lookup"><span data-stu-id="7da9a-106">Member</span></span>|<span data-ttu-id="7da9a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="7da9a-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="7da9a-108">Сериализация объекта не определено.</span><span class="sxs-lookup"><span data-stu-id="7da9a-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="7da9a-109">Объект сериализуется как логический тип.</span><span class="sxs-lookup"><span data-stu-id="7da9a-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="7da9a-110">Объект сериализуется как тип символа.</span><span class="sxs-lookup"><span data-stu-id="7da9a-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="7da9a-111">Объект сериализуется как целое число со знаком 1 байт.</span><span class="sxs-lookup"><span data-stu-id="7da9a-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="7da9a-112">Объект сериализуется как 1-байтовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="7da9a-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="7da9a-113">Объект сериализуется как целое число со знаком длиной 2 байта.</span><span class="sxs-lookup"><span data-stu-id="7da9a-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="7da9a-114">Объект сериализуется как целое число без знака длиной 2 байта.</span><span class="sxs-lookup"><span data-stu-id="7da9a-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="7da9a-115">Объект сериализуется как целое число со знаком 4 байта.</span><span class="sxs-lookup"><span data-stu-id="7da9a-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="7da9a-116">Объект сериализуется как 4-байтовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="7da9a-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="7da9a-117">Объект сериализуется как целое число со знаком размером 8 байт.</span><span class="sxs-lookup"><span data-stu-id="7da9a-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="7da9a-118">Объект сериализуется как целое число без знака размером 8 байт.</span><span class="sxs-lookup"><span data-stu-id="7da9a-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="7da9a-119">Объект сериализуется как 4-байтовое с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="7da9a-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="7da9a-120">Объект сериализуется как 8-байтовое число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="7da9a-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="7da9a-121">Объект сериализуется как тип System.String.</span><span class="sxs-lookup"><span data-stu-id="7da9a-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="7da9a-122">Объект сериализуется как одномерный, нулевой нижней границы массива.</span><span class="sxs-lookup"><span data-stu-id="7da9a-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="7da9a-123">Объект сериализуется как универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="7da9a-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="7da9a-124">Объект сериализуется как объект с тегами.</span><span class="sxs-lookup"><span data-stu-id="7da9a-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="7da9a-125">Объект сериализуется как поле.</span><span class="sxs-lookup"><span data-stu-id="7da9a-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="7da9a-126">Объект сериализуется как свойство.</span><span class="sxs-lookup"><span data-stu-id="7da9a-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="7da9a-127">Объект сериализуется как перечисление.</span><span class="sxs-lookup"><span data-stu-id="7da9a-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7da9a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="7da9a-128">Requirements</span></span>  
 <span data-ttu-id="7da9a-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da9a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da9a-130">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7da9a-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7da9a-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da9a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da9a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7da9a-132">See Also</span></span>  
 [<span data-ttu-id="7da9a-133">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7da9a-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
