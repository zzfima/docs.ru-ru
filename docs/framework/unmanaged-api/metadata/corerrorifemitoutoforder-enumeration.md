---
title: "Перечисление CorErrorIfEmitOutOfOrder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorErrorIfEmitOutOfOrder
api_location: mscoree.dll
api_type: COM
f1_keywords: CorErrorIfEmitOutOfOrder
helpviewer_keywords: CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2cf80375622912c6bb9a59696f37aed2d594253
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="6ed76-102">Перечисление CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="6ed76-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="6ed76-103">Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.</span><span class="sxs-lookup"><span data-stu-id="6ed76-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ed76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ed76-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="6ed76-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6ed76-105">Members</span></span>  
  
|<span data-ttu-id="6ed76-106">Член</span><span class="sxs-lookup"><span data-stu-id="6ed76-106">Member</span></span>|<span data-ttu-id="6ed76-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6ed76-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="6ed76-108">Указывает поведение по умолчанию, которое не выдает сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="6ed76-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="6ed76-109">Указывает, что компилятор не должен создавать сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="6ed76-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="6ed76-110">Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выпускаются в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="6ed76-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="6ed76-111">Указывает, что когда метод выдается вне очереди, компилятор должен создать сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6ed76-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="6ed76-112">Указывает, что компилятор должен создать сообщение об ошибке при поле выпускаются в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="6ed76-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="6ed76-113">Указывает, что компилятор должен создать сообщение об ошибке при извлечении параметра в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="6ed76-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="6ed76-114">Указывает, что когда свойство выдается вне очереди, компилятор должен создать сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6ed76-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="6ed76-115">Указывает, что компилятор должен создать сообщение об ошибке при извлечении события по порядку.</span><span class="sxs-lookup"><span data-stu-id="6ed76-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ed76-116">Требования</span><span class="sxs-lookup"><span data-stu-id="6ed76-116">Requirements</span></span>  
 <span data-ttu-id="6ed76-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ed76-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ed76-118">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6ed76-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6ed76-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ed76-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed76-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6ed76-120">See Also</span></span>  
 [<span data-ttu-id="6ed76-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="6ed76-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
